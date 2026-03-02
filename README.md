# /reclaim-zkp — Claude Code Skill

A Claude Code skill that integrates [Reclaim Protocol](https://reclaimprotocol.org) ZKP verification into any existing app. No scaffolding, no UI generation — just the integration.

Type `/reclaim-zkp` in Claude Code, provide your credentials and pick a target file, and the SDK is wired up in seconds.

## What it does

1. Asks for your **APP_ID**, **APP_SECRET**, **PROVIDER_ID**, and **target file** (auto-detects candidates)
2. Validates credential formats
3. Stores credentials in `.env` (gitignored, never committed)
4. Installs `@reclaimprotocol/js-sdk`
5. Wires up the verification flow + proof parser into your chosen file
6. Proof results are parsed and returned as JSON

## Installation

```bash
# Clone into your project's Claude Code skills directory
git clone https://github.com/RealAdii/starkzap-reclaim-skill.git .claude/skills/reclaim-zkp
```

Restart Claude Code. The `/reclaim-zkp` command will now be available.

## Usage

1. Get your credentials from [dev.reclaimprotocol.org](https://dev.reclaimprotocol.org):
   - **APP_ID** (0x + 40 hex chars)
   - **APP_SECRET** (0x + 64 hex chars)
   - **PROVIDER_ID** (UUID)

2. In Claude Code, type:
   ```
   /reclaim-zkp
   ```

3. Paste your credentials and pick the file to integrate into.

4. Claude installs the SDK, adds the verification function, hooks it to a button, and you're done.

## Supported providers

Any provider available on [dev.reclaimprotocol.org](https://dev.reclaimprotocol.org) — Gmail, GitHub, Instagram, Twitter/X, LinkedIn, Steam, Spotify, Amazon, and more. See [PROVIDERS.md](reclaim-zkp/PROVIDERS.md) for details.

## Framework support

The skill adapts to whatever you're using — React, Vue, Svelte, Next.js, vanilla JS, etc. It reads your existing code and integrates accordingly.

## Security

- Credentials are stored in `.env` which is always gitignored
- `.env.example` is created with placeholder values for reference
- Real credentials are never written to source files — always read from env vars

## License

MIT
