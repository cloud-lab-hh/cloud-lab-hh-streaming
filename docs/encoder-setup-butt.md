# BUTT Encoder Setup

BUTT is used as the local streaming encoder for the Cloud Lab HH Streaming project.

## Role of BUTT

BUTT captures the audio signal from the local audio interface, encodes it into a compressed streaming format and sends it to the Icecast server.

```text
Xone:92 Mixer
    ↓
Focusrite Scarlett 4i4
    ↓
MacBook Pro
    ↓
BUTT Encoder
    ↓
Icecast Server on AWS
