# Pumpkin – Unraid Template

[![Available on GitHub](https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@3/assets/cozy/available/github_vector.svg)](https://github.com/Pumpkin-MC/Pumpkin)
[![Website](https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@3/assets/cozy/documentation/website_vector.svg)](https://pumpkinmc.org/)
[![Issues](https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@3/assets/cozy/documentation/issues_vector.svg)](https://github.com/Pumpkin-MC/Pumpkin/issues)

Unraid Community Apps template for [**Pumpkin**](https://github.com/Pumpkin-MC/Pumpkin) — an experimental, high-performance Minecraft server (Java & Bedrock) written in Rust.

> ⚠️ **Experimental.** Not feature-complete; not for production. Keep world backups. Uses the `latest` image, so behavior can change often.

## Install

Search **PumpkinMC** in Community Apps, or add this template URL manually (**Docker → Add Container → Template**):

```
https://raw.githubusercontent.com/YoshiroMaximus/pumpkin-unraid-template/main/pumpkin.xml
```

## ⚠️ Permissions

The image runs as fixed UID `2613` (no `PUID`/`PGID`). Unraid appdata is `99:100`, so **before first start** run:

```bash
chown -R 2613:2613 /mnt/user/appdata/pumpkinmc
```
Otherwise the world/config won't save.

## Config

| Setting | Default |
| --- | --- |
| Data | `/mnt/user/appdata/pumpkinmc` → `/pumpkin` |
| Java port | `25565/tcp` |
| Bedrock port (optional) | `19132/udp` |
| `RUST_LOG` | `info` |

Tip: if Crafty (or another server) already uses `25565`, change the host port (e.g. `30000`).

## Links

[Project](https://pumpkinmc.org/) · [Source & issues](https://github.com/Pumpkin-MC/Pumpkin) · `ghcr.io/pumpkin-mc/pumpkin:latest`
