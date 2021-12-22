# Nginx-Letsencrypt Docker

An Nginx + Letsencrypt Docker container which self-sign the certificate and reverse-proxy to application.

## How to use:
To generate certificate each time (WARN: you can generate only 10 certificates in time span of 3 hours, check the [rate limit](https://letsencrypt.org/docs/rate-limits/) / IP):
```bash
docker run -e DOMAIN=domain.example.com -e EMAIL=email@example.com -p 80:80 -p 443:443 -d rodrigobaron/nginx-letsencrypt:1.15.5-alpine
```

To use existing certificates:
```bash
docker run -v /opt/certs:/etc/letsencrypt -e DOMAIN=domain.example.com -e EMAIL=email@example.com -p 80:80 -p 443:443 -d rodrigobaron/nginx-letsencrypt:1.15.5-alpine
```

To change nginx configuration:
```bash
docker run -v /opt/nginx-config:/etc/nginx/conf.d/ -e DOMAIN=domain.example.com -e EMAIL=emailexample.com -p 80:80 -p 443:443 -d rodrigobaron/nginx-letsencrypt:1.15.5-alpine
```

# Reference

This is an fork of [Ilhicas](https://github.com/Ilhicas/nginx-letsencrypt) work.
