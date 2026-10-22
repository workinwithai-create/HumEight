# HumEight

**Hum it over your chords and get a DAW-ready line.** The melody is in your head and the DAW gets in the way. Type your BPM, key and 4 chords, put on headphones, and hum 8 bars over a real band. HumEight pitch-tracks the take in the browser (YIN), snaps it to your key and grid, and plays it back on a real flute or grand piano. You can export a WAV, plus a multi-track MIDI file that puts your line on its own track.

- Snap recipes: As sung (16ths), Clean 8ths, Chord-tone downbeats, Long notes. A held note stays one note. If you change the key after recording, the line moves with it.
- Input: pick a mic (audio input select, getUserMedia with echo cancellation, noise suppression and AGC turned off). You get a one-bar count-in, and the output and input latency are compensated, with a manual trim in ms. You can also load a voice-memo file, which is treated as starting at its first sound. Pitch tracking runs on your device and nothing is uploaded.
- Output: pick an audio output device. This uses `AudioContext.setSinkId` where the browser supports it. Otherwise sound goes to the system output, and the app says so.
- Web MIDI in/out with device select. You can play along live with velocity and sustain (CC64). Notes never start the transport. MIDI Start/Stop runs the transport only if you opt in. Computer keys and on-screen keys work as a fallback.
- Chairs: acoustic kit (Virtuosity Drums, CC0), plus upright bass, grand piano, string ensemble and flute (FluidR3 GM, CC BY 3.0, Frank Wen). Every semitone is sampled, so nothing is pitch-shifted (the engine caps shifts at ±4 st).
- Samples are on jsDelivr at pinned commits:
  - gleitz/midi-js-soundfonts@044fab8e1456bfafc5776e86dfd6bb8697149aef
  - sfzinstruments/virtuosity_drums@9f04cf9a734527edfbb0a4eee1f674e45bbf71bc
- Export: `humeight-<recipe>-<bpm>bpm-<key>.wav` is 48 kHz, 24-bit stereo. The downbeat is at sample 0 and the length is exact. The tail is folded back into the start, the peak is −1.1 dBFS, and compressor latency is removed. The matching `.mid` is format 1 with one track per chair, tempo and 4/4.
- Price: **$19 one-time** (Lemon Squeezy license key). The free demo has everything except WAV export, which is limited to 4 bars. Set up checkout in `LEMON` in `app.js` (`checkoutUrl`, `storeId`, `productId`). A key unlocks only when the store and product IDs match. While the config is empty, the Buy button reads "Checkout opening soon".

Code is MIT. The samples keep their own licenses.
