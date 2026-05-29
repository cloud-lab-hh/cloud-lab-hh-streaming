# Architecture

## Overview

The streaming architecture uses a local audio encoder and a cloud-based Icecast server.

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

