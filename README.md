# Pumpkin – Unraid Community Apps Template

An [Unraid](https://unraid.net/) Community Applications template for [**Pumpkin**](https://github.com/Pumpkin-MC/Pumpkin), a high-performance Minecraft server software written entirely in Rust.

## ⚠️ Experimental software

Pumpkin is under active development and is **not yet feature-complete**. It is not recommended for production worlds. Always keep backups of your world data. This template uses the `latest` image tag, which tracks the most recent release build.

## Installation

### Via Community Applications (once approved)

1. Install the **Community Applications** plugin on your Unraid server.
2. Go to the **Apps** tab and search for **PumpkinMC**.
3. Click **Install**, adjust the port and data path if needed, and **Apply**.

### Manual install (before CA approval)

1. In the Unraid web UI go to **Docker → Add Container**.
2. Set **Template** to the raw URL of this template:
   ```
   https://raw.githubusercontent.com/YoshiroMaximus/pumpkin-unraid-template/main/pumpkin.xml
   ```
3. Adjust settings and click **Apply**.

## Configuration

| Setting | Default | Description |
| --- | --- | --- |
| Minecraft Port | `25565` | Java Edition port (TCP). |
| Server Data | `/mnt/user/appdata/pumpkinmc` → `/pumpkin` | World data and config files. |
| `RUST_LOG` | `info` | Log verbosity (`error`, `warn`, `info`, `debug`, `trace`). |

Configuration files (e.g. `config.toml`) are generated in the data folder on first launch and can be edited there.

## Links

- Pumpkin project: https://pumpkinmc.org/
- Source & issues: https://github.com/Pumpkin-MC/Pumpkin
- Container image: `ghcr.io/pumpkin-mc/pumpkin:latest`

## License

This template is provided under the terms in [LICENSE](LICENSE). Pumpkin itself is licensed by its respective authors.
