# Python-based Memory Safety Evaluation Lab

A reproducible evaluation framework for studying safety and reliability
failures in AI agents with persistent long-term memory.

## Why this matters

Memory-enabled agents may rely on stored information across many interactions.
False, outdated, conflicting, irrelevant or deliberately poisoned memories can
therefore influence later decisions and compound over time.

## Current work

The evaluation lab currently contains 50 structured test cases covering:

- poisoned memories
- outdated memories
- conflicting memories
- irrelevant memories
- false or misleading memories
- valid and relevant memories

Initial experiments with a locally deployed language model produced an overall
pass rate of 86%, with poisoned memories producing the clearest failures.

## Research direction

The next stage will:

- expand the number and diversity of evaluation cases;
- compare behaviour across models and memory configurations;
- automate repeated and reproducible API-based experiments;
- evaluate provenance tracking, temporal validation and conflict detection;
- test uncertainty-aware and trust-aware memory retrieval.

## Repository status

This is a curated public research repository. The broader experimental
codebase and literature review remain under active development.

## Background

This project forms part of my independent research into persistent-memory
safety, AI-agent reliability and reproducible model evaluation.
