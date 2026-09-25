# Chore Tracker (Home Assistant app)

Runs the same multi-arch image used for plain Docker installs
(`ghcr.io/luis-aparicio/chore-tracker`) under Home Assistant OS, with ingress
panel access and persistent storage on `/data`.

## Requirements

- Home Assistant OS (or Supervised) with the app store / Supervisor
- Architectures: `amd64`, `aarch64`
- Public pull access to `ghcr.io/luis-aparicio/chore-tracker` (tag matches
  `version` in `config.yaml`; Phase 3 tracks `edge`)

## Install

1. In Home Assistant: **Settings → Apps → App store → ⋮ → Repositories**
2. Add `https://github.com/luis-aparicio/chore-tracker-ha-apps`
3. Install **Chore Tracker**, start it, open the sidebar panel

Or use the My Home Assistant link from the repository README.

## Options

| Option | Default | Description |
|---|---|---|
| `logLevel` | `info` | Server log verbosity (`debug` / `info` / `warn` / `error`). Written to `/data/options.json` and loaded via `CHORE_TRACKER_CONFIG`. |

Other server settings use image defaults (`CHORE_TRACKER_DATA_DIR=/data`,
port `8080` for ingress). Environment variables still override the options file
inside the container if you set them.

## Persistence

SQLite and backups live under `/data` (Supervisor app data). Restarts and app
upgrades keep that volume. A cold backup of the app includes `/data`.

## Source and licence

- Application source: https://github.com/luis-aparicio/chore-tracker
- This packaging repo: https://github.com/luis-aparicio/chore-tracker-ha-apps
- Licence: AGPL-3.0 — Copyright (c) 2026 Luis Aparicio
