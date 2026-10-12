# Valhalla & Soundtoys — verified plugin reference

**Sources:** official vendor documentation checked 2026-10-12 — valhalladsp.com product pages ("Learn"/documentation blog posts: "The Controls" / "The Modes" series, plus official GUI screenshots for control names; Valhalla plugins are otherwise self-documenting via in-plugin tooltips) and soundtoys.com product pages + official PDF manuals (EchoBoy v5, EchoBoy Jr. v5, Little AlterBoy v5, Little Radiator v5). SausageFattener verified from dadalife.com/plugins. Anything not confirmed by a vendor source is marked **(unverified)**.
**Not owned (do not recommend):** Soundtoys Sie-Q, Decapitator, Crystallizer, MicroShift, PrimalTap, SuperPlate, SpaceBlender — only EchoBoy, EchoBoy Jr., Little AlterBoy and Little Radiator are in the collection. Note: **SausageFattener is by Dada Life (made with Tailored Noise), not Soundtoys.**

---

## ValhallaVintageVerb

**What it is:** Valhalla's flagship "old-school digital" algorithmic reverb, inspired by the beloved hardware reverbs of the 1970s–80s (Lexicon 224/224XL, AMS RMX-16 era). 22 reverb modes and 3 color modes, current version 4.0.5. The single most-used reverb in melodic/tech house for pads, synths and vocals.

**Main controls** (names verified from official GUI; Valhalla documents full behavior via in-plugin tooltips):

- **MIX** — wet/dry (%); lockable for send use.
- **PREDELAY** (ms), **DECAY** (s) — the big central knob.
- **DAMPING: HighFreq** (Hz), **HighShelf** (dB), **BassFreq** (100 Hz–10 kHz, per official 4.0.5 changelog), **BassMult** (×) — frequency-dependent decay shaping (bass decay multiplier vs. mid decay, high-frequency damping).
- **SHAPE: Size** (%), **Attack** (%) — per official mode docs, Size scales the space (e.g. "crank up Size" in Smooth Plate) and Attack controls onset — in Ambience it balances early/late energy, in Nonlin it morphs truncated → gated → reverse.
- **DIFF: Early / Late** (%) — early and late diffusion.
- **MOD: Rate** (Hz) / **Depth** (%) — modulation of the reverb decay.
- **EQ: HighCut / LowCut** (Hz) — output filtering.
- **COLOR:** **1970s** (10 kHz bandwidth, internally downsampled, dark noisy modulation with random sidebands — intentional), **1980s** (full bandwidth, still funky modulation), **NOW** (clean, colorless). GUI colors change per era.
- **MODE** — 22 algorithms (all descriptions official): Concert Hall, Bright Hall, Plate, Room, Chamber, Random Space, Chorus Space, Ambience, Sanctuary, Dirty Hall, Dirty Plate, Smooth Plate, Smooth Room, Smooth Random, Nonlin, Chaotic Hall, Chaotic Chamber, Chaotic Neutral, Cathedral, Palace, Chamber1979, Hall1984.
  - Official guidance: **Dirty** modes = most faithful to late-70s/early-80s hardware, best for adding depth/character to synths; **Smooth** modes = modern Lexicon-style, best for "expensive" vocals and realistic rooms; **Chaotic** modes = tape-style wow/flutter modulation, best for longer synth verbs that still sit in the mix; **Palace** = room sounds of any size (small Size for drums, huge for vocal/synth washes); **Nonlin** = gated/reverse.

**Use for house:** First-call pad/synth reverb for melodic house — Concert Hall or Chaotic Hall (1980s color) on pads, Palace at small Size for drum rooms, Nonlin for gated snare/clap FX. Stock fallback: Hybrid Reverb.

**Manual:** https://valhalladsp.com/shop/reverb/valhalla-vintage-verb/ · modes: https://valhalladsp.com/2023/02/10/valhallavintageverb-the-modes/

---

## ValhallaRoom

