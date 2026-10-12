# FabFilter — verified plugin reference

Sources: official FabFilter online help (www.fabfilter.com/help/\<plugin\>, fetched 2026-10-12) and the official
Pro-C 2 PDF manual (fabfilter.com/downloads/pdf/help/ffproc2-manual.pdf). Every control description below comes
from those manuals; anything FabFilter's docs don't state is marked "(unverified)". Note: FabFilter's online help
now documents **Pro-C 3** — Zizz owns **Pro-C 2**, so that section is sourced from the archived Pro-C 2 PDF.

All FabFilter plugins share: four knob modes (vertical drag / rotate drag / mouse wheel / double-click text entry,
with entries like "1k", "A4", "2x" = +6 dB, "50%"), Ctrl/Cmd-click to reset, Shift for fine-tune, Alt to adjust
linked knobs together, MIDI Learn, undo/redo + A/B/copy, interface resizing + Full Screen mode, and a preset
browser with "Options > Save As Default".

---

## Pro-Q 4 (EQ)

**What it is**
FabFilter's flagship 24-band EQ with per-band dynamics, Spectral dynamics, EQ Match, and three analog-modelled
Character modes. The workhorse surgical/creative EQ for everything from kick-tuning to master-bus tilts; Zizz
also owns Pro-Q 2 and Q3 (see version note at the end of this section).

**Main controls**

*Band controls (per selected band, left to right):*
- **Bypass** — bypasses selected bands (Alt-click a dot does the same); bypassed bands dim, button glows red.
- **Shape** — 10 filter shapes: Bell, Low Shelf, Low Cut, High Shelf, High Cut, Notch, Band Pass, Tilt Shelf,
  Flat Tilt, All Pass (phase only). Ctrl+Alt-click a dot to change shape in the display.
- **Slope** — 0 to 96 dB/oct, fractional values allowed; Low Cut / High Cut also reach **Brickwall**.
  Minimum slopes: Bell/Notch 12 dB/oct; Low Cut, High Cut, Band Pass 0 dB/oct; other shapes 6 dB/oct.
- **Frequency** — 10 Hz to 30 kHz (multiple selected bands move in parallel).
- **Gain** — −30 to +30 dB (Bell, shelving and Flat Tilt shapes only).
- **Dynamic range ring** — −30 to +30 dB around the Gain knob; positive = expansion, negative = compression.
  Bell/shelving/Flat Tilt only. Yellow bar shows live dynamic gain change.
- **Q** — bandwidth; 1 = default width; disabled at 6 dB/oct; shelf Q is internally scaled vs other EQs.
- **Gain-Q interaction** — analog-style coupling (higher gain narrows Q slightly); Bell only; remembered per default.
- **Stereo placement** — which channels the band affects (L/R, M/S; extended speaker options in surround), plus a
  **Split** (scissors) button to split a band into L+R or M+S pairs.
- **Prev/next band, band number, Delete.**

*Dynamic EQ (per band):*
- **Auto mode** (default) — attack/release set automatically, threshold tracks the band-limited trigger level.
- **Expand (>>) panel** — manual **Threshold** slider (top position = Automatic "A", soft knee), **Attack** and
  **Release** knobs (50% center = auto-mode behavior; lower = faster), **Triggering**: *Band* (band's own
  frequency range) or *Free* (custom low/high-cut trigger range), **External side chain** toggle, and hold-to-hear
  **Audition** of the trigger signal.
- **Spectral button** — switches a dynamic band to **Spectral dynamics**: only the frequencies that actually
  exceed the threshold get processed. Extra controls: **Spectral Density** slider (lower = wider triggered
  ranges, higher = narrow/selective) and **Spectral Tilt** (3 dB/oct input tilt, on by default). Spectral bands
  always run linear-phase; Low/Medium Processing Resolution recommended.

*Global:*
- **Processing Mode** — **Zero Latency** (analog magnitude match, no latency, default choice), **Natural Phase**
  (matches analog magnitude *and* phase, most accurate), **Linear Phase** (magnitude only, adds latency; for
  phase-cancellation problem-solving). Linear Phase reveals **Processing Resolution**: Low 3072 smp (~70 ms) to
  Maximum 66560 smp (~1509 ms) at 44.1 kHz; dynamic EQ works up to High resolution only.
- **Character mode** — **Clean** (default, transparent), **Subtle** (subtle vintage-type saturation, program- and
  frequency-dependent), **Warm** (more apparent tube-like saturation).
- **Spectrum analyzer** — Pre / Post / SC-Ext sources (external = side chain or another Pro-Q 4 instance's
  post-EQ spectrum); Range 60/90 (default)/120 dB; Resolution Low 1024 → Maximum 8192 points; Speed (release);
  Tilt around 1 kHz (default 4.5 dB/oct); **Freeze**; **Show Collisions** (red glow where input and external
  spectrum may mask each other); **Spectrum Grab** (rest mouse on spectrum to grab and drag peaks directly).
- **EQ Match** — opens from the Instance list: pick a Reference (stored spectrum, input recording, another
  instance / side chain, or audio file), let spectrums average (~30 s), click **Match**, set matching detail
  with a slider (more bands = closer match), **Finish** to commit.
