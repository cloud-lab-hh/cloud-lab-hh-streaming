# Nginx and HTTPS Setup

Nginx is used as the public entry point for the Cloud Lab HH Streaming project.

## Role of Nginx

Nginx acts as a reverse proxy in front of Icecast.

Icecast handles the actual live audio streaming, while Nginx provides a clean public HTTPS endpoint through the custom domain.

```text
Public Listener
    ↓
https://stream.cloud-lab-hh.de/live
    ↓
Nginx
    ↓
http://127.0.0.1:8000/live
    ↓
Icecast
