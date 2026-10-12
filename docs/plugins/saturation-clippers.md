# Saturation, clippers & color — verified reference

**Sources:** official vendor pages/manuals checked 2026-10-12 (XLN Audio, Plugin Alliance, Cradle support, Softube, Klanghelm, Kazrog KClip 3 User Guide v3.2.4, Knock Audio, GVST, Venn Audio/KVR, Slate Digital, Dada Life, Luxora Audio via press, Korneff Audio, Venomode via Plugin Boutique, discoDSP, Universal Audio). Anything a vendor source did not confirm is marked **(unverified)**.
**Skipped here (covered elsewhere):** FabFilter Saturn 2, iZotope (Vinyl, Plasma, Ozone/Trash), SausageFattener, LittleRadiator, Supercharger.

---

## RC-20 Retro Color (XLN Audio)

**What it is:** Lo-fi / vintage color multi-effect built around six effect modules, each emulating a different kind of analog or early-digital degradation. One Magnitude slider scales all active modules together — ideal for automating intros, drops, and transitions.

**The six modules (verified from XLN's product page):**

1. **Noise Generator** — adds texture: vinyl crackle, tape hiss, studio ambience, electric hum, stompbox-style static.
2. **Wobble & Flutter** — pitch instability of unstable analog playback (turntables, tape machines).
3. **Saturation & Distortion** — from mild saturation to heavy fuzz, with several distortion types.
4. **Degrader & Bitcrusher** — vintage-sampler emulation via sample-rate and bit-depth reduction.
5. **Reverb** — a tailored space/width reverb inside the plugin.
6. **Volume Drops** — recreates tape wear and level dropouts.

**Main controls:** per-module amount + on/off; global **Magnitude** slider scaling all modules at once; factory presets for drums, keys, guitars, bass, full mixes, post. (Per-module "Flux" randomization panel: in-plugin, **unverified** from the public page.)

**Use for house:** The go-to for lo-fi texture on melodic loops — light Noise + Wobble on pads/keys for analog movement; automate Magnitude into a breakdown for a "tape dying" transition. Stock fallback: Ableton Vinyl Distortion + Erosion + Redux.

**Manual:** https://www.xlnaudio.com/products/addictive_fx/effect/rc-20_retro_color

---

## Black Box Analog Design HG-2 (Plugin Alliance / Brainworx)

**What it is:** Emulation of the Black Box HG-2 hardware tube processor — four vacuum-tube stages in series and parallel with virtual input/output transformers. Classic mix-bus "glue + harmonics" box.

**Main controls (verified from Plugin Alliance product page):**

- **Input Gain** — digital input level.
- **Pentode / Triode gain** — separate drive for the emulated 6U8A pentode and triode stages.
- **Parallel Saturation** — selects one of two modeled 12AX7 tubes (one voiced more aggressively), blended in parallel.
- **Saturation Frequency** — selector for where the generated 12AX7 harmonics are focused.
- **Density** — drives both tubes harder while keeping their balance and output level roughly constant.
- **Air** — high-frequency sparkle above ~10 kHz.
- **Calibration** — Dark / Normal / Bright high-frequency trim (mimics the hardware's internal trim).
- **Mix** — wet/dry for parallel use.

**Use for house:** Subtle Density + a touch of Air on the drum bus or 2-bus for analog weight without EQ moves; pentode drive on bass for thickness. Stock fallback: Saturator (Analog Clip / Soft Sine) + Glue Compressor.

**Manual:** https://www.plugin-alliance.com/en/products/black_box_analog_design_hg-2.html

---

## The God Particle (Cradle)

**What it is:** Jaycen Joshua's all-in-one mix-bus chain in a plugin: gain-staged input, pre-character EQ, a multiband "character" dynamics section, and an adaptive limiter. Default settings mirror the chain he has used on mixes since 2021. Requires Cradle Hub + internet activation.

**Signal chain / controls (verified from Cradle's official GUI Overview support article):**

1. **Input** — level into the plugin; peak (turns red on clip) + RMS readouts, with a **green target** marking the suggested input level. Hitting the target is the whole gain-staging game here.
2. **EQ (High / Mid / Low)** — three dials before the character section: High = air, Mid = body, Low = warmth.
3. **Amount** — how much "character" (the multiband dynamics processing) is applied, 0–200%; 100% is the recommended start.
4. **Gain reduction (multiband dynamics)** — per-band GR meters with green targets as balance guides; on/off bypass button.
5. **Sidechain INT/EXT** — dynamics keyed from the input itself (INT) or an external signal (EXT, e.g. kick into a drum bus, or full mix when exporting stems).
6. **Limiter** — adaptive limiter; the Limiter dial sets input gain into it, two meters show its gain reduction. Bypassable ("Bypass Active Limiter").
7. **Output** — final level, peak + RMS; keep at 0 dB with the limiter active.

**Use for house:** Mix-bus or drum-bus finisher — feed it the target input level, leave Amount at 100%, and use EXT sidechain from the kick on a drum bus. Don't stack it with the master-bus rule: it IS a master-chain processor, so bypass other 2-bus dynamics while auditioning. Stock fallback: EQ Eight + Multiband Dynamics + Limiter chain.

**Manual:** https://support.cradle.app/hc/en-us/articles/4411750433044-GUI-Overview

---

## Decapitone (vendor UNIDENTIFIED)

**What it is:** **Could not be identified from any official source.** Extensive searching (vendor sites, KVR, Gumroad, GitHub, press) returns no plugin named "Decapitone." It is the only plugin installed in the user folder (`~/Library/Audio/Plug-Ins/VST3` + `Components`) rather than system-wide, which usually means a manually-installed, self-distributed, beta, or renamed build.

**It is NOT confirmed to be Soundtoys Decapitator** — despite the similar name, no official source links the two, and a legitimate Decapitator install appears as "Decapitator" with Soundtoys/iLok licensing. Treat Decapitone as unverified software: open it in Live, check the GUI for a vendor name/version, and verify where it came from before trusting it on sessions.

**Main controls:** (unverified — unknown)

**Use for house:** Not recommended until identified. Stock fallback for any Decapitator-style job: Ableton Saturator (Analog Clip curve) + Dynamic Tube.

**Manual:** none found.

---

## Saturation Knob (Softube, free)

**What it is:** Free one-knob modeled output-distortion unit. One big Saturation knob plus a three-way voicing switch.

**Main controls (verified from Softube page + user manual):**

- **Saturation** — the big knob; amount of drive.
- **Mode switch:**
  - **Keep High** — saturation applied to the low end; highs stay relatively clean.
  - **Neutral** — all frequencies distorted equally.
  - **Keep Low** — saturation applied to the high end; low end (e.g. kick) stays intact.

**Use for house:** Free grit on drum loops and tops — Keep Low mode squashes a loop while the kick stays clean; Keep High fattens bass without fizzy top. Stock fallback: Saturator.

**Manual:** https://www.softube.com/user-manuals/saturation-knob (product: https://www.softube.com/saturationknob)

---

## SDRR2tube (Klanghelm)

**What it is:** The TUBE-mode module of Klanghelm's SDRR 2 saturation processor, distributed as a standalone plugin (notably bundled free in PreSonus's Studio Magic suite — the likely source of this install). The full SDRR 2 ($) is a dynamic, program-dependent saturator with four modes: **TUBE** (two blendable tube-preamp models), **DIGI** (controlled even/odd harmonics, two models), **FUZZ** (two germanium fuzz boxes, tamed), **DESK** (mixing-desk channel with 2-band EQ, transient and compression control). Only TUBE is in this inventory.

**Main controls (verified from Klanghelm's SDRR page):**

- **CHARACTER** (TUBE mode) — blends the two tube models: **WARM** end = transient smoothing/compression, **SIZZLE** end = harmonics from heavily driven transients.
- **DRIFT** — adds movement/variance to the saturation.
- Switchable/exaggerable **crosstalk**; **RMS level-difference metering** mode for gain-matched A/B.
- Central drive knob and output trim: present in the plugin but **(unverified)** by name from the public page — see manual.

**Use for house:** Gentle WARM-side tube rounding on stabs, keys, and vocal loops; the RMS-matched metering makes honest saturation A/B easy. Stock fallback: Dynamic Tube or Saturator.

**Manual:** https://klanghelm.com/contents/products/SDRR (manual linked from page)

---

## KClip 3 (Kazrog)

**What it is:** Mastering-grade clipper and track saturator with multiband parallel processing and loudness metering. Fully verified from the official KClip 3 User Guide (v3.2.4, Kazrog LLC).

**Main controls (verified from the official manual):**

- **In Gain** — boost/cut into the oversampled clipping stage.
- **Out Gain** — output of the clipper process; **Inverse Gain Link (LINK)** ties In/Out inversely for level-matched drive.
- **Soft Mode** — 8 clipping algorithms: **Smooth** (KClip 1 classic, pure hard clip until Softness is raised), **Crisp** (famous blue ADC/DAC digital saturation, fixed curvature — the "in your face" mastering mode), **Tube** (hi-fi tube preamp from Kazrog's Thermionik line), **Tape** (tape warmth/saturation without wow/flutter/hiss), **Germanium** (fuzz-pedal transistor clipping), **Silicon** (harder fuzz transistor — extreme lo-fi), **Guitar Amp** ("Plexi"-style circuit, no cab), **Broken Speaker** (extreme cone-excursion distortion).
- **Soften** — clipping-knee softness (active in all modes except Crisp).
- **Threshold** — clip point adjustable down to −48 dB (clip quiet sources without input-gain changes).
- **Ceiling** — optional final 100% hard clip at session rate, post Out Gain, no oversampling; catches overages only — the manual warns NOT to rely on it for substantial dBs (aliasing).
- **Mid/Side** — stereo-field ratio (pre-clip in single band, post-clip in multiband).
- **Mix / Delta (δ)** — wet/dry blend; Delta solos only the changed signal.
- **Bands Select** — 1 or 4 bands; in 4-band mode each band gets its own mode/settings over adjustable crossovers.
- **Loudness Target** — LUFS target selector; target-reset button auto-adjusts the Ceiling to hit the integrated-loudness target (Ceiling must be enabled).
- Also: Visualiser (waveform/spectrum), jumbo meters, Clipped meter, Integrated/Momentary LUFS, A/B compare + copy, internal bypass, 2x–32x oversampling with separate offline render settings.

**Use for house:** The drum-bus clipper — Crisp or Smooth mode, drive In Gain with LINK on, 4–8x oversampling; also pre-limiter on the 2-bus to shave peaks so the limiter works less. Stock fallback: Saturator (Hard Clip) or Live 12's Limiter.

**Manual:** https://kazrog.com/products/kclip-3 (User Guide PDF ships with the plugin)

---

## KNOCK Clipper (DECAP / Plugins That Knock, now Knock Audio)

**What it is:** The clipper module from DECAP's KNOCK plugin as a standalone — the clipping sound of the DRUMS THAT KNOCK kits. Pushes drums hard, warm-to-aggressive, never exceeding 0 dB. Zero latency.

**Main controls (verified from knockaudio.com product page):**

- **Clip curve (hard ↔ soft)** — continuously variable; harder = more aggressive, softer = rounder.
- **HQ / Oversampling** — optional high-quality oversampled mode.
- Input and output gain controls: reported in reviews, **(unverified)** from the vendor page.

**Use for house:** Per-track drum clipper — kick or full drum bus into the soft side of the curve for punch that stays under 0 dB. Stock fallback: Saturator (Hard Clip) with drive.

**Manual:** https://knockaudio.com/products/knock-clipper

---

## GClip (GVST, free)

**What it is:** Free, tiny wave-shaping clipper — a long-standing utility classic. Stops the signal exceeding a set level with a variable knee.

**Main controls (verified from GVST page):**

- **Gain** — level into the clipper.
- **Clip** — clip level as a percentage of full scale (50% = ±0.5 on a ±1 scale).
- **Softness** — knee shape: 0% = pure truncating hard clip; higher values start shaping below the clip level.
- **2x Oversample** — on/off, reduces shaping aliasing.
- **Graph + wave display** — transfer curve and before/after waveform with clip line.

**Use for house:** Quick utility clip on a slammed percussion loop or to shave a transient before a compressor; zero-cost, zero-frills. Stock fallback: Saturator (Hard Clip).

**Manual:** https://gvst.uk/gclip.htm

---

## Free Clip (Venn Audio, free)

**What it is:** Free multi-algorithm soft clipper / waveshaper. Note: Venn Audio's site was unreachable at time of writing; the plugin has been superseded by Free Suite / Free Clip 2, and details below are from the KVR product listing (vendor-supplied text).

**Main controls (verified from KVR listing for Free Clip 1):**

- **Clip shape** — five sigmoid functions, transparent→saturated: **Hard clip**, **Quantic**, **Cubic**, **Algebraic**, **Arctangent**. Hard/quantic/cubic recommended for mastering (little added saturation); algebraic/arctangent for saturation effects.
- **Ceiling** — clip level slider with adjacent meter; lower ceiling = more saturation.
- **Input gain / Output gain** — drive in, restore level out.
- **Oversampling** — up to 32x (CPU-heavy at 16–32x); **post-oversampling clip** option catches inter-sample overs that oversampling reintroduces above the ceiling.
- No bypass or dry/wet (per user reports — **unverified**).

**Use for house:** Transparent peak-shaving on individual drums or the drum bus when you want a free, honest hard clip. Stock fallback: Saturator (Hard Clip).

**Manual:** https://www.kvraudio.com/product/free-clip-1-by-venn-audio (vendor site vennaudio.com unreachable at check)

---

## Fresh Air (Slate Digital, free)

**What it is:** Free dynamic high-frequency exciter based on vintage exciter circuits plus dynamic processing — brightness and shimmer without static-EQ harshness.

**Main controls (verified from Slate Digital page):**

- **Mid Air** — upper-mid presence lift.
- **High Air** — top-end/air lift.
- (The page confirms only these two knobs; exact frequency ranges and any trim control are **unverified**.)

**Use for house:** A touch of High Air on vocal chops, hats, or a dull melodic sample to open the top end; it's dynamic, so it stays smoother than an EQ shelf. Stock fallback: EQ Eight high shelf, or Saturator with High-quality + tone shaping.

**Manual:** https://slatedigital.com/fresh-air

---

## Wide Awake (Dada Life)

**What it is:** Stereo widener from Dada Life's **Secret Sauce bundle** (with Space In-Your-Face and Eternal Return — all three are in this inventory). Official line: turns mono sounds into "full-on rainbow stereo"; a deliberately drastic effect with an ultra-minimal two-knob interface. Listed as "Wide Awake Rainbow" on dadalife.com.

**Main controls:** two knobs. Press coverage names them **Amount** (effect intensity) and **Range** (which frequency band the widening focuses on), plus a Type switch between two effect versions — knob names are **(unverified)** from Dada Life's own page, which doesn't label them.

**Use for house:** Widen pads, stabs, or tops — never the kick/bass. Keep Range focused above the low end and check mono compatibility. Stock fallback: Ableton Utility (Width) or Chorus-Ensemble.

**Manual:** https://dadalife.com/plugins/ (support via Tailored Noise)

---

## LUX Vocal Preamp (Luxora Audio, free)

**What it is:** Free vocal saturation plugin by **Luxora Audio** (released Aug 2025, alongside LUX Sub-Bass — also in this inventory). Models the tone of 1970s–90s 12AX7 tubes for smooth tube warmth on vocals. VST3/AU/AAX, macOS + Windows; registration required to download.

**Main controls (verified via vendor statements in press/KVR):**

- **Saturation** — single one-knob tube-saturation control.
- **EQ** — a one-knob EQ with a tuned curve for natural vocal shaping; bypassable so the plugin runs as a pure saturator.
- (Noted as CPU-hungry by reviewers.)

**Use for house:** Quick tube color on vocal hooks/chops before the main chain; the sibling LUX Sub-Bass (12AU7-modeled) covers 808s/bass. Stock fallback: Dynamic Tube or Saturator.

**Manual:** https://luxora-audio.com/free-plugins/lux-vocal-preamp

---

## Space In-Your-Face (Dada Life)

**What it is:** Reverb from Dada Life's **Secret Sauce bundle** — not a saturator. Built to stay clear and wide even when applied heavily ("a lush reverb that doesn't sound muddy even if you use a lot of it"). Same ultra-minimal two-knob philosophy as the rest of the bundle.

**Main controls:** two knobs (unlabeled on the vendor page — **unverified**). A third-party Max for Live wrapper exposes **Time, Wetness, Brightness**, suggesting those are the underlying parameters **(unverified)**.

**Use for house:** Instant big-wash reverb on leads/vocal shots in drops where Hybrid Reverb would need more tweaking; automate wetness for transitions. Stock fallback: Hybrid Reverb.

**Manual:** https://dadalife.com/plugins/ (support via Tailored Noise)

---

## Retromulator (discoDSP) — NOT a saturation plugin

**What it is:** Identified: **discoDSP Retromulator** (released March 2026) — a bit-accurate, low-level hardware **synthesizer emulator** built on the open-source Gearmulator project, not a color/saturation tool. Emulates classic digital synths (Access Virus A/B/C/TI, Waldorf microQ/XT, Nord Lead 2X, Roland JP-8000, Yamaha DX7, Akai S1000). Free/GPL-v3; most cores require ROM firmware dumped from hardware you own (the Akai S1000 core needs none). AU/VST3/standalone.

**Main controls:** per-emulated-synth; no unified control set. The JP-8000 and Virus cores are the only ones relevant to melodic house supersaws — but note users report no editing GUI for some cores.

**Use for house:** File under synths, not processing. Without ROMs it does little; Serum 2 / Diva / Vital already cover this ground. Stock fallback: Wavetable or Analog.

**Manual:** https://www.discodsp.com/retromulator

---

## Power Grid Disruptor (Korneff Audio)

**What it is:** Identified: **Korneff Audio** glitch/damage/transition effect (released 2026, free for a limited time, list $347.99). It "disrupts" audio with damage processing plus built-in riser (Surge) and impact samples — an FX-and-transitions tool rather than a mix saturator. VST3/AU/AAX/LV2.

**Main controls (verified from Korneff product page):**

- **Disrupt button** — detonator-style: hold to build tension, release to trigger the impact.
- **Damage modes** — **Drive, BitCrush, Decimate, Noise**, or **All** four at once.
- **Glitch Engine** — four pattern modes: **Stutter, Gate, Random, Chaos**, synced to the DAW.
- **Surge & Impact sample selectors** — 40+ combinable riser/impact sounds.
- **Impact Duck** — ducks the dry signal under the impact sample (100% = impact only).
- **Time direction (LMM)** — forward/backward processing with direction, duration, length controls.

**Use for house:** Build-up and drop transitions — hold Disrupt through the last bars of a break, release on the drop; Stutter/Gate patterns for fills. Belongs with 09 FX & TRANSITIONS racks, not on mix buses. Stock fallback: Echo + Redux + Auto Filter automation, or a Beat Repeat.

**Manual:** https://korneffaudio.com/product/power-grid-disruptor/

---

## Mesa Lite (Venomode)

**What it is:** Identified: **Venomode Mesa Lite** — a free **soft clipper**, not an amp sim (the "Mesa" name is coincidental to Mesa/Boogie). Free entry version of the paid Mesa, which adds multiband, more clipping modes, and stereo options. VST/VST3/AU/AAX, macOS/Windows/Linux.

**Main controls (verified from the Plugin Boutique listing; Venomode's own page was unreachable at check):**

- **Variable-shape soft clipping** — one control sweeping from hard flatline clipping to a very gentle roll-off around the threshold.
- **4x oversampling** — internal, for aliasing reduction.
- **Waveform metering** — real-time input/output/clipping display.
- Pre Gain / Post Gain with Link: reported in press reviews, **(unverified)** from the listing.

**Use for house:** Another free utility clipper — handy on individual drum hits where KClip is overkill. Stock fallback: Saturator (Hard Clip).

**Manual:** https://www.pluginboutique.com/products/16308-Mesa-Lite (vendor: venomode.com)

---

## UAD Showtime '64 Tube Amp (Universal Audio) — brief

**What it is:** `uaudio_showtime_amp` = **UAD Showtime '64 Tube Amp**, a native UA plugin (no UAD hardware needed) modeling a 1964 Fender Showman-style tube amp — full circuit including the tube-driven vibrato/bias-tremolo, with a selection of classic speaker cabinets. Released Oct 2025 as a free promo (normally $149); runs AU/VST3/AAX on Apple Silicon natively.

**Main controls:** standard amp-panel controls (volume/tone/vibrato) + cab selection — individual knob names **(unverified)**; see the UAD manual.

**Use for house:** Niche here — character amp for guitar samples, or crank it as a creative tone box on keys/vocal chops. Stock fallback: Ableton Amp + Cabinet.

**Manual:** https://www.uaudio.com/blogs/press/ua-announces-uad-showtime-64-tube-amp-brings-bold-vintage-guitar-tones-to-any-daw (full manual via UA help docs)
