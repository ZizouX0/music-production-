# Return Tracks — Tech House / Minimal Deep Tech ("Get Stupid" reference, 130 BPM)

Genre note: Beatport files "Get Stupid" under Minimal / Deep Tech, but the
same return architecture serves tech house identically — only send amounts
shift. Tech house lean: clap send to A up a couple dB, vocal a bit more
present in A and C. Minimal lean: starve the sends, bassline dominates.

Four returns: A REV SHORT · B REV LONG · C DELAY · D CRUSH.
Throws are send automation into B and C, not a separate return.

Note values at 130 BPM: 1/4 = 462 ms · 1/8 = 231 ms · 1/16 = 115 ms ·
3/16 (dotted 8th) = 346 ms.

Universal rules:

1. Every reverb/delay on a return runs **100% wet** (the dry signal lives on
   the source track; passing dry here doubles and comb-filters it).
2. Chain order is always **EQ in → effect → EQ out → duck → Utility**.
3. Kick, bass, and hi-hats get **zero sends**. Dryness = closeness = punch.

---

## Return A — REV SHORT (placement / glue)

### Chain

**1. EQ Eight** (or Pro-Q 4)
- Band 1: high-pass, 250 Hz, 24 dB/oct — low-mids entering a reverb come out
  as pitchless mud that eats kick/bass headroom.
- Band 8: low-pass, 9 kHz, 12 dB/oct — keeps hat spill and vocal sibilance
  from turning the tail hissy. Gentle slope because we only want to darken,
  not dull.

**2. Valhalla Room** (stock: Hybrid Reverb, small room)
- Decay: **1.0 s** (range 0.8–1.2). At 130 BPM the tail is inaudible by the
  next 8th note — space without smear.
- Pre-delay: **15 ms** — separates the dry transient from the wet onset so
  claps keep their crack; below ~10 ms the verb "swallows" the attack.
- Size/Room: small–medium (~40%) — big size + short decay sounds unnatural.
- High Freq Damp: ~7 kHz — real rooms absorb highs; darker tail sits behind
  the source instead of on top.
- Mix: **100% wet**.
- Hybrid Reverb equivalents: small room IR or Quartz algorithm, decay 1.0 s,
  pre-delay 15 ms, Dry/Wet 100%.

**3. EQ Eight (post)**
- One bell, 450 Hz, −2 to −3 dB, Q ~1 — only if the tail sounds "boxy"
  (small-room algorithms resonate in the low mids). Bypass if it sounds fine.

**4. Compressor — sidechain duck** (or LFOTool)
- Sidechain: Audio From → Kick track, **Post FX**.
- Ratio 4:1 · Attack 0.1 ms (fastest) · Release **90 ms**.
- Threshold: pull down until **3–4 dB** of gain reduction per kick.
- Why 90 ms: kick ducks the tail, tail is fully back before the off-beat —
  you keep the space but the kick pocket stays clean.
- LFOTool version: one curve per 1/4 note, dip to ~40% at the kick, ramp back
  to 100% by 60% of the beat.

**5. Utility**
- Width **115%** — slightly wider than the sources so the "room" feels like
  it surrounds them. Gain = your master trim for the whole return.

### When to use it
Always on, whole track, never automated. It's scenery: it answers "where is
this sound standing," not "look at this effect." If you can name it in the
mix, the sends are too hot.

### Send what into it (starting send levels)
- Clap/snare: **−15 dB** — the main customer; makes samples sound performed.
- Rims / congas / perc one-shots: −20 dB — just enough to seat them.
- Main vocal & chops: −25 dB — a whisper; the vocal's real space is Return C.
- Synth stabs: −20 dB, only if they feel stiff.
- Never: kick, bass, hats.

---

## Return B — REV LONG (size / emotion)

### Chain

**1. EQ Eight** — high-pass 300 Hz, 24 dB/oct. Stricter than Return A
because a 3-second tail of low-mids is three seconds of mud.

**2. Valhalla VintageVerb** (stock: Hybrid Reverb, hall)
- Mode: Concert Hall · Color: **1970s** — the color modes darken and grain
  the tail; bright digital halls read "cheap trance," dark ones read
  "expensive warehouse."
- Decay: **3.0 s** (2.5–4 range).
- Pre-delay: **25 ms** — longer than Return A: this verb is *behind* the
  music, and more pre-delay pushes the wall further away.
- High Cut inside the verb: ~6 kHz.
- Bass Mult: **0.5× under ~200 Hz** — shortens low-frequency decay so the
  tail can't build a boom under a breakdown pad.
