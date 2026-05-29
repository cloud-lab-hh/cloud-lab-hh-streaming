# Troubleshooting

This document collects issues, findings and planned checks from the Cloud Lab HH Streaming project.

## Crackling Audio

### Symptom

During earlier tests, the live stream had audible crackling and unstable audio quality.

### Findings

- A local QuickTime recording from the Focusrite Scarlett interface sounded clean.
- This indicated that the mixer and audio interface signal were probably not the root cause.
- Direct ffmpeg capture from the Scarlett interface was unstable during testing.
- Switching to BUTT as the streaming encoder removed the crackling.

### Current Solution

BUTT is currently used as the preferred encoder for the live stream.

## Stream Skipping / Buffering

### Symptom

The stream sometimes skips, jumps or buffers during playback.

### Possible Causes

- Icecast mount or listener buffer too low
- Player keeps an old or cached connection
- Network instability between local encoder and AWS server
- Bitrate too high for the available upload connection
- Temporary server resource spikes
- Mobile browser/player behavior on iPhone
- Encoder reconnects or unstable source connection

### Next Checks

- Test playback with VLC, browser and iPhone separately
- Restart the player session completely before testing
- Compare different bitrates: 128 kbps, 192 kbps and 320 kbps
- Check Icecast logs during skipping
- Check Nginx logs during playback
- Monitor CPU, RAM and network usage on the AWS server
- Review Icecast mount and burst-size settings
- Test a longer stream session with stable wired network if possible

## Encoder Stability

### Symptom

The quality and stability of the stream depends strongly on the encoder setup.

### Findings

- BUTT produced a cleaner result than earlier ffmpeg capture tests.
- The audio signal from the Scarlett interface itself appears to be clean.
- Encoder settings such as bitrate, codec and reconnect behavior are important for stable operation.

### Planned Actions

- Document final BUTT settings
- Add screenshots or notes for encoder configuration
- Define a default test profile
- Define a fallback profile with lower bitrate

## Lessons Learned

- Local audio quality should be tested separately before debugging the streaming server.
- A clean local recording helps separate audio-interface issues from network/streaming issues.
- Streaming problems can happen on several layers: encoder, network, Icecast, Nginx or player.
- A professional setup needs monitoring, logs and repeatable test steps.

