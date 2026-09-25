# Changelog

## edge

- Initial app repository scaffold: `repository.yaml`, `chore_tracker/` config,
  AppArmor profile, docs, and placeholder icon/logo.
- Points at `ghcr.io/luis-aparicio/chore-tracker:edge` with ingress on port 8080.
- `legacy: true` until a labeled GHCR image is published (then flip to `false`).
- `panel_admin: false` so non-admin members can use the sidebar panel.
- AppArmor expanded for Node (passwd/hosts/resolv, `/proc/self/**`, cgroup reads).
