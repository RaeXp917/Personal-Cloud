## Personal Cloud (Seafile + Cloudflare Tunnel)

Self-hosted cloud storage running on Windows 11 with Docker, fronted by a Cloudflare Tunnel for secure remote access.

## Stack

Docker Compose (Windows 11)

Seafile CE for file sync + web UI

MariaDB + Memcached for backend performance

Cloudflare Tunnel for HTTPS + domain access

Windows Scheduled Task for autostart

## Why

I wanted a private Dropbox-style cloud: fast file sync, web access anywhere, and no need to expose router ports.

## Architecture

Containers: seafile, mariadb, memcached

Cloudflare Tunnel → localhost:8080 (nginx in Seafile container)

Custom domain secured end-to-end with HTTPS

## Highlights

Secure: CSRF + proxy headers fixed in seahub_settings.py

Resilient: Auto-restart with restart: unless-stopped

Convenient: Autostart on login (docker compose up -d) via Windows Task Scheduler
