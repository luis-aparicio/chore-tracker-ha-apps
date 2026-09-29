# Changelog

## sha-646ea4f

- Temporary pin to `ghcr.io/luis-aparicio/chore-tracker:sha-646ea4f` so HA OS
  can update past a cached `:edge` and pick up the Secure-cookie fix for HTTP.

## edge

- Default `CHORE_TRACKER_COOKIE_SECURE=false` (and `cookieSecure` option) so
  session cookies work on HTTP LAN port 8124 and HA ingress. Turn on only when
  serving the app over HTTPS.
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
