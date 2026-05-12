# Aleo Docs Source

Markdown and MDX source files for the Aleo documentation site. This repo contains the content only — the Docusaurus configuration, custom components, and build pipeline live in a separate repo that imports this one.

## Structure

```
aleo-docs-source/
├── learn/         # Conceptual documentation (What is Aleo, Core Concepts, Network, Advanced)
├── build/         # Developer documentation (Aleo Instructions, SDK, Wallet Adapter, Standards)
├── participate/   # User-facing guides (Wallets, Getting Tokens, Staking, Run a Node, Governance)
└── leo/           # Leo language documentation
```

## Component Dependencies

Some MDX files import custom React components from the config repo (e.g., `WalletEntry`). These files will not render standalone — they require the config repo to resolve the imports.

Currently used components:

| Component | Import Path | Used In |
|---|---|---|
| `WalletEntry` | `@site/src/components/WalletEntry` | `participate/wallets/`, `participate/funding/crosschain.mdx` |

If you add, rename, or change the props of a component in the config repo, check these files for breakage.

Pages that don't use custom components (most of `learn/` and `build/`) are pure MDX and have no dependency on the config repo.

## Contributing

See [Contributing](/participate/contributing.mdx) for guidelines on submitting changes to these docs.
