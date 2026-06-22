# Pumpkin - Unraid Template

[![Unraid](https://img.shields.io/badge/Unraid-Community%20Apps-f15a2c?logo=unraid&logoColor=white)](https://unraid.net/community/apps)
[![Made with Rust](https://img.shields.io/badge/Made%20with-Rust-000000?logo=rust&logoColor=white)](https://www.rust-lang.org/)
[![Image](https://img.shields.io/badge/ghcr.io-pumpkin--mc%2Fpumpkin-2496ed?logo=docker&logoColor=white)](https://github.com/Pumpkin-MC/Pumpkin/pkgs/container/pumpkin)
[![License](https://img.shields.io/github/license/YoshiroMaximus/pumpkin-unraid-template)](LICENSE)

Unraid Community Apps template for [**Pumpkin**](https://github.com/Pumpkin-MC/Pumpkin) — an experimental, high-performance Minecraft server (Java & Bedrock) written in Rust.

> ⚠️ **Experimental.** Not feature-complete; not for production. Keep world backups. Uses the `latest` image, so behavior can change often.

## Install

Search **PumpkinMC** in Community Apps, or add this template URL manually (**Docker → Add Container → Template**):

```
https://raw.githubusercontent.com/YoshiroMaximus/pumpkin-unraid-template/main/pumpkin.xml
```

## Permissions

The image defaults to a fixed UID `2613` that can't write to Unraid appdata (`99:100`), which causes a `VanillaData::load` panic on first start. This template avoids that by running the container as `99:100` via `--user 99:100` in **Extra Parameters** — no manual `chown` needed.

If you already have a broken appdata folder from an earlier run, clean it once:

```bash
chown -R 99:100 /mnt/user/appdata/pumpkinmc
```

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