- **EQ Sketch** — draw the desired EQ curve in one go to set up initial EQing (per the official feature list).
- **Instance list** — view and control any other Pro-Q 4 instance in the session (per the official feature list).
- **Output options** — Global Bypass (latency-compensated, soft), Phase Invert, **Auto Gain** (estimated
  compensation, not measured), output level metering toggle, **Gain Scale** slider (scales all curve gains),
  **Output Gain** −∞ to +36 dB, Output Pan ring with L/R or M/S pan mode.
- Piano display, stereo options and full surround/Dolby Atmos support (documented on their own help pages).

**Use for house**
The default first insert on every bus: high-pass clutter at 20–30 Hz Brickwall on the master, dynamic bell at
the kick fundamental on the bass track (external side chain from the kick) instead of broadband sidechain
ducking, and Warm character on pads/stabs for free analog glue.

**Older versions owned:** Pro-Q 2 and Pro-Q 3. Vs Q3, Pro-Q 4 added (official list): Spectral dynamics, EQ Sketch,
the Instance list, Character modes, and copy/paste of bands/presets between instances. (Q3's own additions over
Q2 — per-band dynamic EQ etc. — unverified here; Pro-Q 2 presets load in Q4, but Q2 automation does not carry over.)

**Manual:** https://www.fabfilter.com/help/pro-q

---

## Pro-C 2 (compressor)