**What it is:** A versatile true-stereo algorithmic reverb with twelve original algorithms, designed from a psychoacoustic perspective — it generates early and late acoustic energy for an "idealized" room impression rather than physically modeling a space. Range: tight ambiences and rooms through halls/plates to vast modulated spaces. Current version 2.0.5.

**Main controls** (all verified from official "High Level Sliders" / "Early Controls" / "Late Controls" posts + product page):

- **High-level sliders:** **MIX** (%), **PREDELAY** (ms), **DECAY** (RT60, mid-frequency, 0.1–100 s), **HIGH CUT** (−12 dB/oct lowpass; 3–7.5 kHz optimal for most rooms), **DEPTH** (balance Early↔Late reverb, 0% = all early, 100% = all late).
- **LO CUT** (new in 2.0.0) — reduces low-frequency content of the reverb output.
- **Early section:** Early Size (ms; >100 ms = gated sounds), Early Cross (stereo cross-mixing), Mod Rate / Mod Depth (early chorusing), Early Send (feeds Early into Late; 1.0 + small size = denser late reverb, 1.0 + big size = slow onset), Diffusion, **Space** (new in 2.0.0 — feedback around predelay/early reflections for diffuse echoes or early-only reverbs).
- **Late section:** Late Size, Late Cross (stereo coupling), Mod Rate / Mod Depth, **Bass Mult** (×, LF decay vs. DECAY), **Bass Xover** (Hz, 300–1500 typical), **High Mult** (×, HF decay), **High Xover** (Hz, 3–8 kHz typical).
- **MODE** — 12 algorithms (official descriptions): Large Room, Medium Room, Bright Room, Large Chamber, Dark Room (lo-fi, <11 kHz, low CPU), Dark Chamber, Dark Space, Nostromo (biggest, sparse slow build), Narcissus (lightest CPU), Sulaco (very dark), LV-426 (dark + dense + slow attack), Dense Room ("great for snare drums!" — official).

**Use for house:** The realistic-space tool — short Dense Room / Large Room decays (0.3–0.8 s) to glue drums and give percussion a room; Bass Mult < 1× keeps the low end clean under a 4/4 kick. Stock fallback: Hybrid Reverb or Reverb.

**Manual:** https://valhalladsp.com/shop/reverb/valhalla-room/ · controls: https://valhalladsp.com/2011/05/02/valhallaroom-the-high-level-sliders/

---

## ValhallaPlate

**What it is:** Valhalla's algorithmic take on classic steel-plate reverb (EMT140-style — one mode was tuned against the specific EMT140 at Avast Recording, Seattle). Twelve algorithms emulating real plate sound and behavior: instant onset, instant high echo density, dispersion, and complex frequency-dependent decay — then pushed beyond what physical plates can do.

**Main controls** (names verified from official GUI): **MIX** (%), **PREDELAY** (ms), **DECAY** (s), **SIZE** (% — up to 200%+, where some modes turn chamber-like per official mode notes), **WIDTH** (%), **EQ: LowFreq / HighFreq** (Hz) + **LowGain / HighGain** (dB), **MOD: Rate** (Hz) / **Depth** (%), **MODE**, presets.

- **MODE** — 12 algorithms (official descriptions): **Chrome** (neutral starting point), **Steel** (like Chrome, darker), **Brass** (sharp attack, bright), **Cobalt** (deep attack, dark, EMT140 low-mid resonance), **Adamantium / Titanium / Osmium** (mono-in stereo-out; airy / darker / dark with booming low end), **Aluminum** (much higher modal density, bright; chamber-like >100% Size), **Copper** (dense, deep and dark — "works on almost any source"), **Unobtanium** (dense, bright, long HF decay — "turn up modulation… perfect reverb for synths"), **Radium** (dual-mono plate hybrid preserving stereo image), **Lithium** (lush stereo-chamber/plate hybrid preserving input panning).

**Use for house:** Classic vocal and clap/snare plate — Chrome or Copper, 1–2 s decay, predelay 20–30 ms; Unobtanium + modulation for synth-lead sheen. Stock fallback: Hybrid Reverb (plate IRs) or Reverb.

