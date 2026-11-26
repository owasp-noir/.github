<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/owasp-noir/noir/main/docs/static/images/noir-dark.png" width="500">
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/owasp-noir/noir/main/docs/static/images/noir-light.png" width="500">
    <img alt="OWASP Noir" src="https://raw.githubusercontent.com/owasp-noir/noir/main/docs/static/images/noir-dark.png" width="500">
  </picture>
  <p>Hunt every Endpoint in your code, expose Shadow APIs, map the Attack Surface.</p>
</div>

<p align="center">
<a href="https://github.com/owasp-noir/noir/releases">
<img src="https://img.shields.io/github/v/release/owasp-noir/noir?style=for-the-badge&color=black&labelColor=black&logo=web"></a>
<a href="https://github.com/owasp-noir/noir">
<img src="https://img.shields.io/github/stars/owasp-noir/noir?style=for-the-badge&color=black&labelColor=black"></a>
<a href="https://crystal-lang.org">
<img src="https://img.shields.io/badge/Crystal-000000?style=for-the-badge&logo=crystal&logoColor=white"></a>
<a href="https://owasp.org/projects/noir">
<img src="https://img.shields.io/badge/OWASP-000000?style=for-the-badge&logo=owasp&logoColor=white"></a>
<a href="https://www.bestpractices.dev/projects/14203">
<img src="https://img.shields.io/badge/OpenSSF-Best%20Practices-000000?style=for-the-badge&labelColor=black"></a>
</p>

<p align="center">
  <a href="https://owasp-noir.github.io/noir/">Documentation</a> •
  <a href="https://owasp-noir.github.io/noir/get_started/installation/">Installation</a> •
  <a href="https://owasp-noir.github.io/noir/usage/github_action/">GitHub Action</a> •
  <a href="https://owasp.org/projects/noir">OWASP project page</a>
</p>

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
