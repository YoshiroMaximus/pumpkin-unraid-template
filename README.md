# Pumpkin – Unraid Community Apps Template

An [Unraid](https://unraid.net/) Community Applications template for [**Pumpkin**](https://github.com/Pumpkin-MC/Pumpkin), a high-performance Minecraft server software written entirely in Rust, supporting both Java and Bedrock Edition clients.

## ⚠️ Experimental software

Pumpkin is under active development and is **not yet feature-complete**. It is not recommended for production worlds. Always keep backups of your world data. This template uses the `latest` image tag, which tracks the most recent release build, so compatibility may change often.

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
| Server Data | `/mnt/user/appdata/pumpkinmc` → `/pumpkin` | World data and config files. |
| Java Minecraft Port | `25565/tcp` | Java Edition server port. |
| Bedrock Port | `19132/udp` | Optional Bedrock port, only if enabled in `config.toml`. Not exposed by the image by default. |
| `RUST_LOG` | `info` | Log verbosity (`error`, `warn`, `info`, `debug`, `trace`). |

Configuration files (e.g. `config.toml`) are generated in the data folder on first launch and can be edited there.

### Port conflicts

If **Crafty Controller** or another Minecraft server is already installed, it may reserve port `25565`. In that case change the **host** port for "Java Minecraft Port" to something free (e.g. `30000`) to avoid a conflict.

## Permissions (important)

The Pumpkin image runs as a **fixed non-root user, UID/GID `2613:2613`** (baked into the image — it does **not** support `PUID`/`PGID`). Unraid's `appdata` share is normally owned by `99:100`, so on first launch Pumpkin may be unable to write its world data and config, and the server will fail to start or save.

Fix it once from the Unraid terminal **before** starting the container:

```bash
mkdir -p /mnt/user/appdata/pumpkinmc
chown -R 2613:2613 /mnt/user/appdata/pumpkinmc
```

## Security

The container runs with `--security-opt=no-new-privileges:true`, is not privileged, and runs as a non-root user.

## Links

- Pumpkin project: https://pumpkinmc.org/
- Source & issues: https://github.com/Pumpkin-MC/Pumpkin
- Container image: `ghcr.io/pumpkin-mc/pumpkin:latest`

## License

This template is provided under the terms in [LICENSE](LICENSE). Pumpkin itself is licensed by its respective authors.
