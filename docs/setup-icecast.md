# Icecast Setup

Icecast is the central streaming server used in the Cloud Lab HH Streaming project.

## Role of Icecast

Icecast receives the encoded audio stream from the local encoder and distributes it to connected listeners.

```text
BUTT Encoder
    ↓
Icecast Server
    ↓
Listeners
