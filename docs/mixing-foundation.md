# Mixing Guide — Mastering.com method, full binder, adapted for Zizz

Source: Zizz's Mastering.com "Mixing & Mastering Cheat Sheet Binder"
(all 30 pages encoded 2026-10-20), adapted to Ableton Live 12, tech /
melodic house at ~120–126 BPM, stock-first per CLAUDE.md. Use this in
every mix session (`mixer-doctor`, `mastering-prep`).

## The roadmap (three parts)

**Part 1 — Building a Foundation:** initial assessment → gain staging →
low-end process → limiter stress test → loudness check-in.
**Part 2 — Mixing the Tracks:** lead balance → lead editing →
instrument balance → instrument editing → reference check-in.
**Part 3 — Finishing Touches:** spatial processing → assess transitions
→ assess the story → final referencing → bounce at −6 dBFS headroom
with no master limiter.

Rule of thumb throughout: **fix first, then enhance**, and **balance
before processing**.

## Part 0 — Organize the session (the 12 steps)

1. Arrange tracks by instrument, same order every project.
2. Label tracks clearly. 3. Color-code consistently (Zizz: drums /
bass / synths / vocals / FX groups).
4. Delete unused tracks; 5. hide keepers not in the mix.
6. Group instruments to busses (Drums, Bass, Synths, Vocals, FX) — one
fader per family.
7. Fades (~10 ms) on every audio clip edge.
8. **Gain stage: any channel peaking above −6 dBFS gets gain cut; any
below −30 dBFS gets gain added** (clip gain/Utility, not faders).
9. Tempo + time signature set. 10. Section locators (intro, groove,
break, drop, outro).
11. Buffer to 1024 while mixing.
12. Import reference tracks, muted, in-session.

## Metering (stereo out, last in chain)

- **mvMeter2, "VU Standard" preset** = VU @ −18 dBFS (verified preset).
- **Youlean Loudness Meter 2** = short-term LUFS + TRUE PEAK MAX
  (reset ✕ before each measurement pass; max holds until reset).
- Workflow: solo = calibration, context = decision.

## Part 1 — Foundation (kick → bass → clap → stress test)

1. **Kick alone:** shape it, set true peak **≤ −5 dBFS** (Youlean,
   fresh reset). The kick is the loudest element and never moves again.
2. **Add bass:** balance until combined low end rides the VU into the
   **0…+3 zone** (Hip-Hop/EDM bracket on the −18 cal). Tune bass to
   kick root, sidechain bass under kick (stock Compressor sidechain or
   ShaperBox volume curve), sub mono below ~120 Hz.
