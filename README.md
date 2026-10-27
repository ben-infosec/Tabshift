# TabShift — Guitar Tab Transposer (first prototype)

A self-contained, offline-first PWA prototype designed for Android. The core app uses plain HTML/CSS/JavaScript and does not require a server for transposition.

## Included in this first version
- Enter or paste text guitar tablature.
- Choose original and target keys.
- Transpose frets by key interval.
- Smart position mode searches strings/frets for the target pitch (standard tuning, up to fret 24).
- Same-string fret-shift mode.
- Save/load/delete songs in local browser storage.
- Export a transposed tab as `.txt`.
- Preview image uploads and open PDFs; load text files directly.
- Stage mode with larger tablature.
- PWA manifest and service worker for offline use after first load/install.

## Current limitations
- Photo/PDF import is preview-only. OCR and PDF tablature recognition are not yet implemented. This is intentionally stated in the app UI rather than pretending recognition works.
- Chord-name transposition, alternate tunings, capo handling, and detailed technique-aware parsing are future work.
- Smart position mode optimizes individual notes; it does not yet optimize an entire phrase for hand position or preserve every rhythmic alignment perfectly when fret numbers have different widths.
- Browser clipboard, PWA installation, and offline caching require serving over HTTPS or localhost (opening `index.html` directly does not enable service workers).

## Run locally
For a quick preview, open `index.html` in a browser. For PWA/offline installation, serve this folder from localhost or an HTTPS static host. Example from a computer with Python installed:

```bash
python -m http.server 8080
```

Then visit `http://localhost:8080` from that computer, or use an HTTPS host to install it on an Android device. A future native Android wrapper can package this interface and add on-device OCR (for example, ML Kit text recognition) plus a PDF page renderer.
