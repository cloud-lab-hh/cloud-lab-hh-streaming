# Server Setup

This document describes the basic AWS/Linux server setup for the Cloud Lab HH Streaming project.

## Role of the Server

The server provides the cloud runtime environment for the streaming infrastructure.

It hosts the main backend components:

```text
AWS Lightsail / EC2
    ↓
Ubuntu Linux
    ↓
Icecast
    ↓
Nginx
    ↓
Public HTTPS stream endpoint

