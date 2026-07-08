# Drum Mix Guide — Tech House / Minimal ("Get Stupid" reference, 130 BPM)

Goal in one sentence: mixed drums in this genre = right volumes, cleaned
low-mids, bone dry, kick in the center — nothing fancy.

Vocabulary: **HP** (high-pass) = cuts everything below a frequency.
**GR** = dB of gain reduction on a compressor. **Send** = copy of a track
routed into a return (see `return-tracks-minimal-deep-tech.md`).

## Step 1 — Setup
1. Group all drum tracks (kick included) → `DRUMS`.
2. Reference track muted in the set (or in REFERENCE), level-matched —
   it should feel weak; that's correct.
3. Moderate fixed listening volume. Never mix loud.

## Step 2 — Volumes first (fixes 70% of "mix problems")
No plugins. Loop the drop.

| Track | Level | Feel |
|---|---|---|
| Kick | peaks ~−10 dBFS | the boss |
| Clap | −4 to −6 dB vs kick | clear second place |
| Open hat | −8 to −10 | drives the groove quietly |
| Percs | −8 to −12 | garnish answering the bass |
| Closed hats | −10 to −14 | background texture |
| Shaker/loop | −12 to −16 | only noticed when muted |

Test: listen through a door — hear only kick, clap, groove.

## Step 3 — Kick
1. Tune check: fundamental on the track's root note (Spectrum/Pro-Q piano).
2. EQ Eight (only the moves it needs): HP 30 Hz · weak → +1–2 dB at the
   fundamental (50–60 Hz) · boxy → −2–4 dB in 250–400 Hz · hollow → check
   600–700 Hz · invisible on phone → +2 dB at 3–5 kHz (the click).
3. Clip, don't compress: KClip3 or Saturator+SoftClip, shave 1–2 dB of
   peak. 4/4 sample = no dynamics to compress; clipping = sits louder.
4. Utility → Mono. Zero sends.

## Step 4 — Clap
1. Layered? Phz-Invert test on one layer, keep the fatter option
   (phase cancellation = the classic "small clap" cause).
2. EQ: HP 150 Hz · boxy → cut 400–600 · dull → +2 dB shelf 8 kHz+.
3. No compressor (single repeating sample).
4. Send → Return A at ~−15 dB (its room).

## Step 5 — Hats & shaker
1. HP hard: closed hats 300–500 Hz, shaker/loops 500 Hz.
2. Open hat must END before the next kick — fix with sample decay, not EQ.
3. Harsh → −2–3 dB in 3–5 kHz. Need presence → fader +1 dB, not a boost.
4. Groove = MIDI velocity contour (accent off-beats), never a compressor.
5. Pan: closed hats ~10% one side, shaker ~10–15% other, open hat center.
6. Sends: dry (max: shaker → C at −25).

## Step 6 — Percs
1. HP 150–250 Hz.
2. Bass wins ties: cut the perc 2–3 dB wherever it overlaps the bass's
   100–400 Hz growl.
3. Pan as call-and-response (L asks, R answers).
4. Send → Return C at −20 dB.

## Step 7 — Drum bus (the group)
1. EQ Eight: HP 25 Hz only.
2. Glue Compressor: 2:1 · attack 10–30 ms (slow = transients pass, only
   sustain squeezed) · release Auto · 1–2 dB GR. Denser reference → 4:1.
3. Group send → Return D (CRUSH) at 0 dB.
4. No limiter/clipper on the bus — it kills the pump.

## Step 8 — Verify
| Test | Pass |
|---|---|
| Reference A/B | as dry and forward as the reference |
| Mono flip | nothing vanishes |
| Phone speaker | kick click + clap + groove readable |
| Mute Return D | weight/glue disappears, never "a second kit" |

## Pro numbers worth memorizing (from research)
- Bass peaks 3–6 dB below kick on a PEAK meter but ≈ equal on
  LUFS short-term (check with Youlean/Insight).
- Master peaks ≤ −6 to −9 dBFS pre-master; mix ≈ −12 to −18 LUFS
  integrated; club master ≈ −8 LUFS.
- HP below ~100 Hz on everything except kick and bass.
- Sub <120 Hz mono, harmonics above may be stereo.

Three rules: ① faders before plugins ② HP everything except kick & bass
③ dry, mono-centered, hats quieter than you think — the kick and the gaps
do the talking.
