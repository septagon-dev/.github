# Septagon

Build the company before it needs saving.

Septagon builds software products and operating layers for teams that care about
leverage, boundaries and execution quality.

Our flagship is **PlatformKit**, a reference architecture for multi-tenant SaaS in
Go. The public repository is
[`septagon-oss/platformkit`](https://github.com/septagon-oss/platformkit): a small
kernel, business modules as plain packages, one server-rendered UI stack whose
screens derive from schemas, one binary with roles, ten gates on every pull
request. [`septagon-oss/platformkit-mobile`](https://github.com/septagon-oss/platformkit-mobile)
is its native shell.

This organisation holds what is private around it: the module catalog
(`platformkit-catalog`), client compositions and cluster state
(`septagon-clients`), secrets and operations. Repositories here that predate v1
are archived read-only and are not maintained.

## Start here

- [`septagon-oss/platformkit`](https://github.com/septagon-oss/platformkit) — read `ARCHITECTURE.md`, then run `scripts/start.sh`
- [Community discussions](https://github.com/septagon-dev/platformkit-community/discussions)
- [`septagon.dev`](https://septagon.dev)

Calm surface. Serious machinery underneath.