**Manual:** https://valhalladsp.com/shop/reverb/valhalla-plate/ · modes: https://valhalladsp.com/2015/11/08/valhallaplate-the-reverb-modes/

---

## ValhallaShimmer

**What it is:** The pitch-shifting reverb — built for BIG ethereal sounds, with a pitch shifter inside the reverb feedback loop. Shift +12 semitones with Feedback ≥ 0.5 reproduces the classic Eno/Lanois "shimmer" sound (official recipe). Also does spring-like, reverse-ish, and conventional huge reverbs.

**Main controls** (all verified from official "The Controls" post):

- **Mix** — power-complementary wet/dry.
- **Pitch** — shift amount in the feedback loop, −12 to +12 semitones.
- **Feedback** — around the diffusor/pitch-shifter network; pitch shifting only audible with Feedback > 0.
- **Diffusion** — 0 = straight delay; 0.5–0.618 = slow fade-in reverb; 0.9 = long decay even with zero Feedback.
- **Size** — delay lengths = room size; larger Size also lengthens decay.
- **Low Cut / High Cut** (Hz) — in the feedback path, so the tilt compounds as the tail decays.
- **Mod Rate** (Hz) / **Mod Depth**.
- **Reverb Mode:** Mono (huge, mono-in/stereo-out), Big Stereo (cathedral-scale), Medium Stereo (best for traditional halls and fast-building shimmer), Small Stereo (small rooms, chorused ambiences).
- **Pitch Mode:** Single (classic Eno/Lanois, orchestral), Dual (up+down in parallel, symphonic), SingleReverse (reversed grains, smoother/organ-like), DualReverse (pipe-organ), Bypass (normal reverb).
- **Color Mode:** Bright (full-bandwidth, modern) / Dark (steep HF loss above ~10 kHz, 70s/80s digital character).

