# nanobot-docker

Auto-built Docker image for [HKUDS/nanobot](https://github.com/HKUDS/nanobot), published to GitHub Container Registry.

## Image

```
ghcr.io/tio-27/nanobot:latest
```

Builds täglich via GitHub Actions. Wenn ein neuer upstream Release erkannt wird, wird das Image neu gebaut und gepusht.  
Kein eigener Code — reiner Build-Mirror vom offiziellen Dockerfile.

## Tags

| Tag | Beschreibung |
|-----|-------------|
| `latest` | Aktuellster upstream Release |
| `v0.1.x` | Gepinnter Release-Tag |

## Platforms

`linux/amd64` · `linux/arm64`

## docker-compose Beispiel

```yaml
services:
  nanobot:
    image: ghcr.io/tio-27/nanobot:latest
    container_name: nanobot
    restart: unless-stopped
    volumes:
      - ./config:/home/nanobot/.nanobot
    ports:
      - "18790:18790"
    command: gateway
```

## Upstream

- Repo: https://github.com/HKUDS/nanobot
- Docs: https://nanobot.wiki
