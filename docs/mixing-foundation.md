# Mixing Foundation Workflow (Mastering.com method, adapted for Zizz)

Zizz follows the Mastering.com cheat-sheet approach. When running
`mixer-doctor`, `mastering-prep`, or any mix session, use these targets
and this order. Tool choices follow the three-option rule.

## Session prep (before mixing)

- Set tempo and time signature in the project.
- Create song section labels/locators (intro, groove, break, drop…).
- Raise audio buffer to 1024 samples while mixing (low CPU, latency
  doesn't matter at mix time).
- Import 1–2 reference tracks into the session, muted, for A/B checks.
- Add gain to any channel peaking below −30 dBFS so faders work in a
  useful range.

## Metering setup (stereo out)

- VU meter **calibrated to −18 dBFS** — Zizz owns MiniMeters VU or
  mvMeter2 (stock fallback: Live's meters are peak-only, so a
  third-party VU is justified here).
- Short-term **LUFS** meter — Youlean Loudness Meter 2 (or MiniMeters
  Loudness).
- True-peak readout — SPAN or the channel meter.

## Foundation order (the core of the method)

1. **Gain stage / volume mix.** Kick is the loudest element, true peak
   **≤ −5 dBFS**. Rough volume balance of everything relative to the
   kick, rough pans.
2. **Kick alone.** Mute everything else, shape the kick while holding
   the −5 dBFS peak.
3. **Add bass.** Balance the combined low end so the VU level sits at
   the genre target — for house/EDM that's the hot end of the VU scale
   (the Hip-Hop/EDM zone, roughly +1 to +3 VU on the −18 calibration).
4. **Add the snare/clap.** Transient peak around **−5 dBFS**, balanced
   against kick + bass.
5. **Limiter stress test.** With only kick, snare, bass active, put a
   limiter on the stereo out and push gain to **−9 to −11 short-term
   LUFS** (or match the reference). Listen for lost punch, depth, or
   distortion; fix the individual elements, then remove or reset the
   limiter and continue mixing on the solid foundation.
   Limiter: stock Limiter first; Pro-L 2 or KClip 3 if more control is
   needed.

If a track has no kick/snare/bass: find what carries the low end and
level it to the VU target, find the biggest transients and set them
near −5 dBFS true peak, then run the same stress test.

## Standing targets (also in audio-production skill)

- Working headroom on the master while mixing: −6 dB or more.
- Keep a muted reference in every mix session; A/B often at matched
  loudness.
- Source: Zizz's Mastering.com cheat-sheet binder (local PDF, not in
  repo).