**Use for house:** Breakdown weapon — +12 Single shimmer on a sustained pad or vocal phrase for lift into a drop; Bypass pitch mode + Big Stereo is a free massive hall. Stock fallback: Hybrid Reverb + Shifter in the feedback (or Echo's pitch), far more work.

**Manual:** https://valhalladsp.com/shop/reverb/valhalla-shimmer/ · controls: https://valhalladsp.com/2010/11/27/valhallashimmer-the-controls/

---

## ValhallaDelay

**What it is:** Valhalla's take on classic and modern delay/echo units — tape, BBD, old-school digital, pitch shifting — expanded with Ratio/Quad styles, the frequency-shifting Ghost mode, and a diffusion section that turns any mode into smeared echoes or a full reverb. Delay range <1 ms to 20 s. Current version 3.0.5 (17 modes).

**Main controls** (all verified from official "The Controls" post; visible controls depend on Mode + Style):

- **MIX** (%; lockable), **DELAY** (ms or beat-synced: notes/dotted/triplet; DELAY L/R in Dual & Ping Pong; SPREAD offset in Single; RATIO in Ratio style — 61.8% = "Golden Ratio" pseudo-reverb), **FEEDBACK** (up to 200% for self-oscillation), **WIDTH** (100% stereo / 0% mono-summed / −100% swapped).
- **ERA** — Past/Present/Future variations of each mode (filters, saturation, diffusion behavior).
- **COLOR: Drive** (dB, level-compensated saturation) and **Age** (mode-dependent: tape asperity noise & splice artifacts, BBD chip noise, bit depth on Digital/Pitch modes).
- **DIFF: Amount** (off → 68% equal fade → 91% reverb-from-diffusion-alone) and **Size** (% of delay length; small = blurred attack, large = reverb).
- **MOD:** Wow & Flutter depths (Tape mode) or Rate/Depth (HiFi/BBD/Digital); **FREQ Shift/Detune** (Ghost, Hz); **PITCH Shift/Detune** (Pitch/RevPitch, semitones/cents).
- **EQ High / EQ Low** (Hz) — cut filters in the delay feedback path.
- **STYLE:** Single, Dual, Ratio, Ping Pong, Quad (multi-head tape emulation: Tap A/B/C/D, SPACING, REPEAT/SWELL).
- **MODE** — 17 algorithms (official): Tape (RE-201/RE-301 model), HiFi, BBD, Digital, Ghost (freq-shift + diffusion), Pitch, Reverse Pitch, BBD Duck, Clarity, DuckTape, PitchDuck, LoFi, Quartz (colorless/transparent), Phaser DDL, RichPitch, Chrome Tape (3.0, cleaner Tape), Analog (3.0, modern BBD — officially "a PERFECT frequency balance for delays, choruses, and reverbs"). The Duck modes have a 1-knob ducking control that tracks input level.

**Use for house:** The main dub/echo box — Tape or Analog mode, Ping Pong style, 1/8-dotted sync on stabs and vocals; Duck modes keep repeats out of the way of the groove automatically; DIFF high for instant ambient washes in breakdowns. Stock fallback: Echo (closest), Delay.

**Manual:** https://valhalladsp.com/shop/delay/valhalladelay/ · controls: https://valhalladsp.com/2019/04/16/valhalladelay-the-controls/

---

## ValhallaSupermassive (free)

**What it is:** Free reverb/delay built on feedback delay networks with delays up to 2 s each — "luscious clouds of reverb, otherworldly delays, swelling waves of feedback." 22 celestial-named modes, current version 5.0.0 (Sirius, Nov 2025).

**Main controls** (all descriptions official, from the product page):

- **MIX** (%; lockable for sends), **WIDTH** (100% → 0% mono → −100% reverses L/R spin).
- **DELAY** (ms or tempo-synced) — length of the longest delay line.
- **WARP** — scales the other delay lengths relative to DELAY: simple echoes → resonant/smeared repeats → lush reverbs.
- **FEEDBACK** — decay length (also affects attack time in some modes).
- **DENSITY** — perceived number of echoes.
- **MOD Rate** (Hz) / **MOD Depth** — multi-phase sinusoidal chorusing; depth auto-scales with rate.
- **EQ High Cut / Low Cut** — −6 dB/oct output filters (in the feedback path on the newer filtered modes).
- **MODE** — 22 algorithms (official): Gemini, Hydra, Centaurus, Sagittarius, Great Annihilator, Andromeda (decays into thousands of seconds), Lyra, Capricorn, Large Magellanic Cloud, Triangulum (looper/repeating echoes at 8× DELAY), Cirrus Major, Cirrus Minor, Cassiopeia, Orion, Aquarius (EchoVerb), Pisces (EchoVerb), Scorpio, Libra, Leo (largest/densest), Virgo (smallest/sparsest), Pleiades ("the best sounding reverb in Supermassive"), Sirius (5.0.0 — "true workhorse," clear clean reverbs of any size).

**Use for house:** Free secret weapon for huge breakdown pads and "reverse-swell" transitions — Libra/Pleiades for lush synth reverb, Sagittarius for slow fade-in swells, Triangulum for rhythmic loop beds. Stock fallback: Hybrid Reverb + Echo.

**Manual:** https://valhalladsp.com/shop/reverb/valhalla-supermassive/ · controls: https://valhalladsp.com/2020/05/06/valhallasupermassive-the-controls/

---

## ValhallaFreqEcho (free)

**What it is:** Free Bode-style frequency shifter + analog echo emulation — "perfect for dub, Dr. Who, and all of your psychedelic needs." Covers subtle chorusing and double-tracking through barberpole phasing/flanging to endless glissandos and runaway echoes.

**Main controls** (names verified from official GUI; tooltips document full behavior in-plugin):

- **Mix** (%).
- **Delay** (ms) with **Delay Sync** selector (Free / tempo sync).
- **Shift** (Hz) — the big central frequency-shift knob (0 at center; frequency shifting, not pitch shifting — shifts all partials by a fixed Hz, making repeats increasingly inharmonic).
- **Feedback** (%) — each repeat gets shifted again, producing the barberpole/runaway effects.
- **Low Cut / High Cut** (Hz).
- **Output Mode** (Stereo / other options in-plugin).

(Parenthetical explanation of frequency- vs pitch-shift behavior derives from the official description of "Bode-Style Frequency Shifter" + "endless glissandos"; exact per-knob tooltip text **(unverified)**.)

**Use for house:** Dub-siren and psychedelic send FX — tiny Shift values (±1–5 Hz) with feedback for barberpole-phased dub delays on stabs and percussion fills. Stock fallback: Echo + Shifter (frequency mode).

**Manual:** https://valhalladsp.com/shop/delay/valhalla-freq-echo/

---

## ValhallaUberMod

**What it is:** A unique multitap delay/modulation plugin — up to 32 modulated delay taps with diffusion, overdrive, and parallel slow + vibrato LFOs. Does lush dimensional choruses, classic string ensembles (Solina/VP330-style), tape/BBD echoes, and nonlinear/reverse reverbs.

**Main controls** (verified from official "High Level Controls" post):

- **MIX** (%; label doubles as mix-lock for preset browsing).
- **DEPTH** — master scale on all slow/vibrato modulation depths.
- **WIDTH** — 0% mono-summed → 100% full stereo → >100% "super-stereo" (inverted highs crossfed; crossover set by EQ SpatialEQ).
- **DELAY** (ms) + **SYNC** (Free or tempo divisions, dotted/triplet).
- **FEEDBACK** (stable up to 100% without DRIVE).
- **Tweak tabs** (low-level knob groups, each with its own official doc post): **MOD** (slow/vibrato rates & depths), **TAPS**, **DIFF** (diffusion), **EQ**, **DRIVE** (overdrive), **WARP** (incl. Speed — 1/2X doubles delay time, halves bandwidth).
- **MODE** — 9 algorithms (official): 2TapChorus (Dimension C/D territory), 4TapEnsemble (VP330-derived), SuperSix (analog-poly "unison"), 6TapRandom, DualEnsemble (Solina/ARP String Ensemble, Polysix…), 8Tap, 16Phase (super string ensemble, comb filtering at Depth 0), 16Tap, 32Tap (dense nonlinear/gated/reverse reverbs via DIFF).

**Use for house:** Width and ensemble thickener — 2TapChorus for Dimension-style stereo on basslines/keys (keep WIDTH ≤100% for mono safety), DualEnsemble to turn a plain saw pad into a string machine. Stock fallback: Chorus-Ensemble.

**Manual:** https://valhalladsp.com/shop/delay/valhalla-uber-mod/ · controls: https://valhalladsp.com/2012/01/03/valhallaubermod-the-high-level-controls/

---

## ValhallaSpaceModulator (free)

**What it is:** Free flanger — "our take on flanging." Eleven algorithms covering through-zero flanging, barberpole flanging, detuning, doubling, strange echoes, reverbs, "and all sorts of effects that defy description."

**Main controls** (names verified from official GUI; tooltips document behavior in-plugin):

- **Mix** (%), **Rate** (Hz), **Depth** (ms), **Feedback** (%), **Manual** (ms — static delay offset), **Mode** selector (11 algorithms; the GUI shows e.g. "Up" — individual mode names **(unverified)** from public docs), presets.

**Use for house:** Transition/FX flanger — slow barberpole-style sweep on a riser or white-noise build; subtle Depth + zero Feedback for doubling width on percussion loops. Stock fallback: Phaser-Flanger.

**Manual:** https://valhalladsp.com/shop/modulation/valhalla-space-modulator/

---

## Soundtoys EchoBoy

**What it is:** The pro-standard "ultimate echo machine" — decades of echo devices in one plugin, with modeled vintage styles (Echoplex, Space Echo, Memory Man, DM-2, Tel-Ray oil can, Ampex ATR-102 tape…) and unique musical groove control. Current version 5.5.

**Main controls** (all verified from the official EchoBoy v5 manual):

- **Mix** — 12 o'clock = 50/50; 100% wet for send use.
- **Echo Time** — knob, typed ms values, or tempo-synced **Note / Dot / Trip** buttons (1/2 to 1/64 note); turning the knob live glides pitch like real hardware (automatable for pitch-slide transitions).
- **Feedback** — repeats; high settings go into RE-201-style self-oscillation "runaway" mode.
- **Input / Output level** — drive the modeled analog input stage (affects echo signal only, not dry); LED metering (yellow = −6 dB, red = clipping).
- **Saturation** — tube/tape-style compression, emphasis and subtle distortion on the echo; behavior depends on Style (e.g. Studio Tape adds odd harmonics + HF compression ≈ auto de-essing on vocals; Limited acts like a limiter threshold).
- **Style** — ~30 echo styles (manual list): Master Tape, Studio Tape, EchoPlex, Space Echo, Tube Tape, Cheap Tape, Memory Man, DM-2, TelRay, Binsonette, Telephone, AM Radio, FM Radio, Shortwave, Transmitter, Digital Delay, Analog Delay, Digital Chorus, Analog Chorus, CE-1 Chorus, Vibrato, Saturated, Fat, Distressed, Limited, Distorted, Queeked, Ambient, Diffused, Splattered, Verbed — plus a **Style Editor** (saturation type/amount, tape wobble, diffusion) to design your own.
- **Low Cut / High Cut** — tone of the echoes (effect depends on Style).
- **Groove** (Shuffle ↔ Swing around 12 o'clock) and **Feel** (push echoes ahead of or drag them behind the beat) — "the only echo with true groove."
- **Accent** — accent pattern of repeats (per-mode Tweak menus).
- **Mode:** **Single** (Tweak: Width, L/R Offset up to 25 ms, Accent), **Dual** (Tweak adds Balance, FB Mix, FB Bal), **Ping-Pong**, **Rhythm** (up to 16 taps on a rhythm grid, Shape loudness curve, Repeats, custom saveable patterns).
- **Prime Numbers** switch — nudges repeat times to prime-ish intervals to kill resonant buildup (great for short delays with feedback).
- **Tap Tempo** + **MIDI** toggle (sync to host clock).

**Use for house:** THE dub delay for stabs and vocals — Space Echo style, Ping-Pong, 1/8-dotted, Saturation up, High Cut ~5 kHz so repeats darken into the mix; Feel/Groove to lock echoes into a shuffled tech-house pocket. Stock fallback: Echo.

**Manual:** https://www.soundtoys.com/wp-content/uploads/EchoBoy-Manual.pdf

---

## Soundtoys EchoBoy Jr.

**What it is:** The streamlined EchoBoy — seven of the most iconic analog echo emulations with the complex tweak options stripped away. Same core sound engine, faster workflow.

**Main controls** (all verified from the official EchoBoy Jr. v5 manual):

- **Mix**, **Echo Time** (knob / typed ms / tempo-synced **Note, Dot, Trip** from 1/2 to 1/64 note), **Feedback** (self-oscillation capable).
- **Stereo Mode:** Normal (centered), Wide (slight L/R delay offset), Ping Pong.
- **Glide** — ON: pitch glides when delay time changes (tape/analog behavior); OFF: time changes without pitch artifacts.
- **Style** — 7 styles (official): **Studio Tape** (ATR-102 at 15 ips), **Plex** (Echoplex EP-3), **Space** (Roland RE-201), **Cheap Tape** (worn consumer tape, bright/compressed), **Memory** (EHX Memory Man BBD), **Ambient** (EchoBoy's Distortion + Diffusion combined), **Transmitter** (resonant CB-radio distortion).
- **Low Cut / High Cut**, **Input / Output level** (echo signal only, with LED metering), **Saturation**.

**Use for house:** Quick slapback and groove delay when full EchoBoy is overkill — Space style + Ping Pong on a vocal chop, Glide ON for pitch-drop delay throws. Stock fallback: Echo or Delay.

**Manual:** https://www.soundtoys.com/wp-content/uploads/EchoBoyJr-Manual.pdf

---

## Soundtoys Little AlterBoy

**What it is:** Dramatic voice alteration tool: real-time pitch and formant shifting (lineage: Eventide H3000 team → PurePitch, the first real-time formant shifter), hard-tune quantize, robot mode, MIDI pitch control, plus a Decapitator-derived tube drive stage. Designed for clean **monophonic** vocals — insert it BEFORE other vocal effects (official guidance).

**Main controls** (all verified from the official Little AlterBoy v5 manual):

- **Pitch** — ±12 semitones (±1 octave). Mappable to MIDI for played intervals / vocoder-style lines.
- **Formant** — shifts vocal character independent of pitch: up = "feminine"/chipmunk, down = deeper/richer. Official tip: −1 to −3 adds depth to thin vocals, great for backing vocals.
- **Link** — ON ties Formant to Pitch (tape speed-up/slow-down sound, DJ-style warping; often smoother on difficult material); OFF for independent control.
- **Mode:** **Transpose** (plain shifting), **Quantize** (hard-tune to nearest chromatic semitone — the pop/rap autotune effect), **Robot** (locks to one note; Pitch at 0.0 = C above middle C, Pitch knob selects the note).
- **Drive** — Decapitator-model tube saturation, warmth → grit (official tip: Quantize + Drive = instant pop vocal effect).
- **Mix** — blend shifted and dry for instant harmony/doubling without bussing.

**Use for house:** Vocal-chop sound design — Formant down a few steps for the dark "deep house vocal" color, Pitch −12 for doubled sub-octave thickness, Quantize + Drive for pitched hook effects. Stock fallback: Shifter (pitch+formant-ish via window) or simpler: Auto-Tune Artist / Melodyne for tuning jobs.

**Manual:** https://www.soundtoys.com/wp-content/uploads/Little-AlterBoy-Manual.pdf

---

## Soundtoys Little Radiator

**What it is:** Modeled tube preamp saturation based on the Altec 1566A, the "Motown-era" three-stage mic pre — colored, gritty 60s warmth. Great for fattening bass, guitar, drums, vocals, and (officially) "fantastic on electric piano."

**Main controls** (all verified from the official Little Radiator v5 manual):

- **Heat** — input gain into the tube saturation stage; more Heat = more harmonic distortion and level.
- **Mix** — dry/wet for parallel saturation without external bussing (an addition over the hardware).
- **Bias** switch — ON = choppier, more distorted misaligned-unit character (lo-fi drums, gritty vocals); OFF = pristine-unit, gentler saturation.
- **Noise** switch — models the 1566A's circuit noise; switch down to disable.

**Use for house:** Parallel grit on bass and rhodes/keys stabs — Heat pushed, Mix ~30–50%; Bias ON for lo-fi drum-loop color. Stock fallback: Saturator or Tube drive in Roar/Dynamic Tube.

**Manual:** https://www.soundtoys.com/wp-content/uploads/Little-Radiator-Manual.pdf

---

## SausageFattener (Dada Life / Tailored Noise — NOT Soundtoys)

**What it is:** Dada Life's signature "fat and greasy" one-trick saturator/compressor (their first plugin, made with Tailored Noise). Official positioning: moderate settings on a single channel = a musical compressor; cranked = "a dirty bastard of distortion"; also usable on a drum+bass bus or the whole track as a mastering colorer.

**Main controls:** Officially "only two knobs" (dadalife.com). The knob names — **Fatness** (saturation/weight, with large internal gain boost) and **Color** (brightness/tonal edge), plus a small **Gain** output dial with clipping LED — are consistently documented in press/manual walkthroughs but **(unverified from an official Dada Life control description)**. Widely-cited workflow: set Gain so the LED stays green, then dial Fatness and Color to taste **(unverified)**.

**Use for house:** Classic drum-bus fattener for big-room/tech moments — low Fatness settings glue a drum bus; watch the output Gain since Fatness adds serious level. Stock fallback: Saturator + Glue Compressor (does the same job more transparently).

**Manual:** https://dadalife.com/plugins/ (no public PDF manual online; purchase/support via tailorednoise-downloads.com)
