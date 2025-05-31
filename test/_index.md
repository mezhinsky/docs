---
title: Заголовок
---

**Test4**

```yaml
services:
  gramax:
    image: docker.io/gramax/docportal:latest
    platform: linux/amd64
    container_name: gramax
    restart: unless-stopped
    # ports:
    #   - ${PORT:-80}:${PORT:-80}
    environment:
      - PORT=${PORT:-80}
      - ADMIN_LOGIN=${ADMIN_LOGIN:-admin}
      - ADMIN_PASSWORD=${ADMIN_PASSWORD:-password}
      - AUTO_PULL_TOKEN=${AUTO_PULL_TOKEN:-}
      - AUTO_PULL_INTERVAL=${AUTO_PULL_INTERVAL:-}
    volumes:
      - ${ROOT_PATH:-./gramax}:/app/data
    networks:
      - reverse-proxy
networks:
  reverse-proxy:
    external: true
12
```