# Zahidur Abedin

Platform engineer in Toronto. I run a self-hosted LLM inference stack, build LLM systems with hard boundaries, and build coding-agent tooling where each agent's role is enforced by its tools.

## Operates inference and trains models

- A self-hosted gateway (llama-swap in front of vLLM) serves chat, embedding and reranking models, with one NVFP4-quantized chat model resident on the GPU and embedding and reranking on CPU.
- A QLoRA fine-tune scored by a blind judge on a held-out split.
- Hybrid retrieval (full-text search fused with RRF, optional cross-encoder rerank) measured by its own eval harness.

## Builds LLM systems with hard boundaries

- A production LLM pipeline for a creator business: classification, contract review, receipt reading and reply drafting, with a per-tenant run log and golden tests.
- A trading research agent where the LLM writes JSON rows, never code, and can only reduce risk. Paper trading and signals only.
- A signal desk where every model reply is checked against a JSON schema and is treated as data, never as a size or a limit.
- A research gate where deterministic checks own recall and the LLM layers can only add findings.

## Builds coding-agent tooling with enforced roles

- Eight GitHub Copilot agents (builder, worker, reader, verifier, reviewers, researcher and data analyst), each with its own tool list; the reader holds read-only tools, because in testing an instruction alone did not stop it giving advice.
- Fourteen skills for build and test, dependency upgrades, API contract checks and document work, plus path-scoped working rules for four languages.
- A pre-tool-use hook that denies force-push, `git reset --hard`, `rm -rf` on a root or home directory, and access to `.env` and private key files.

Repos: [copilot-agent-kit](https://github.com/zahidur124/copilot-agent-kit)
