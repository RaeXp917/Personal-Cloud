# Personal Cloud: Seafile + Cloudflare Tunnel

**Stack:** Docker (Windows 11), Seafile CE, MariaDB, Memcached, Cloudflare Tunnel, custom Windows Service / Scheduled Task.

## Why
Private “cloud vault” with fast file sync and web access from anywhere, without opening router ports.

## Architecture
- Docker Compose: `seafile`, `mariadb`, `memcached`
- Cloudflare Tunnel → `localhost:8080` (nginx in Seafile container)
- and a personal domain

## Highlights
- HTTPS end-to-end via Cloudflare
- CSRF / proxy headers fixed in `seahub_settings.py`
- Autostart: Scheduled Task runs `docker compose up -d` on login

## Redacted Config
See `docker-compose.yml.example` and `.env.example` for how to wire secrets safely.

## Notes
- Never commit real passwords/tokens.
- Use `.env` locally; keep it out of git (add to `.gitignore`).
# Personal-Cloud
