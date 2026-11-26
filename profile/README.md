Noir is a SAST tool that reads source code and lists the endpoints an application exposes: paths, methods, parameters, headers, cookies, and the source files behind them. Shadow APIs, deprecated routes, and undocumented handlers are in the same inventory.

The inventory has three readers:

- **Human reviewers** start from attacker-reachable entry points instead of the whole repo.
- **AI auditors** get the same list plus per-endpoint review context (`--include callee`, `--ai-context`).
- **DAST tools** (ZAP, Burp Suite, Caido, Gori) get routes a crawler would never reach.

![Source code, the endpoints Noir finds in it, and the same result as JSON](https://raw.githubusercontent.com/owasp-noir/noir/main/docs/content/get_started/overview/noir-usage.jpg)

## What Noir does

- **Endpoint extraction.** Static analysis across [264 frameworks](https://owasp-noir.github.io/noir/usage/supported/language_and_frameworks/).
- **LLM fallback.** OpenAI, Ollama, and other providers cover frameworks the static rules don't.
- **Output formats.** JSON, YAML, OpenAPI, SARIF, cURL, Postman, HTML, and more.
- **DAST integration.** Send endpoints to ZAP, Burp Suite, Caido, or Gori through a proxy, or export OpenAPI.
- **AI review context.** `--include callee` adds the functions each handler calls; `--ai-context` adds guards, sources, sinks, validators, and signals.
- **CI/CD.** GitHub Action, SARIF output, and exit codes.

## Get started

```bash
brew install noir
noir scan <source_dir>
```

Snap, Docker, npm, Nix and packages are on the [Installation](https://owasp-noir.github.io/noir/get_started/installation/) page.

## Repositories

| Repository | What it holds |
| --- | --- |
| [noir](https://github.com/owasp-noir/noir) | The scanner, its documentation and the GitHub Action |
| [noir-passive-rules](https://github.com/owasp-noir/noir-passive-rules) | Rules for the passive scan, which reports secrets left in source code |
| [alibi](https://github.com/owasp-noir/alibi) | Cross-checks the views of an attack surface and finds the endpoints that cannot corroborate each other |
| [noir-artwork](https://github.com/owasp-noir/noir-artwork) | Logos, wallpapers and Hak, the project mascot |
| [homebrew-noir](https://github.com/owasp-noir/homebrew-noir) | Homebrew tap |

## Contributing

Bug reports, framework requests and pull requests are welcome. Start with the [contributing guide](https://github.com/owasp-noir/noir/blob/main/.github/CONTRIBUTING.md), or pick a [good first issue](https://github.com/owasp-noir/noir/issues?q=is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22).
