# Cloud Lab HH Streaming

Cloud Lab HH Streaming is a cloud-based live audio streaming lab built on AWS.

The project demonstrates how to operate a publicly reachable live audio stream using a Linux server, Icecast, Nginx, HTTPS, custom DNS and basic operational monitoring.

## Project Goals

- Build a reliable live audio streaming endpoint
- Use a custom domain with HTTPS
- Operate Icecast behind Nginx
- Document the full setup as an AWS/cloud portfolio project
- Add stream health checks and monitoring
- Extend the project with status pages and alerting

## Current Architecture

```text
Xone:92 Mixer
    ↓
Focusrite Scarlett 4i4
    ↓
MacBook Pro
    ↓
BUTT Encoder
    ↓
AWS Lightsail / EC2
    ↓
Icecast
    ↓
Nginx with HTTPS
    ↓
Public listeners

