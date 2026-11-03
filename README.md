# Zahidur Abedin

Platform engineer in Toronto. I run a self-hosted LLM inference stack, build LLM systems with hard boundaries, and build coding-agent tooling where each agent's role is enforced by its tools.

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

## Builds coding-agent tooling with enforced roles

- Four GitHub Copilot agents (builder, reader, verifier, reviewer), each with its own tool list; the reader holds read-only tools, because in testing an instruction alone did not stop it giving advice.
- A pre-tool-use hook that denies force-push, `git reset --hard`, `rm -rf` on a root or home directory, and access to `.env` and private key files.
- A weekly live check runs the latest Copilot CLI against the kit: the agents load, the hook blocks, and the verifier reports FAIL when it should.

Repos: [copilot-kit](https://github.com/zahidur124/copilot-kit)