3. **Add clap/snare:** its own transient ≈ **−6 to −5 dBFS** measured
   solo (ceiling, not goal — clap sits under the kick's authority);
   re-check the summed peak on beats 2/4 stays ≈ −4 or lower.
4. **Limiter stress test:** kick+bass+clap only → stock Limiter (or
   Pro-L 2) on the stereo out → push to **−9 to −11 LUFS short-term**
   (or match reference). Listen for lost punch/distortion; watch
   Youlean PSR (healthy ≈ 9–10 LU; collapsed ≤ ~6 = squashed). Fix
   elements, re-test, then REMOVE the limiter and mix on.
- No kick/snare/bass in the track? Level whatever carries the low end
  to the VU target, set the biggest transients ≈ −5 TP, same test.

## Part 2 — Mixing the tracks

**Order:** lead element first (vocal or lead hook), then everything
else *around* it. Binder: tucked-in vocal starts 1–2 dB **below** the
snare/clap level; forward vocal 1–2 dB **above**. Instruments are the
environment for the lead — simplify overlapping arrangement roles
before reaching for EQ/compression.

**EQ — the 4 ways (stock EQ Eight first; Pro-Q 4 when dynamic/surgical
needed):**
1. *Remove the gross stuff:* narrow cuts on resonances (sweep a +boost
   bell, Q ≈ 1.5, find the nasty spot, cut it); HPF only when needed.
2. *Enhance the good stuff:* wide (Q 0.1–2.0) boosts/cuts, start ±3 dB.
3. *Make things different:* filter lows+highs, boost mids = megaphone
   etc.
4. *Create space:* cut in one instrument where another needs to live
   (e.g. cut synth 1–3 kHz where the lead/vocal sits).

**Frequency map (binder):** Sub 20–60 (rumble/deep) · Bass 60–200
(boom/full/punch ~100) · Low mids 200–500 (mud 200–400 / warm­th) ·
Mids 500–2k (boxy 500–800 / honky / full) · High mids 2–6k (presence,
edge, harsh — ear's danger zone) · Highs 6–20k (air, sibilance 5–10k,
brittle). HPF junk at 20–35 Hz. Low end = kick & bass each in their own
pocket (kick thump 40–60, bass above or below by arrangement).

**Compression — the 3 ways (stock Compressor / Glue first; LA-2A slow
color, 1176 fast aggression, Pro-C 2 clean):**
1. *Control dynamics:* faster attack+release, harder knee, higher
   ratio.
2. *Shape/color:* slower attack+release, soft knee, lower ratio
   (analog-style: LA-2A, 1176, Glue).
3. *Glue a bus:* medium attack/release/knee, low ratio (2:1), ~1–2 dB
   GR — Glue Compressor on Drums bus / mix bus.
   Mix-bus recipe (binder): ratio 3:1 → threshold to ~10 dB GR (to
   hear it) → attack 100 ms, release 5 ms → slow the attack down till
   transients dull, back off → lengthen release till it breathes with
   the song (GR returns to zero between hits) → raise threshold to
   final 1–2 dB GR → trim ratio to taste → makeup.

**Gate (stock Gate mirrors the binder):** reduction full down →
threshold where only the wanted sound opens → fast attack for perc /
slow for pads → hold+release long enough to sound natural → optional:
hysteresis (Live: "Return"), sidechain filters, lookahead, then raise
Reduction (floor) back up a little so it breathes. Ducker mode = lower
volume when ABOVE threshold (Live Gate has Flip for this).

**Transient shaping:** curve-based first for consistency (ShaperBox 3
Volume / Gatekeeper / LFOTool — deterministic, no detector wobble),
detector-based for feel (Drum Buss Transients, HelperTransients2, SPL
Attacker Plus, Trinity Shaper gently + Limit off while diagnosing).
Clipper after shaper pins peaks (KClip 3 / KNOCK / stock Saturator
clip).

**Panning (binder LCR, adapted to house):** kick, bass/808, lead
vocal, snare/clap dead center; mono low end; hats/percs/synth layers
hard L/R or halfway; one or two elements at half-pan to fill the
field. Keep stereo FX subtle on anchors — center focus comes from
vocals/kick/bass mono.

**Common problems table (binder, by element):**
- *Kick:* no low end → boost 40–60 Hz or saturate; not forward →
  transient shaper; too much sustain → gate/slow-attack comp; hollow →
  don't over-cut 150–250; dull → top-end EQ; too bright → roll highs +
  heavy slow comp.
- *Snare/clap:* thin → 250 Hz low mids; no snap → transient shaping or
  fast gate; buried → brightness/saturation upper mids; too far back →
  slow-attack comp then volume; dry → room/plate; wet → gate the tail.
- *Bass:* weak → EQ lows or sub-harmonic generator tuned to key; too
  much → gentle low shelf, don't over-filter; inconsistent → gain
  automation or compression; clashing kick → sidechain to kick; pumping
  limiter → lower volume or low-end content; not cutting → boost mids /
  saturate (RC-20, Saturn 2 on mids only).
- *Vocal/lead:* harsh → de-esser (Pro-DS) or 5–10 kHz dip; boxy →
  dynamic EQ 500–800 + short room; muddy → cut 200–400 in vocal AND
  competing tracks; uneven → serial compression (slow then fast) or
  automation; weak doubles → tighten timing/pitch, blend under lead.
- *Instrumental:* masking lead → carve 1–3 kHz + pan apart; dull/bright
  → tone with EQ/saturation not volume; weak transients → shaping or
  parallel comp; no center focus → anchors mono, stereo FX subtle;
  clutter → mute/filter non-essentials; clarity comes from subtraction.

## Part 3 — Finishing touches

**Two-bus room reverb (binder):** two returns —
*Ambience*: Room, decay 250–750 ms, pre-delay 2–25 ms, early > late
reflections, 100 % wet (pushes things back without being heard).
*Room Tone*: Room/Hall/Chamber, decay 500–3000 ms, pre-delay 0–75 ms,
late > early, 100 % wet (audible space).
Send each instrument to taste (more Ambience = further back; more Room
Tone = more obvious verb). **EQ before each reverb:** HPF up till thin
then back, shelf top for bright/dark, cut 3–10 dB low mids if muddy.
Level: returns from silence, up till nice, then back down 1–2 dB.
Zizz: stock Hybrid Reverb or ValhallaRoom (Ambience) /
ValhallaVintageVerb (Room Tone); tempo-synced Echo or EchoBoy dub
throws for transitions.

**Vocal/lead delay (binder):** return with stereo delay 100 % wet,
unlink L/R, one side 50–200 ms, other 20–50 ms behind, feedback
0–15 %; EQ before delay: HPF ≤ 300 Hz, LPF ≥ 3 kHz; level from
silence. **Vocal reverb:** plate (or room/hall), 100 % wet, start 4 s
decay then shorten to taste (vocals usually 0.5–1.5 s), pre-delay
30–100 ms until the vocal separates from the tail.

**Transitions & story:** automate levels/tone to steer attention;
contrast dry/wet, bright/dark, narrow/wide between sections; reverb
throws and rhythmic FX across section changes (Endless Smile, Eternal
Return, RVRSE for builds); re-establish hierarchy whenever everything
feels flat — the hook must lead. Mixing is emotional storytelling, not
just balance.

**Referencing (binder questions):** production (modern/old, live/
samples) · mix (balance, loudest element, automation) · frequencies
(spectrum shape on SPAN) · dynamics (locked vs breathing, punchy vs
thick) · space (wet/dry, tail lengths, what has audible verb). Use
REFERENCE plugin or muted in-session refs, level-matched.

**Bounce:** remove the master limiter, export with ~**−6 dBFS**
headroom (peaks). Mastering is a separate pass/session.

## Standing habits

- Master fader stays at 0; balance on tracks.
- Solo to calibrate, context to decide. One change at a time.
- Ear breaks; check mono (Utility) and at low volume.
- Mix in the arrangement, not an endless 8-bar loop.
