# Signal Processing Lab

A local static web app for basic audio signal processing in the browser.

## Features

- upload local audio files
- formats accepted by the browser: WAV, MP3, OGG where supported
- no backend and no external API
- channel selection for multichannel audio:
  - left channel
  - right channel
  - mono / average of all channels
- audio information display:
  - sample rate
  - duration
  - sample count
  - detected channel count
  - selected channel
- explicit signal normalization to `[-1, 1]`
- responsive time-domain waveform chart
- FFT magnitude spectrum chart
- selectable FFT sizes:
  - 256
  - 512
  - 1024
  - 2048
  - 4096
  - 8192
  - 16384
- Hann window before FFT
- pure HTML, CSS, and JavaScript
- compatible with GitHub Pages

## Notes

The Web Audio API decodes audio into `Float32Array` channel data. These samples are generally already represented in the `[-1, 1]` range. The app still applies a clean normalization pass so display and FFT analysis use a predictable scale, including after mono channel averaging.

The FFT implementation is included directly in `index.html` and expects power-of-two FFT sizes.

## Run Locally

From the workspace root:

```bash
python3 -m http.server 8000 -d projects/signal-processing-lab
```

Then open:

```text
http://localhost:8000
```

You can use another port if `8000` is already in use:

```bash
python3 -m http.server 8010 -d projects/signal-processing-lab
```
