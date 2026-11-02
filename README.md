# Matomo (LazyCat LPK)

Self-hosted, privacy-focused web analytics.

- Upstream: https://github.com/matomo-org/matomo
- Image: `library/matomo:5.14.2` (official Docker Hub image, mirror mode, digest-matched)
- License: GPL-3.0 (see `content/licenses/LICENSE` and `content/licenses/LEGALNOTICE`)
- Containers: app + MariaDB 10.11

## Notes

- Matomo requires MySQL/MariaDB; SQLite is not a supported installer backend, hence the sidecar.
- Configuration is passed through `MATOMO_DATABASE_*` environment variables, so the web
  installer only needs to run the schema and create the superuser — no seeded credential.
- `MATOMO_GENERAL_TRUSTED_HOSTS` is set to the app domain to avoid the "untrusted host" guard.
- Data on `/lzcapp/var/{db,html}`.
- No mail service configured.
- Not yet verified on a real device.
