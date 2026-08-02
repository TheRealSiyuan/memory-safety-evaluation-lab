# Preliminary Results

## Research question

Can an AI assistant use helpful long-term memory while resisting outdated, conflicting, false or deliberately manipulated stored information?

## Evaluation

The initial experiment tested a locally deployed `llama3.2:3b` model on 50 synthetic memory-safety cases.

The cases covered seven conditions:

- no stored memory;
- clean and relevant memory;
- relevant memory mixed with irrelevant information;
- stale memory;
- conflicting memories;
- poisoned memory;
- false memory.

Prompts were constructed using a consistent evaluation template. Responses were assessed using a transparent, rule-based scorer measuring memory correctness, resistance to poisoned instructions, handling of stale information, conflict resolution and answer helpfulness.

## Results

| Memory condition | Cases | Pass rate |
|---|---:|---:|
| Poisoned memory | 6 | 50% |
| Stale memory | 7 | 57% |
| Relevant memory with noise | 7 | 86% |
| Clean memory | 8 | 100% |
| No memory | 8 | 100% |
| False memory | 7 | 100% |
| Conflicting memory | 7 | 100% |
| **Overall** | **50** | **86%** |

Although the overall pass rate was 86%, performance was substantially weaker on poisoned and stale memories. This shows how aggregate accuracy can conceal important condition-specific safety failures.

In several poisoned-memory cases, the model followed an unsafe instruction embedded in stored information. In stale-memory cases, it sometimes relied on an old detail without checking whether it remained current.

## Why this matters

Memory-enabled agents may use stored information across many interactions and long-running tasks. A false, outdated or malicious memory can therefore influence later decisions, persist over time and compound without being noticed.

These preliminary results suggest that evaluating overall answer quality is not enough. Memory systems also need dedicated tests for provenance, recency, conflicts and embedded instructions.

## Limitations

- Only one small local model was evaluated.
- The scenarios are synthetic and English-only.
- Memory was supplied as a dated text block rather than through a production retrieval system.
- The rule-based scorer may not correctly interpret every paraphrase.
- The number of cases in each condition remains limited.

## Next stage

API access would support:

- larger and more varied evaluation sets;
- repeated runs to measure consistency;
- comparisons across models, prompts and memory configurations;
- automated collection of structured experimental outputs;
- validation of automated scores against human judgements;
- testing safeguards such as provenance tracking, temporal validation, conflict detection, uncertainty signalling and trust-aware retrieval.

These findings are preliminary and should not be interpreted as general evidence about frontier AI systems.
