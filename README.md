# caddy-mfa

Custom [caddy](https://caddyserver.com/) image with the [caddy-security](https://github.com/greenpau/caddy-security) plugin for authentication and MFA support.

## Image

```
docker pull sedyh/caddy-mfa
```

## What's included

| Component      | Version |
| -------------- | ------- |
| caddy          | 2.11.3  |
| caddy-security | 1.1.62  |

## Usage

```yaml
services:
  caddy:
    image: sedyh/caddy-mfa:2.11.3
    restart: unless-stopped
    ports:
      - "80:80"
      - "443:443"
    volumes:
      - ./conf:/etc/caddy
      - caddy_data:/data
      - caddy_config:/config

volumes:
  caddy_data:
  caddy_config:
```

Place your `Caddyfile` and any other configuration files inside the `conf/` directory.

## Build locally

```bash
docker build -f caddy.dockerfile -t caddy-mfa .
```
