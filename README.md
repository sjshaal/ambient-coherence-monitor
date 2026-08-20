# Coherence Monitor

Body · Environment · Signal Field

**Live:** https://sjshaal.github.io/ambient-coherence-monitor/

A single-page app that reads heart rate and HRV from the camera (via remote photoplethysmography) and ambient sound characteristics from the microphone, then combines them into a coherence score.

No build step or server required — it's a static HTML/JS page. Camera and microphone access require a secure context (`https://` or `localhost`), which is why it's served via GitHub Pages rather than opened as a local file.
