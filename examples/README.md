# Examples

## `openlamp-midi-demo.mid` — a demo clip that drives WLED

A short MIDI clip that **emits OpenLamp MIDI** — colour looks, a brightness fade
(CC 1), a hue sweep (CC 3), a flash, and a blackout → restore. It's a plain Standard MIDI File,
so it works in **any DAW**. (Regenerate it with `python3 examples/gen-demo-mid.py`.)
This file was named `wled-midi-demo.mid` until 2026-09-20; only the name changed, the
notes and CC are byte-for-byte the same.

### Use it in Ableton Live (the "Ableton demo")

1. Run an OpenLamp MIDI implementation that opens a MIDI input — e.g. the [engine](https://github.com/openlamp/openlamp-engine-python)
   (virtual port **`OpenLamp`**), pointed at your WLED device(s).
2. In Live, create a **MIDI track**, drag `openlamp-midi-demo.mid` onto it.
3. Set the track's **MIDI To** → **`OpenLamp`** (the virtual port), channel 1.
4. Press play — the lamps run the showcase in time.

> A `.mid` rather than a `.als` on purpose: a MIDI file is stable and DAW-agnostic; an Ableton
> `.als` is a version-specific session that breaks easily. Drag this clip into a Live MIDI track
> and you have the same thing, in any DAW.

Same idea in **Logic / Reaper / Bitwig**: import the `.mid` on a MIDI track and route its output
to the `OpenLamp` port. On a **high-res-CC** setup (`highres_cc` in the engine), the fades are
step-free.
