# Changelog

## edge

- Map container `8080/tcp` to host port **8124** by default for standalone LAN
  browser access (Chore Tracker login / invites; disable under Network for
  ingress-only).
- Declare `discovery: [chore_tracker]` so Supervisor accepts the app’s discovery POST
  (main repo #18). End-to-end zero-touch setup still needs the HACS integration.
- Initial app repository scaffold: `repository.yaml`, `chore_tracker/` config,
  AppArmor profile, docs, and placeholder icon/logo.
- Points at `ghcr.io/luis-aparicio/chore-tracker:edge` with ingress on port 8080.
- `legacy: true` until a labeled GHCR image is published (then flip to `false`).
- `panel_admin: false` so non-admin members can use the sidebar panel.
- AppArmor expanded for Node (passwd/hosts/resolv, `/proc/self/**`, cgroup reads).
