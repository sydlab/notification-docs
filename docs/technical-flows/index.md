# Technical flows (discovery)

This section holds **Mermaid** sources as `.mmd` files for the discovery phase. The site renders them on the linked pages below. You can still open the raw `.mmd` files in the repository, use [Mermaid CLI](https://github.com/mermaid-js/mermaid-cli), or paste into [mermaid.live](https://mermaid.live).

## Levels (working definition)

| Level | Intent | Typical diagram types |
|-------|--------|------------------------|
| **0** | System in its environment — actors and external systems | Context (e.g. C4 Context) |
| **1** | Major building blocks and responsibilities | Containers, high-level processes |
| **2** | Interactions and time order | Sequences, detailed processes, state |

Naming: use `kebab-case.mmd` and short prefixes such as `l0-`, `l1-`, `l2-` if you want sort order in file listings.

Each diagram uses **one directory** containing `index.md` and its `*.mmd` file. That way `[Mermaid source](slug.mmd)` resolves correctly when MkDocs publishes `slug/index.html` (directory URLs). Putting `slug.md` next to `slug.mmd` in a parent folder breaks those links; using `../slug.mmd` from `index.md` is not a fix here—MkDocs treats `..` as the parent of the **source** path and `mkdocs build --strict` will flag missing targets.

## Diagram index

- [Level 0 — system context](level-0/l0-system-context/index.md)
- [Level 1 — platform containers](level-1/l1-platform-containers/index.md)
- [Level 2 — onboarding sequence](level-2/l2-onboarding-sequence/index.md)
- [Level 2 — feed setup](level-2/l2-feed-setup/index.md)
- [Level 2 — login and register](level-2/l2-login-register/index.md)

## Cross-links to product docs

- [Partner onboarding](../partner-onboarding/index.md)
- [Notification setup](../notification-setup/index.md)
- [Login and register](../login-register/index.md)

## Next step (AWS)

When you are ready, add something like `docs/architecture/` or `docs/technical-flows/aws/` for EKS, Secrets Manager, Aurora PostgreSQL, and event-driven components, and reference those flows from level 1–2 diagrams.