**What it is**
Program-dependent compressor with eight styles, full side-chain EQ section and M/S trigger options. Documented
here from the official Pro-C 2 PDF manual (FabFilter's online help now covers Pro-C 3, which Zizz does not own).

**Main controls**

*Dynamics:*
- **Style** — 8 algorithms: **Clean** (allround low-distortion feedforward, from v1), **Classic** (vintage
  feedback, very program-dependent, from v1), **Opto** (slow, very soft knee, from v1), **Vocal** (automatic
  knee/ratio, brings vocals to the front), **Mastering** (maximum transparency, minimal harmonic distortion),
  **Bus** (glue for drums/mixes), **Punch** (traditional analog-like behavior), **Pumping** (deep over-the-top
  pumping for drums/EDM).
- **Threshold** — down to −60 dB; circular side-chain level meter around the knob shows the detection signal.
- **Ratio** — 1:1 to ∞:1 (full right = limiting); dots on the knob jump to fixed ratios.
- **Knee** — 0 dB (hard) to 72 dB (soft); >60 dB knee + fast attack gives saturation-like compression.
- **Range** — 0 to 60 dB; caps the maximum applied gain change.
- **Audition Triggering** — hear where Pro-C 2 triggers and how much compression occurs.

*Time / output:*
- **Attack** — 0.005 ms to 250 ms, program-dependent.
- **Release** — program-dependent release models per style; **Auto Release** button adds smart gain-reduction-
  dependent release (Release knob then scales the auto behavior).
- **Lookahead** — 0–20 ms slider; globally enable/disable in the bottom bar for zero-latency work.
- **Hold** — 0–500 ms; prolongs gain-reduction peaks (longer holds = pumping effects).
- **Wet Gain (make-up)** — with pan ring for mid/side balance; **Auto Gain** applies estimated make-up from
  Threshold/Ratio/Knee/Attack (M/S-aware; it guesses, so still check output gain).
- **Dry Gain** — adds uncompressed signal for parallel compression.

*Side chain section (Expert button):*
- **In/Ext** trigger source; **Audition** (click or click-hold).
- **Side Chain Level** slider −36 to +36 dB.
- **Stereo Link** — 0% (unlinked) → 100% (fully linked) → beyond: mid-only / side-only processing, with
  **Stereo Link Mode**: Mid, Side, **M>S** (trigger on mid, compress side), **S>M** (trigger on side, compress mid).
- **Side chain EQ controller** — fixed low cut + high cut filters plus one customizable "Mid" band
  (Auto Mode bell by default; disable Auto for free frequency/gain/Q and shapes Bell, Low Shelf, High Shelf,
  Band Pass, Notch, Tilt).

*Global:* **Oversampling** Off/2x/4x; knee + level displays with meter scale 9–90 dB; input/output level/pan
knobs; **Mix** 0–200%; latency-compensated soft Global Bypass; MIDI triggering (Note On triggers compression).

**Use for house**
Bus style at 2:1, slow-ish attack / auto release on the drum bus for glue; Clean with side-chain EQ (low cut
~100 Hz) on vocals; for the classic kick-pump, external side chain from the kick + Pumping or Punch style —
though ShaperBox/LFOTool may stay cleaner for pure ducking.

**Manual (Pro-C 2 PDF):** https://www.fabfilter.com/downloads/pdf/help/ffproc2-manual.pdf
(online help is now Pro-C 3: https://www.fabfilter.com/help/pro-c)

---

## Pro-L 2 (limiter)

**What it is**
True-peak mastering limiter with eight algorithms, broadcast-grade loudness metering and up to 32x oversampling.
The last device on the master before export. Zizz also owns Pro-L 1 (see note).

**Main controls**
- **Gain slider** — the main control: raises level by adjusting limiting threshold and output gain together,
  respecting the output ceiling. Reverse-linked to Output Level (Alt-drag keeps apparent volume constant).
- **Style (Advanced panel)** — 8 algorithms: **Transparent** (close to original, rock/pop), **Punchy** (most
  audible, pumps when pushed; single tracks), **Dynamic** (enhances transients pre-limiting), **Allround**,
  **Aggressive** (near-clipping; EDM/trance), **Modern** (v2 default, transparent high loudness, near-zero
  lookahead possible), **Bus** (deliberately non-transparent glue/squash for drum buses), **Safe** (no
  distortion; delicate material). The last four (v2 additions) need more latency.
- **Lookahead** — look-ahead for the transient stage; shorter = louder but risks distortion; below 0.1 ms it
  approximates hard clipping (use oversampling + true peak there).
- **Attack** — how quickly the slower release stage engages.
- **Release** — how heavily the release stage acts (longer = more effect).
- **Channel linking** — separate **Transient** (often works well below 100%) and **Release** (start at 100%)
  link amounts; extended linking in surround.
- **Output Level** — the ceiling; factory presets at 0.0 dB; shown in dBTP when True Peak Limiting is on.
  Recommended: −1.0 dBTP streaming/EBU R128, −2.0 dBTP ATSC A/85, −0.1 dBTP CD/iTunes.
- **True Peak Limiting** — guarantees true-peak output never exceeds the ceiling.
- **Oversampling** — Off/4x/8x/16x/32x; 4x (or 8x) recommended for normal use, 16x/32x for offline renders;
  reduces aliasing and inter-sample peaks (slight linear-phase pre-ring, usually inaudible).
- **Dithering and noise shaping** — optional output dither to reduce quantization distortion (own help page).
- **Metering** — real-time level display (input, output, gain reduction, loudness); scales Loudness, K-12,
  K-14, K-20. **Loudness metering**: ITU-R BS.1770-4 (EBU R128 / ATSC A/85), targets −9 / −14 (streaming) /
  −23 / −24 LUFS or Custom; +9 or +18 LU scales; Momentary / Short Term / Integrated + LRA and Max M/S;
  true-peak readout; pause/reset + Auto-Reset on playback.
- **Output options** — Global Bypass; **Unity Gain** (output = inverse of Gain, for honest A/B); **Audition
  Limiting** (hear the delta/gain reduction only); **Filter DC Offset**; **Side Chain Triggering** (stem
  mastering: feed the unmastered master into the side chain so stems share its limiting).

**Use for house**
Modern style, True Peak on, 4x oversampling, ceiling −1.0 dBTP, aim ~−8 to −9 LUFS integrated for club masters
(−14 for streaming checks). Use Unity Gain while pushing the Gain slider so louder never fools you.

**Older version owned:** Pro-L 1. Pro-L 2 added (official list): true peak limiting, EBU R128/ITU-R BS.1770-4/
ATSC A/85 loudness metering, immersive/Atmos support, DC offset filter, external side-chain triggering,
Unity Gain, Audition Limiting — plus the Modern/Bus/Safe/Aggressive-generation styles (the four newer styles
are v2 additions per the help).

**Manual:** https://www.fabfilter.com/help/pro-l

---

## Pro-MB (multiband compressor/expander)

**What it is**
Multiband dynamics with up to six bands placed freely anywhere in the spectrum (not a fixed crossover bank),
upward/downward compression and expansion per band, and the unique zero-latency Dynamic Phase mode.

**Main controls**

*Display / workflow:*
- Create a band by clicking an empty display area (+ button, drag the yellow curve, or double-click). Bands
  only process where you put them; snap two bands together to share a crossover, snap to display edges for a
  traditional full-split. **Split**/**Unsnap** buttons appear on snapped crossovers. Per-crossover **slope**:
  6 to 48 dB/oct. Per-band solo/mute on hover; display range ±3/6/12/30 dB; draggable frequency scale zoom.

*Per band (basic):*
- **Threshold** — level where processing starts (circular side-chain meter around it).
- **Range** — limits maximum gain change; its **sign** picks the direction: Compress + negative Range =
  downward compression; Compress + positive = upward compression; Expand + negative = downward expansion /
  gating; Expand + positive = upward expansion.
- **Dynamics Mode** — Compress or Expand buttons.
- **Attack / Release** — 0–100% (program- and frequency-dependent curves, shown as percentages, not ms).
- **Ratio** — scales compression/expansion amount.
- **Knee** — hard to soft.
- **Lookahead** — up to 20 ms (global Lookahead Enabled button in the bottom bar).
- **Output Level** knob + **Output Pan** (mid/side) ring; band preset, bypass, delete buttons.

*Per band (Expert):*
- **Band/Free** triggering — trigger on the band's own range, or a freely chosen range elsewhere in the spectrum.
- **In/Ext** — internal or external side chain; **Audition** the trigger signal.
- **Stereo Link** — 0–100%, beyond 100% = mid-only or side-only processing (mode button).

*Global:*
- **Processing Mode** — **Dynamic Phase** (default: zero latency, no pre-ringing, phase changes only while gain
  actually changes — most transparent), **Linear Phase** (flat summed phase, accurate lows, more latency +
  possible pre-ringing), **Minimum Phase** (classic filters, no latency, static phase shifts at crossovers —
  avoidable with 6 dB/oct slopes).
- **Oversampling** — Off/2x/4x. **Mix** — global dry/wet 0–200%. Input & output level/pan; latency-compensated
  Global Bypass; full Pro-Q-style spectrum analyzer.

**Use for house**
One band 60–150 Hz on the bass bus, external side chain from the kick, Compress with −3 to −4 dB Range: the
low end ducks only where the kick lives. Also great as a de-harsher: a 2–5 kHz band on the master in Dynamic
Phase, fast attack, barely touching.

**Manual:** https://www.fabfilter.com/help/pro-mb

---

## Pro-G (gate/expander)

**What it is**
Gate and expander with six program-dependent algorithms, lookahead, full side-chain filtering and M/S expert
routing. Cleaner and far more tweakable than most console-style gates.

**Main controls**
- **Threshold** — level at which the gate/expander opens.
- **Ratio** — expansion amount below threshold (1:1 = none; above ~5:1 behaves like a gate).
- **Range (floor)** — caps maximum attenuation (e.g. 20 dB max reduction).
- **Style** — **Classic** (vintage channel-strip, drums), **Clean** (minimal flutter/distortion), **Vocal**
  (opens gently on breaths, cuts bleed), **Guitar** (follows natural decay, best 2:1–5:1), **Upward** (amplifies
  above threshold — upward expansion; avoid high ratio + low threshold), **Ducking** (inverted gating for
  voice-over ducking or pumping effects). All styles have built-in hysteresis (closes slightly below the
  opening level, so no chatter).
- **Attack / Release / Hold** — opening speed (very fast possible, program-dependent), closing speed, and
  minimum fully-open time.
- **Knee** — custom soft knee, visualized in the transfer curve.
- **Lookahead** — opens up to 10 ms early; with lookahead and oversampling off, Pro-G is zero-latency
  (10 ms latency when on).
- **Expert mode** — side chain **In/Ext** + **Audition**; side-chain **HP/LP filters** (48 dB/oct, bypassed at
  the extremes, Alt-drag moves both); per-channel trigger gain + pan rings (full stereo link, full unlink, or
  cross-link; mixes mid/side instead when Channel Mode is M/S); **Wet/Dry** output knobs for parallel use.
- **Oversampling**; MIDI Note trigger option; M/S channel mode.

**Use for house**
Ducking style = instant pump on pads/FX returns triggered from the kick via external side chain — a musical
alternative to sidechain compression. Upward style can push hat-loop ghost notes forward. Gate live percussion
loops with the HP side-chain filter so the kick bleed doesn't trigger it.

**Manual:** https://www.fabfilter.com/help/pro-g

---

## Pro-DS (de-esser)

**What it is**
Intelligent de-esser with a Single Vocal detection algorithm that splits sibilance from non-sibilance, plus an
Allround mode usable as a smooth high-frequency limiter on buses and full mixes.

**Main controls**
- **Threshold** — side-chain level above which de-essing triggers (down to −∞ dB); circular side-chain meter
  around the knob; **Audition Triggering** button to hear what triggers.
- **Range** — scales how much of the detected gain reduction is applied.
- **Side-chain HP/LP sliders** — 2 kHz to 20 kHz trigger range, with a built-in real-time spectrum analyzer
  highlighting strong frequencies; **Audition Sidechain** button below them.
- **Mode** — **Single Vocal** (sibilance-detection algorithm for one vocal) or **Allround** (triggers purely on
  the HP/LP range + threshold; for whole mixes/material).
- **Processing** — **Wide Band** (lowers overall gain; zero latency possible, often preferred on single vocals)
  or **Split Band** (attenuates only the highs; split frequency follows the HP filter setting; adds some latency).
- **Stereo Link** — 0–100%, beyond = mid-only / side-only processing (stereo version).
- **Lookahead** — up to 15 ms (≈10 ms typical on vocals); Lookahead Enabled button (off + wide band +
  no oversampling = zero latency; on = 15 ms latency).
- **Oversampling** — 2x/4x. External side-chain input selector; instance list; standard output options.

**Use for house**
Allround mode doubles as a hi-hat/cymbal tamer on the drum bus (set the HP around 6–8 kHz, gentle Range) and a
sparkle controller on white-noise risers; Single Vocal mode for any vocal chops before the reverb send.

**Manual:** https://www.fabfilter.com/help/pro-ds

---

## Pro-R 2 (reverb)

**What it is**
Algorithmic reverb built around musical "Space/Decay Rate" controls instead of engineering parameters, with
three algorithm styles, a Decay Rate EQ, a six-band Post EQ, ducking/gating, and impulse-response import that
converts IRs into algorithm settings. Zizz also owns Pro-R 1 (see note).

**Main controls**
- **Space** — room model + decay time in one knob: ~200 ms to 10 s across over a dozen room models.
- **Decay Rate** — scales decay 25% to 400% of the current Space.
- **Style** — **Modern** (the original Pro-R natural style), **Vintage** (early-digital character, strong on
  large spaces/long decays), **Plate** (fast build-up, metallic vintage plate).
- **Predelay** — delay before the tail; **Predelay Sync** Off/quarter/8th/16th/32nd with **Predelay Offset**
  50–200% (150% dotted, 67% triplet).
- **Character** — 0% transparent → 100% chorus-like; modulation increases above 50%; adds early reflections
  and late echoes.
- **Thickness** — density + subtle saturation/non-linearity; lower = sparser, airier.
- **Distance** — listener position: 0% close/bright early reflections → far = longer build-up, diffuse tail.
- **Brightness** — high-frequency absorption / clarity balance.
- **Stereo Width** — 0% mono → 100% fully independent channels (50% = max cross-feed); above 100% boosts side.
- **Ducking** — attenuates the reverb while input is active (triggered by the plug-in input) — vocal/lead clarity.
- **Auto Gate** — input-triggered gating with automatic threshold/attack/release; hold time by vertical drag,
  sync button for tempo-based hold.
- **Freeze** — infinite sustain of the current tank (toggle or momentary).
- **Decay Rate EQ** — up to 6 bands (Bell, Low/High Shelf, Notch) shaping *how long* each frequency rings
  (e.g. lows 200%, highs 50%); freq/decay-rate/Q per band.
- **Post EQ** — up to 6 bands (Bell, Low/High Shelf, Low/High Cut) on the reverb output, ±30/18/9 dB display,
  automatic reverb gain compensation, per-band stereo placement.
- **Mix** + **Lock Mix** (keeps Mix fixed while browsing presets — set 100% on sends).
- **IR import** — load a WAV/AIFF impulse response; Pro-R 2 approximates it with Decay Rate EQ/Post EQ/main
  settings (always Modern style); save as a normal preset. Spectrum analyzer; surround/Atmos up to 9.1.6.

**Use for house**
On the main reverb send: Style Vintage, medium room, predelay synced to a 16th, Decay Rate EQ cutting lows
below ~250 Hz to 50% so the tail never muddies the kick/bass, and Ducking for self-clearing vocal/lead space.

**Older version owned:** Pro-R 1. Pro-R 2 added (official list): Vintage and Plate algorithms, IR import,
Thickness/Ducking/Auto Gate, Freeze, immersive/Atmos up to 9.1.6, speaker options for EQ bands, M/S + L/R
Post EQ options, output metering and piano display.

**Manual:** https://www.fabfilter.com/help/pro-r

---

## Saturn 2 (saturation/distortion)

**What it is**
Multiband (up to 6 bands) saturation and distortion unit with 28+ styles from mastering-grade tube/tape to amps
and bit-crushing, per-band tone/dynamics/feedback, and FabFilter's full modulation system. Zizz also owns
Saturn 1 (see note).

**Main controls**

*Bands / display:*
- Click the **+** at the top of the display to split bands (up to 6); new band copies the split band's settings.
- Crossover **slope** 6/12/24/48 dB/oct; per-band **solo/mute** (hover top-left; Ctrl/Cmd-click = exclusive;
  hold = momentary).

*Per band:*
- **Style** — distortion type families: **Tube** (subtle/clean mastering to broken), **Tape** (subtle to
  extreme), **Amp** (American/British classics, modern smooth/crunchy/screaming), **Transformer** (subtle to
  lush), **Smudge** (smears/stretches audio), **Breakdown** (down-pitch + aggressive distortion), **Foldback**
  (aggressive digital clipping), **Rectify** (rectification + DC removal + soft clip), **Destroy** (bit-crush +
  sample-rate reduction + clipping).
- **Drive** — how hard the stage is driven; output auto-compensated for loudness; pan ring = per-channel drive.
- **Mix** — per-band dry/wet.
- **Feedback Amount / Feedback Frequency** — level and ringing pitch of the band's feedback loop
  (self-oscillating textures); **Unrestricted Feedback** option in the output panel allows endless
  self-oscillation.
- **Dynamics** — right = pumping compression, left = gating/expansion.
- **Tone** — Bass / Mid / Treble / Presence for the band's generated harmonics.
- **Level** — −∞ to +36 dB with pan ring (L/R or M/S); enable/bypass, band presets, delete.

*Modulation:*
- Sources: **XLFO** (16-step sequencer: per-step value/curve/glide/random, 0.02–500 Hz free or 16-bars–1/64
  synced, Balance ring, Legato/Retrigger), **Envelope Generator** (ADSR, audio- or MIDI-triggered), **Envelope
  Follower** (loudness/transient tracking), **MIDI source**, **XY controllers / sliders** (6). Drag a source's
  drag-button onto any knob; slots set modulation depth; almost every parameter is a target.

*Global:*
- **HQ (oversampling)** — Good = 8x, Superb = 32x. **Linear Phase** option for crossovers + oversampling
  filters. Channel Mode Stereo or Mid/Side. Input and Output level −36 to +36 dB with pan (all modulation
  targets). **Mix** slider. Latency-compensated Global Bypass.

**Use for house**
Subtle Tape or Tube on the drum bus (Drive low, Mix ~30%) for weight; 3-band trick on bass: keep the sub band
clean, drive 100 Hz–1 kHz with Tube, add Presence on top — mono-compatible grit without losing the sub. Modulate
Drive with an envelope follower for dynamic saturation.

**Older version owned:** Saturn 1. Saturn 2 added (official list): up to 6 bands with adjustable crossover
slopes, Linear Phase mode, Superb HQ, redesigned UI + modulation visualization, new amp/transformer/foldback/
breakdown and subtler tube/tape styles, EG curve slopes, band-input triggering, EF Transient mode, 6 XY
controllers, full resizing/Full Screen.

**Manual:** https://www.fabfilter.com/help/saturn

---

## Timeless 3 (delay)

**What it is**
Creative stereo delay with two delay lines (up to 16 taps), tape/stretch time behavior, six-filter section,
five built-in effects and the full FabFilter modulation system. Zizz also owns Timeless 2 (see note).

**Main controls**

*Delay:*
- **Delay Time** — free, or synced (becomes **Delay Offset**, 50–200% of the synced value; type "d"/"t" for
  dotted/triplet); **Tap** tempo on the DELAY label (free mode only).
- **Delay Time Pan ring** — lengthens one channel's delay up to 400% of base time.
- **Delay Read Mode** — **Tape** (vintage pitch swoops when time changes) or **Stretch** (constant pitch,
  time-stretched).
- **Feedback** — 0–200% (above 100% grows and drives internal saturation); **Feedback Pan** ring; **Cross
  Feedback Mix** slider (normal vs cross-channel feedback); per-channel **Feedback Invert** buttons.
- **Ping Pong** — with starting-channel choice; **Freeze** — loops current buffer at 100% feedback (modulatable).
- Up to **16 delay taps**, each controllable and modulatable, edited in the interactive delay display.

*Effects (left of delay controls, click center to enable, all modulatable):*
- **Drive** — input saturation; **Lo-Fi** — sample-rate + bit-depth reduction; **Diffuse** — blurs the buffer,
  big settings get reverb-like; **Dynamics** — right = pumping compression, left = gating; **Pitch** — ±1
  octave, with **Mirroring** (inverts shift in right channel — chorus tricks) and **Routing** (inside the
  feedback path = pitch spirals each repeat; outside = one-time shift). Pitch raises minimum delay 5 → 45 ms.

*Filters:*
- Up to **6 filters** in the feedback path (each repeat gets filtered again): analog-style self-oscillating
  LP/HP/BP with ~10 saturating styles ("Classic"… "Raw", "Tube", "Gentle") plus Clean EQ-type Bell/Shelf/Notch
  and Low/High Cut. **Routing**: Serial, Parallel, or Per-channel (odd filters = L, even = R). Freq/gain/Q/pan
  all modulatable.

*Output / modulation:*
- **Stereo Width**, **Wet Level** (+ pan ring), **Mix** + **Lock Mix**.
- Modulation: XLFO / EG / EF / MIDI / 6 XY-controllers-sliders, drag-and-drop slots (same system as Saturn 2).

**Use for house**
The dub-tech workhorse: 16th or dotted-8th sync, Feedback 60–80%, an LP filter ~2 kHz + HP ~300 Hz in the loop
so repeats darken and thin out musically, a touch of Diffuse, and Freeze mapped for live build-ups. Tape mode +
modulated delay time = instant analog echo wobble.

**Older version owned:** Timeless 2. Timeless 3 added (official list): redesigned UI, 16 modulatable taps,
ping-pong with start channel, Stereo Width, Mix slider, modulatable Freeze, 6 filters with EQ shapes and
6 dB slope, the five effects (Drive/Lo-Fi/Diffusion/Dynamics/Pitch Shift), EG curve slopes, EF Transient mode,
6 XY controllers, modulation visualization.

**Manual:** https://www.fabfilter.com/help/timeless

---

## Twin 3 (synth)

**What it is**
FabFilter's flagship subtractive synth: four oscillators, four analog-modelled self-oscillating filters, a
six-effect FX section, arpeggiator, and the drag-and-drop modulation system (up to 100 slots). Zizz also owns
Twin 2 (see note).

**Main controls**

*Oscillators (up to 4, + button to add):*
- **Waveforms (8):** Sawtooth, Square, Square Pure, Triangle, Triangle Pure, Sine, White noise, Pink noise.
- Per osc: Enable, **Pulse Width** (square shapes, modulatable), **Detune** ±1 octave (extra-sensitive near
  center), **Scale** (−1 to +3 octaves vs Master Tune), **Sync** (hard sync level; 1 = off), **Phase Sync**
  (reset phase on note-on), **Level/Pan**. **Ring modulation** between osc 1–2 and 3–4. Built-in analog drift.
- Global: **Master Tune**, octave Scale menu, **Portamento** + Legato mode.

*Filters (up to 4):*
- Analog-like, self-oscillating; shapes LP/HP/BP/Bell/Low-High Shelf/Notch; slopes 6/12/24/48 dB/oct;
  **11 styles**: FabFilter One, Smooth, Raw, Hard, Hollow, Extreme, Gentle, Tube, Metal, Easy Going, Clean.
- **Routing**: Serial, Parallel, or Per Oscillator (osc N → filter N). Per-filter frequency/peak/pan +
  global **Frequency Offset / Peak Offset** knobs moving all filters at once (classic "cutoff" macros).

*FX section (6 units, each with Amount knob + enable + per-effect presets):*
- **Reverb** (vintage style; Time 200 ms–20 s, Brightness, Predelay — modulating predelay = tape-style pitch),
  **Delay** (stereo, tempo sync, ping-pong, up to 4 multimode filters in the loop, feedback, time panning),
  **Chorus** (Single/Double mode, rate/depth/delay), **Phaser/Flanger** (rate/depth/feedback, flanger mode,
  L/R phase Shift), **Drive** (subtle saturation → amp distortion; routable pre/post FX chain), **Compressor**
  (threshold/attack/release, auto gain, metering — last in chain).

*Performance:*
- **Polyphony**: Mono / Poly (voice count up to 64) / **Per Oscillator** mode; **Unison** with **Spread**
  (detune + L-R panning, modulatable); last-note priority mono.
- **Microtuning**: MTS / MTS-ESP support, .tun file loading, reset; tuning-fork indicator.
- **Arpeggiator**: host tempo sync, groove/legato, transpose, note order, latch.
- **Modulation**: XLFO / EG / EF / MIDI / 6 XY controllers-sliders, up to 100 slots, source level −200% to
  +200%. **High Quality** mode = 4x oversampling. Side chain input usable as a modulation trigger.

**Use for house**
Strong candidate for rolling tech-house basses: one saw + one square an octave down, serial Raw or Tube filter,
EG → Frequency Offset for pluck, EF on the side-chain input (feed the kick) → filter cutoff for pump that
breathes with the groove. Unison + Spread for melodic-house super-pads.

**Older version owned:** Twin 2. Twin 3 added (official list): 4th oscillator + Per Oscillator mode, 4 filters
with bell/shelf/notch + 6 dB slope, the 6-effect FX section, arpeggiator, 64 voices (was 32), 100 mod slots,
preset browser with tags/search, HQ 4x oversampling, MTS microtuning, redesigned UI.

**Manual:** https://www.fabfilter.com/help/twin

---

## Volcano 3 (filter)

**What it is**
Characterful filter effect: up to four analog-modelled, self-oscillating multimode filters with eleven styles
and per-filter drive, routed serial/parallel/per-channel/M/S, driven by the full modulation system. Zizz also
owns Volcano 2 (see note).

**Main controls**
- **Filters** — up to 4, created by dragging the yellow curve or double-clicking the display (created/deleted
  in pairs in L/R and M/S modes).
- **Shapes** — Low/High Pass, Band Pass, Bell, Low/High Shelf, Notch, All Pass.
- **Slopes** — 6/12/24/48 dB/oct (6 dB not available for band pass/notch; slope = width for bell/shelf).
- **Styles (11)** — Classic (original FabFilter One), Smooth, Raw (heavy overdrive), Hard, Hollow (strong
  low-end self-oscillation), Extreme, Gentle, Tube (warm overdrive, great on synths), Metal, Easy Going
  (softer Tube), Clean (linear, no drive). Filters are non-linear even in bell/shelf shapes.
- Per filter: **Drive** (input grit), **Frequency** (+ pan ring = stereo balance of center frequency, stereo
  routing mode only), **Peak** (resonance; most styles self-oscillate at max; bipolar gain+resonance on
  bell/shelf), **Delay** (0–50 ms on the filter output — comb/Haas/chorus/flange tricks with parallel routing),
  **Output level/pan**, enable/bypass, delete.
- **Routing** — serial or parallel (options depend on filter count); **Routing mode** — Stereo, per-channel
  L/R, or Mid/Side (half the filters per channel in L/R and M/S).
- **Modulation** — XLFO / EG / EF / MIDI / 6 XY controllers-sliders, drag-and-drop slots; frequency, peak, pan,
  levels all targets.
- **Bottom bar** — **High Quality** (oversampling), **Auto Mute Self-Osc** (kills self-oscillation when input
  goes silent), Global Bypass, Input and Output level −36 to +36 dB with pan (modulation targets), **Mix**
  slider (phase cancellation possible when blending with dry).

**Use for house**
The filter-sweep machine for transitions: a 24 dB/oct Tube low-pass, XLFO synced to 8 bars on frequency, Peak
riding the edge of self-oscillation. M/S trick: filter only the sides for width automation on breakdowns.

**Older version owned:** Volcano 2. Volcano 3 added (official list): vintage EQ-type shapes (bell/shelf/notch/
all-pass), 6 dB slope, per-filter Drive and Level/Pan, improved sound, High Quality oversampling, spectrum
analyzer + piano display, modulation visualization, EG/EF/XY upgrades, 6 XY controllers.

**Manual:** https://www.fabfilter.com/help/volcano

---

## Simplon (basic filter)

**What it is**
The budget two-filter plug-in: two multimode filters with an interactive display — a quick, light filter for
simple duties, without Volcano's modulation engine.

**Main controls**
- **Two filters**, each with: **Frequency** 5 Hz–75 kHz; **Peak** (resonance, self-oscillates at max);
  **Response** Low Pass / High Pass / Band Pass; **Slope** 12/24/48 dB/oct; **Characteristic** (3 algorithms):
  FabFilter One (original synth character), Gentle (smoother/cleaner), Raw (strong overdrive); click-free
  per-filter enable/bypass.
- **Filter Routing** — serial or parallel.
- **Interactive filter display** — drag filters individually or together (Alt = both linked, Ctrl/Cmd+Alt =
  opposite directions).
- **Output options** — input gain, output gain, mix. MIDI Learn; presets; undo/redo.

**Use for house**
Disposable automation filter: drop on a loop, automate the display dot for quick HP/LP DJ-style sweeps when
Volcano 3 or Auto Filter would be overkill.

**Manual:** https://www.fabfilter.com/help/simplon

---

## Micro (micro filter)

**What it is**
FabFilter's smallest plug-in: a single 12 dB/oct filter with built-in envelope follower modulation — the fastest
route to an auto-wah / envelope-filter effect.

**Main controls**
- **Frequency** — cutoff across the entire audio range.
- **Peak** — resonance; warm character low, self-oscillation at maximum.
- **Response** — Low Pass or High Pass (always 12 dB/octave).
- **EF Level** — bipolar envelope-follower → frequency modulation amount (center = off; reset button above).
- **EF Speed** — follower response from fast/aggressive (left) to slow/smooth (right); EF light shows activity.
- **Input/output gain** options; MIDI Learn; presets; undo/redo.

**Use for house**
Instant envelope-filter squelch on percussion loops and funky top-loops — EF Level positive, medium speed — or
a dirt-cheap resonant HP on FX returns.

**Manual:** https://www.fabfilter.com/help/micro

---

## One (basic synth)

**What it is**
FabFilter's first synth: one oscillator, one legendary 12 dB/oct low-pass filter, envelope + modulation
generator. Deliberately minimal — the filter is the point.

**Main controls**
- **Oscillator** — waveforms Triangle, Sawtooth, Square (with PW/PWM), White noise; **Scale** in octaves
  (32' rich bass … 4' whistles); **Pitch** detune; **Portamento** (works polyphonically); **Noise** mix with
  white/pink Noise Type switch.
- **Filter** — 12 dB/oct low-pass; **Frequency** (0–10; ~10 = above 20 kHz); **Peak** (self-oscillates around
  position 8); cutoff modulated by **MG**, **EG** and keyboard velocity amounts.
- **Envelope generator** — Hold, Attack, Decay, Sustain (level), Release.
- **Modulation generator** — low-frequency square or triangle wave to oscillator pitch and/or filter cutoff.
- **Extras** — Mono or 10-voice polyphonic mode, PWM type choice, filter keyboard tracking amount, velocity →
  volume/cutoff amounts; MIDI Learn; presets.
- "How To Create" help section covers bass, lead, drum and FX recipes.

**Use for house**
Honest mono synth-bass and bleepy techno stabs: saw at 16', filter frequency ~3–4 with high Peak for ringing
subby tones. For anything bigger, reach for Twin 3.

**Manual:** https://www.fabfilter.com/help/one

---

## Quick-pick cheat sheet (house context)

| Job | First pick | Note |
|---|---|---|
| Surgical / dynamic EQ | Pro-Q 4 | dynamic band + external SC beats broadband ducking |
| Glue / vocal compression | Pro-C 2 | Bus style for buses, Clean + SC-EQ for vocals |
| Master limiting | Pro-L 2 | Modern, TP on, 4x OS, −1 dBTP |
| Multiband control | Pro-MB | Dynamic Phase, bands only where needed |
| Gating / pump | Pro-G | Ducking style = clean pump |
| De-ess / tame highs | Pro-DS | Allround mode works on buses too |
| Reverb | Pro-R 2 | Decay Rate EQ keeps lows short |
| Saturation | Saturn 2 | multiband: keep the sub clean |
| Delay | Timeless 3 | filters in the feedback loop |
| Synth | Twin 3 | EF on side chain → cutoff pump |
| Filter FX | Volcano 3 | Tube style + XLFO sweeps |
| Quick/light filter | Simplon / Micro | automation fodder |

Remember the three-option rule: Ableton stock (EQ Eight, Compressor, Glue, Limiter, Auto Filter, Echo, Hybrid
Reverb, Saturator, Gate) is offered first; these FabFilters are the step-2 upgrades when stock genuinely falls
short (dynamic/spectral EQ, true-peak loudness work, Dynamic Phase multiband, decay-rate-EQ reverb, etc.).