- Mix: 100% wet.
- Hybrid Reverb equivalents: Hall IR, decay 3 s, pre-delay 25 ms, Dry/Wet
  100%, EQ section high shelf down.

**3. EQ Eight (post)** — low-pass **6 kHz**, 12 dB/oct. Yes, on top of the
verb's own damping: two gentle slopes sound smoother than one steep one, and
this is your quick "darker/brighter" handle while mixing.

**4. Compressor duck** — same routing as Return A but **deeper: 5–6 dB** GR,
release **110 ms**. A long tail overlaps many kicks; deeper ducking is the
only way it can exist during a groove without flattening it.

**5. Utility** — width **130%**. The long verb is your "beyond the
speakers" layer; contrast against the mono bass is what creates depth.

### When to use it
Breakdowns and transitions — this is event gear, not scenery. During groove
sections it should be near-silent. The core move: lead/pad sends ride UP
through the breakdown, then get yanked to −∞ one bar before the drop. The
sudden dryness is what makes the drop hit like a wall.

### Send what into it
- Pads/atmosphere: main customer, −12 to −6 dB **in breakdowns only**.
- Lead/hook synth: automated as above.
- Clap/snare throw: one-hit send spike (−∞ → −6 dB → back) on the last hit
  before a section change, so it blooms across the transition.
- Vocal: last word of a phrase in the breakdown, via automation spike.
- Impacts/crashes: constant small send (−18 dB) is fine — they're events.
- Never: kick, bass, groove percussion, hats.

---

## Return C — DELAY (groove-space — the workhorse)

### Chain

**1. EQ Eight** — high-pass 300 Hz. Delayed low-mids are worse than reverb
mud: they repeat ON the grid, so they mask the bass rhythmically.

**2. EchoBoy** (stock: Echo)
- Mode: **Dual Echo** — L = **1/16**, R = **1/8**. Two different note values
  = repeats ping asymmetrically = groove, not a metronome.
- Feedback: **30%** — 2–4 audible repeats then gone. Past ~45% repeats pile
  into the next bar and blur the pocket.
- Style: **Master Tape**, saturation ~25% — each repeat gets slightly darker
  and grittier, so the tail recedes on its own like a real tape echo.
