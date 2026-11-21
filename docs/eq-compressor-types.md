# EQ & Compressor Types — plain-language cheat sheet (Zizz)

How to choose tools by TYPE, with Zizz's owned plugins per type.
Companion to docs/mixing-foundation.md. Keep advice consistent with
this taxonomy.

## EQ types

1. **Transparent (surgical)** — changes only what you touch, no color.
   For CUTTING problems (mud 200–400, resonances, HPF junk).
   Owned: EQ Eight (stock, daily), FabFilter Pro-Q 4 (deluxe; also
   Q2/Q3).
2. **Dynamic** — bands act only when the problem appears (loud-note
   harshness, booming single notes).
   Owned: TDR Nova, Pro-Q 4 dynamic bands, soothe2 (automatic
   harshness finder), Ozone 11 Dynamic EQ.
3. **Character ("tonal")** — EQ + pleasant circuit color, for POSITIVE
   moves. Three flavors ("pans"):
   - **Passive/tube, small (Pultec-style): Ozone 11 Vintage EQ** —
     boost + cut same low freq = bigger AND cleaner lows. Use on
     kick/bass/808; silky high boost too.
   - **Passive/tube, broad (Massive-Passive-style): NI Passive EQ** —
     4 huge smooth bands; warm/open a whole bus or master. Never
     surgery.
   - **Console (SSL-style): NI Solid EQ** — punchy, forward, angry
     boosts; drums/synths that sound too polite. (E = sharper,
     G = smoother curves.)
   - **Air band: Maag EQ2** — super-high shelf (10–40 kHz) = sheen
     without harshness; hats, claps, drum bus, master.
4. **Filters (creative)** — sweeps/motion, not correction.
   Owned: Auto Filter (stock), Volcano 3, Simplon, Filtron, Supermodal.

| Job | Type | Tool |
|---|---|---|
| Cut mud / fix | Transparent | EQ Eight, Pro-Q 4 |
| Problem comes & goes | Dynamic | Nova, Pro-Q 4, soothe2 |
| Kick/bass bigger & tighter | Pultec passive | Ozone 11 Vintage EQ |
| Warm/open a bus | Broad passive | NI Passive EQ |
| Punch & attitude | Console | NI Solid EQ |
| Sparkle on top | Air band | Maag EQ2 |
| Sweeps/motion | Filter | Auto Filter, Volcano 3 |

## Compressor types (robot hands)

1. **FET — lightning hand**, aggressive color. Drum energy, parallel
   crush. → **UAD 1176**.
2. **Opto — slow smooth hand** (light cell; can't react fast). Vocal &
   bass leveling, invisible. → **UAD LA-2A** (+ opto in UAD Century).
3. **VCA — precise hand.** Bus glue (SSL G) → **Glue Compressor
   (stock)**; drum snap (dbx 160 style) → **stock Compressor**
   hard-knee/fast (no exact dbx owned).
4. **Vari-mu — thick tube hand**, ratio grows with level. Mixbus
   density, 1–2 dB. → **RoyalCompressor**.
5. **Digital/clean — invisible hand.** Control without color.
   → **Pro-C 2**, stock Compressor.
6. **Multiband — one hand per band.** OTT (melodic-techno pad sound;
   Depth 20–30%), Pro-MB (surgical), Ozone Dynamics.
7. **Limiter — the wall.** Stress test, mastering ceiling. → stock
   Limiter, Pro-L 2, Ozone 11 Maximizer.
   (Clippers shave peaks instead: KClip 3, KNOCK, GClip, Mesa Lite.)

| Situation | Hand | Tool |
|---|---|---|
| Clap must smack | FET | UAD 1176 |
| Vocal/bass jumps around | Opto | UAD LA-2A |
| Drum bus = one kit | VCA bus | Glue 2:1, 1–2 dB |
| Huge dense pads | Multiband | OTT (gentle) |
| Clean control | Digital | Pro-C 2 |
| Thick finished bus | Vari-mu | RoyalCompressor |
| Ceiling | Limiter | Limiter / Pro-L 2 |

NI installs pending on the Mac (then rescan inventory): Solid EQ,
Passive EQ, Raum, Replika XT (optional: Solid Dynamics, VC 160).

## Saturation/distortion types (heat scale)

One idea: all of these add harmonics. Small = warm, big = destroyed.
Ask: "how much heat?"

1. **WARM — invisible thickness** (busses, refinement): HG-2 (king;
   Density = drive both tubes, level-compensated), UAD 610/Century
   (per-track preamp color), Saturation Knob, SDRR2 Tube,
   LittleRadiator. Stock: Saturator Soft Sine, low drive.
2. **HOT — audible character** (main mixing level): Saturator (stock
   workhorse, curve + drive), **Saturn 2 (multiband — saturate bass
   MIDS only, sub stays clean: the small-speaker trick)**, Fresh Air
   (highs-only exciter), FireCharger, RC-20/Vinyl (texture/lo-fi, not
   drive).
3. **BURNING — obvious distortion** (sound design): **Roar (stock
   flagship: 3 stages, serial/parallel/M-S/multiband routing, tunable
   feedback, built-in comp + modulation)**, Cyberdrive Core,
   Electrum/Bassment (amp sims), SausageFattener (cranked).

Cousins: clippers (KClip 3, KNOCK, GClip, Mesa Lite) = peak shaving,
a dynamics job; Redux = bitcrush.

| Situation | Tool |
|---|---|
| Drum bus analog weight | HG-2 (Density + Air) |
| Bass audible on phone, clean sub | Saturn 2 mids band (or Roar multiband, angrier) |
| One sound needs presence | Saturator |
| Growl / build-up / destruction | Roar |
| Vintage texture | RC-20, Vinyl |
| Dull top | Fresh Air (exciter) or Maag (EQ) |
| 2-bus final thickness | HG-2, barely on |

Discipline: count heat sources per signal path — one deliberate
saturator beats four accidental ones. HG-2 = "expensive", Saturator =
"present", Roar = "dangerous".
