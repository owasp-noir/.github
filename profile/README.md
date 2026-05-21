## 🔍 What is Noir?

Noir is a SAST tool that reads source code and extracts the endpoints an application exposes — paths, methods, parameters, headers, cookies, and the source files behind them. Shadow APIs, deprecated routes, and undocumented handlers come out as part of the same inventory; they aren't a separate mode.

The inventory feeds three audiences:

- **Human reviewers.** Security engineers and code auditors get a focused list of attacker-reachable entrypoints — paths, parameters, source files, tags — instead of skimming the whole repo.
- **AI auditors.** LLM-based SAST agents get the same focused list, plus per-endpoint review context (`--include-callee` for 1-hop callees, `--ai-context` for guards, sinks, validators, and signals).
- **DAST tools.** ZAP, Burp Suite, and Caido get a real route list to scan, including paths they would never have reached by crawling.

![](https://github.com/user-attachments/assets/fa6b19fb-9a53-46fd-9622-a19223b362a2)

## 🚀 Key Features

- **Endpoint Extraction.** Static analysis across 50+ frameworks. Returns endpoints, parameters, headers, cookies, and the source files they came from.
- **LLM Fallback.** Hand unsupported frameworks (or one-off custom routing) to OpenAI / Ollama / etc. when static rules don't apply.
- **AI SAST Context.** The endpoint inventory is the focused context an LLM auditor needs to find attacker-reachable bugs. `--include-callee` attaches 1-hop callees; `--ai-context` adds aggregated review context per endpoint — guards, sinks, validators, and signals.
- **DAST Integration.** Pipe directly into ZAP, Burp Suite, or Caido as a proxy target, or export OpenAPI for them to import.
- **Multi-Format Output.** JSON, YAML, OpenAPI, SARIF, cURL, Postman, HTML, and more — whichever format the next tool in the pipeline reads.
- **CI/CD Ready.** GitHub Action, SARIF output, exit codes. Fits the pipeline you already have.

![noir-banner](https://github.com/user-attachments/assets/ffb689cd-a8f8-48a6-8073-43f1d98ec1f3)

![https://github.com/owasp-noir/noir/releases](https://img.shields.io/github/v/release/owasp-noir/noir?style=for-the-badge&color=black)
![](https://img.shields.io/github/stars/owasp-noir?style=for-the-badge)
![](https://img.shields.io/badge/Crystal-000000?style=for-the-badge&logo=crystal&logoColor=white)
