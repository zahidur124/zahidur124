# Zahidur Abedin

Platform engineer in Toronto. I run a self-hosted LLM inference stack, build LLM systems with hard boundaries, and run an agent-driven build pipeline that takes an intent to a tested release.

## Operates inference and trains models

- A self-hosted gateway (llama-swap in front of vLLM) serves 5 models, with a 27B model in NVFP4 as the resident chat model and CPU-side embedding and reranking.
- QLoRA fine-tune scored by a blind judge on a held-out split: 2.57 → 3.67 (n=60, prior private run; public-data rerun in progress).
- Hybrid retrieval with a measured MRR of 0.47 on 44 queries.

Repos: [selfhosted-llm-platform](https://github.com/zahidur124/selfhosted-llm-platform) · [qwen3-qlora-eval](https://github.com/zahidur124/qwen3-qlora-eval)

## Builds LLM systems with hard boundaries

- A production LLM pipeline for a creator business: classification, contract review, receipt reading and reply drafting, with a per-tenant run log and golden tests.
- A trading research agent where the LLM writes JSON rows, never code, and can only reduce risk. Paper trading and signals only.
- A signal desk whose model replies were 43/43 valid against a JSON schema at 0.69 s median.
- A research gate where deterministic checks own recall and the LLM layers can only add findings.

Repos: [research-gate](https://github.com/zahidur124/research-gate)

## Runs an agent-driven software factory

- A harness built on a `features.json` contract and role crews, where the coder never edits tests and every step has a verifier and a reviewer.
- An unattended build pipeline: intent → design crew → build crew → live-test crew → release, with no session open.
- The same approach packaged for GitHub Copilot.

Repos: [agent-build-crew](https://github.com/zahidur124/agent-build-crew) · [copilot-kit](https://github.com/zahidur124/copilot-kit)
