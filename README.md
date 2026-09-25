# Chore Tracker — Home Assistant apps

Home Assistant app repository for [Chore Tracker](https://github.com/luis-aparicio/chore-tracker).
The app runs the published multi-arch image `ghcr.io/luis-aparicio/chore-tracker`
(no Dockerfile here — see [ADR 0003](https://github.com/luis-aparicio/chore-tracker/blob/main/docs/adr/0003-single-image-deployment.md)).

**Licence:** [AGPL-3.0](LICENSE) — Copyright (c) 2026 Luis Aparicio.

## Add this repository

[![Open your Home Assistant instance and show the app store with a specific repository URL pre-filled.](https://my.home-assistant.io/badges/supervisor_store.svg)](https://my.home-assistant.io/redirect/supervisor_store/?repository_url=https%3A%2F%2Fgithub.com%2Fluis-aparicio%2Fchore-tracker-ha-apps)

Or: **Settings → Apps → App store → ⋮ → Repositories** and paste

`https://github.com/luis-aparicio/chore-tracker-ha-apps`

## Apps

### [Chore Tracker](./chore_tracker)

![Supports aarch64 Architecture][aarch64-shield]
![Supports amd64 Architecture][amd64-shield]

Household chore tracker with ingress panel (`mdi:checkbox-marked-outline`),
persistent `/data`, and Supervisor API access for later discovery work.

Configures the container with `CHORE_TRACKER_CONFIG=/data/options.json` so
Supervisor options (currently `logLevel`) feed the server's `loadConfig`.

Image tag tracked by `version` in `chore_tracker/config.yaml` (Phase 3: `edge`).

[aarch64-shield]: https://img.shields.io/badge/aarch64-yes-green.svg
[amd64-shield]: https://img.shields.io/badge/amd64-yes-green.svg