- High Cut ~7 kHz · Low Cut ~300 Hz (matches the EQ; belt and suspenders).
- Mix: 100% wet.
- Echo (stock) equivalents: Sync on, L 1/16, R 1/8, Channel Mode →
  **Ping Pong**, Feedback 30%, in-device filter HP 300 / LP 7 kHz,
  Dry/Wet 100%. (Echo's filter makes a separate Auto Filter unnecessary.)

**3. Auto Filter (optional)** — LP ~7 kHz. Only if repeats still poke over
the hats after step 2; dulling repeats beats lowering the send, because you
keep the rhythm and lose only the brightness.

**4. Compressor duck** — same as Return A: 4:1, fastest attack, ~90 ms
release, 3–4 dB GR. Non-negotiable here: un-ducked 16th repeats sit exactly
where the kick needs to breathe.

**5. Utility** — width **130%**. Wide repeats + mono bass = the classic
minimal stereo picture: the groove wraps around a rock-solid center.

### When to use it
Always available, whole track. This is your DEFAULT space — in this genre
reach for delay before either reverb. Order of operations when something
feels dry-in-a-bad-way: try Return C → then a whisper of A → B only if it's
a breakdown moment.

### Send what into it
- Vocal / vocal chops: **−15 to −10 dB** — the #1 customer; the "Get Stupid"
  vocal space is rhythmic repeats, not wash.
- Synth stabs/hooks: −18 dB — turns a static stab into a groove element.
- Perc accents (rim, zap): −20 dB.
- Throws: automate the source's send from −∞ to ~−3 dB on the last word of
  a phrase, snap back immediately — 3–4 repeats cascade into the next bar.
- Never: kick, bass. Hats: almost never (instant wash).

---

## Return D — CRUSH (parallel drum density — body, not space)

### Chain

**1. EQ Eight** — high-pass **100 Hz** (not 250 — you WANT drum body here,
just not sub rumble), low-pass 10 kHz.

**2. Glue Compressor** (yours: UAD 1176 all-buttons, or OTT at ~30% depth)
- Ratio **10:1** · Attack **0.3 ms** · Release **0.2 s or Auto**.
- Threshold: slam it — **8–12 dB** of gain reduction. On an insert this
  would murder the transients; in parallel the dry bus keeps the punch and
  this branch contributes only the between-hits sustain (ghost notes, room,
  hat texture) that reads as "density."
- Makeup: bring the crushed signal back to healthy level; final balance
  happens on the return fader.

**3. Saturator** (yours: Saturn 2)
- Curve: **Soft Sine** · Drive: **6–8 dB** · Dry/Wet 100%.
- Why after the compressor: compression raises the quiet gunk between hits;
  saturation converts that gunk into harmonic grit that glues the kit.
- Saturn 2 version: 2 bands split at ~200 Hz — Warm Tape on the low band,
  Warm Tube on the high band — so low-end saturation doesn't fuzz the top.

**4. Utility**
- Width: **0–60%** — unlike the space returns this layer must be
  centered/mono-ish, reinforcing the kit from the middle instead of
  smearing it sideways.
- No duck — it's made of drums; it already moves with the kick.

### When to use it
On during full-groove sections. Automate it down/off in breakdowns so the
drums come back denser than they left — cheap, effective impact trick.

### Send what into it
- **Drum bus only, one send.** Set the return fader so the crushed layer
  peaks **10–12 dB under** the dry drums. Blind test: mute/unmute — you
  should feel the drums lose weight, not hear an obvious second layer.
- Never: anything else. One customer keeps this layer coherent.

---

## Return E — SAT (parallel bass saturation — harmonics, not distortion)

### Why it exists
Sub must stay clean and mono, but clean sub is invisible on phones/laptops
(they can't reproduce 40–90 Hz). Saturation generates harmonics of the sub
(60 Hz → 120/180/240 Hz) and the ear reconstructs the missing fundamental.
Dry path = clean sub for the club; this parallel path = harmonics for small
speakers.

### Chain

**1. EQ Eight** — HP **150 Hz @ 48 dB/oct** (critical: no sub reaches the
saturator — this path is harmonics-only) · LP 5 kHz @ 24 dB/oct (keeps fizz
out of the vocal/hat range).

**2. Saturator** (yours: Saturn 2 Warm Tube, or Decapitator) — Medium Curve
· Drive **10–12 dB** · Soft Clip OFF · Output −10 dB · 100% wet ·
**Hi-Quality mode ON** (right-click title bar — oversampling prevents
aliasing at this drive).

**3. EQ Eight (post, bypass by default)** — bell 2–3 kHz, −2 to −4 dB, Q 1,
only if the layer barks over the vocal.

**4. Utility** — **Mono (width 0%)**. This layer reinforces the bass;
bass is center-mono, so its reinforcement is too.

No duck device: Live sends are post-fader/post-FX, so the copy already
carries the bass track's own sidechain pump. (Don't switch the send to
Pre-FX or the pump disappears.)

### Routing & dose
- Bass track/group only → send E starting at **−10 dB** (range −12 to −6).
- Raise until the bass steps forward in the drop, back off 2 dB.

### Calibration test
On a phone/laptop speaker: E muted = bassline nearly vanishes; unmuted =
groove and notes clearly audible. On monitors the difference stays subtle —
"more present," never "distorted."

### Return D & E build notes (Live specifics)
- Insert Return Track (right-click mixer area), rename, color.
- D routing: drum bus send at **0 dB**, balance on the **return fader**
  (~−10 to −12 dB) — cleaner gain into the chain, one obvious dose fader.
- D calibration: mute/unmute during the drop — drums should lose weight and
  glue, never reveal an audible second kit.
- Parallel rule of thumb: bus-level or multi-device parallel = return;
  single track + single device = just use the device's Dry/Wet knob
  (e.g. vocal NY compression: Compressor 8:1, fast attack, ~8 dB GR,
  Dry/Wet 30%, on the vocal track itself).

---

## Send-map summary

| Source | A REV SHORT | B REV LONG | C DELAY | D CRUSH |
|---|---|---|---|---|
| Kick | — | — | — | via drum bus |
| Bass | — | — | — | — |
| Hats/shakers | — | — | — | via drum bus |
| Clap/snare | −15 dB | throw spikes | — | via drum bus |
| Perc accents | −20 dB | — | −20 dB | via drum bus |
| Vocal | −25 dB | breakdown spikes | −15 to −10 dB | — |
| Stabs/hooks | −20 dB | — | −18 dB | — |
| Pads/leads | — | breakdown rides | small taste | — |
| FX/impacts | — | −18 dB | — | — |

Mix-order rule: **delay first, short verb second, long verb only for
moments.** If muting a return changes the mix in a way you can *name*, its
sends are too hot — you should only miss it vaguely.
