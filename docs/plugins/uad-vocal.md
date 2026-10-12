# UAD & vocal tools — verified reference

Sources: help.uaudio.com official plug-in manuals (Teletronix LA-2A Tube Compressor, 1176 Classic FET Compressor, UA 1176 Classic Limiter Collection, UA 610 Tube Preamp & EQ Collection, Century Tube Channel Strip), Antares official Auto-Tune Artist User Guide (PDF via help.antarestech.com), celemony.com, sienna.acustica-audio.com, support.landr.com. Controls below are taken from those manuals unless marked "(unverified)". Checked 2026-10-12.

> Binary-name mapping: the `uaudio_*` entries in `inventory/plugins.txt` are UA's **native (UADx) single plug-ins** installed via UA Connect — the simplified giveaway/Volt-bundle versions, not the full paid Collections. Where the full Collection adds controls, that's noted so you know what you do *not* have.

---

## Teletronix LA-2A Tube Compressor (`uaudio_teletronix_la-2a_tc`)

**What it is:** UA's native single-plug-in LA-2A — officially "a simplified version of the Teletronix LA-2A Silver plug-in from the Teletronix LA-2A Leveler Collection" (UA manual), i.e. the late-'60s Bill Putnam-era "Silver" algorithm in the classic GUI. Hardware heritage: Jim Lawrence (Teletronix, Pasadena, 1958) invented the electro-optical T4 gain cell — a luminescent panel driving photoresistors — giving program- and frequency-dependent gain reduction with a multi-stage release (the cell can take minutes to fully recover). Putnam/UA acquired Teletronix via Babcock in 1967 and kept building the LA-2A. Tube make-up amplifier; ~3:1 "compress" behavior, soft knee.

**Main controls** (complete set of the single plug-in):
- **Peak Reduction** — sets compression amount by lowering the threshold (range 0 to −40 dB; the 0–100 panel numbers are arbitrary). At minimum, no compression but the signal is still colored by the circuit.
- **Gain** — up to +40 dB make-up after compression; does not affect compression amount.
- **Compress/Limit switch** — ratio ≈3:1 (Compress) or ≈∞:1 (Limit); nonlinear and frequency dependent, so not absolute. (On the hardware this switch is on the rear panel.)
- **Meter knob** — VU shows Gain Reduction, or output at +10 / +4 calibration.
- **VU Meter**, **On/Power switch** (full bypass, reduces CPU).
- *Collection-only (not in this plug-in):* Mix (parallel, LA-2 model), Emphasis (R37 sidechain HF filter — turning it counter-clockwise makes compression more sensitive to highs), and the Gray / LA-2 models.

**Use for house:** The classic slow-opto vocal leveler — 3–5 dB of Peak Reduction in Compress mode glues vocal samples and toplines without audible pumping at 124 BPM; also lovely on melodic bass/pad stems for warmth. Stock fallback: Ableton Compressor with slow attack/auto release, or Glue Compressor.

**Manual:** https://help.uaudio.com/hc/en-us/articles/19378009641748-LA-2A-Tube-Compressor-Manual (full Collection: https://help.uaudio.com/hc/en-us/articles/4419496124180-Teletronix-LA-2A-Leveler-Collection-Manual)

---

## UA 1176 — 1176 Classic FET Compressor (`uaudio_ua_1176`)

**What it is:** UA's native single 1176, officially "based on the classic early 70's / Brad Plunkett 'LN' (Low Noise) era of the 1176 circuit lineage" — i.e. the Rev E "Blackface" character (more linear response, transistor gain amp, musical program dependency). Hardware heritage: Bill Putnam's 1967 1176 was the first solid-state limiter with ultra-fast 20 µs FET gain reduction. The paid **1176 Classic Limiter Collection** (which this is not) adds three separate plug-ins — 1176 Rev A "Bluestripe" (original FET design, more distortion), 1176LN Rev E, and 1176AE 40th Anniversary (2:1 ratio + fixed 10 ms "SLO" attack) — plus Headroom, Mix and Sidechain Filter controls.

**Main controls** (complete set of the single plug-in):
- **Input** — sets gain reduction amount *and* relative threshold (no separate threshold knob). Clockwise = more compression and more distortion. Values are arbitrary, as on hardware.
- **Output** — make-up gain; increasing it also increases distortion.
- **Attack** — 20 µs to 800 µs (fastest fully clockwise — the knob works "backwards").
- **Release** — 50 ms to 1100 ms (fastest fully clockwise); heavily program-dependent (fast after transients, slower under sustained compression).
- **Ratio buttons** — 4:1, 8:1, 12:1, 20:1. **All-Button ("British") mode** via Shift-click on any ratio: ratio lands between 12:1 and 20:1, bias points shift, radically more distortion — the trademark overdriven drum/room sound.
- **Meter Function** — GR, +8, +4 output calibration, OFF (bypass). VU meter reads strangely in GR with all buttons in; that's authentic.
- *Collection-only (not in this plug-in):* Headroom (4–28 dB internal reference), Mix (parallel), Sidechain Filter (3 dB/oct tilt to stop bass pumping), multi-button combos, Attack-OFF color mode, Rev A / AE models.

**Use for house:** Aggression box — 4:1, medium-slow attack (let the transient through), fast release on percussion loops, tops and rave stabs; all-button on a parallel drum bus for energy. UA's own "grit trick": fastest attack + release = FET distortion on bass. Stock fallback: Ableton Compressor (fastest attack is ~0.01 ms) + Saturator for the color.

**Manual:** https://help.uaudio.com/hc/en-us/articles/34530260482324-1176-Classic-FET-Compressor-Manual (Collection: https://help.uaudio.com/hc/en-us/articles/4419447352980-UA-1176-Classic-Limiter-Collection-Manual)

---

## UA 610-A / 610-B Tube Preamp & EQ (`uaudio_610_a`, `uaudio_610_b`)

**What it is:** End-to-end emulations (tube amps, transformers, feedback-style EQ) of Bill Putnam Sr.'s 610 console channel strips (1960) — among the first desks purpose-built for recording. **610-A** models the vintage 610-A module from the Wally Heider "Green Board" console (Pet Sounds, Folsom Prison, Monterey Pop, later Neil Young's *Harvest*). **610-B** models UA's modern 2-610 dual-channel preamp (the design in the LA-610mkII / 6176; Adele, Cold War Kids). Input and output stages each have their own tube gain stage — tuning the I/O gain structure is the whole game; the EQ's feedback design also changes output-stage distortion.

**Main controls** (both, differences noted; all from the UA manual):
- **Input Select** — Line (less tube gain, cleaner) or Mic (~+30 dB unattenuated tube gain → easy saturation/clipping from a line-level DAW signal). 610-A mic impedance fixed 600 Ω; 610-B selectable 500 Ω / 2.0 kΩ (subtle color differences; impedance physically switches only with Apollo Unison).
- **Gain** — 610-A: three-position LO/OFF/HI switch exposing internal gain jumpers; HI ≈ +8 dB at the tube input stage with changed distortion character; OFF bypasses the plug-in. 610-B: 5-position switch, −10 / −5 / 0 / +5 / +10 dB at the tube input stage.
- **Mic Pad** — 610-A: −20 dB; 610-B: −15 dB. Mic input only; fixed off in the native plug-ins.
- **Polarity (ø)** — phase flip.
- **EQ** — 610-A: L.F. shelf fixed 100 Hz, ±6/0 dB; H.F. shelf fixed 10 kHz, −6/0/+3/+6 dB. 610-B: LO shelf 70/100/200 Hz and HI shelf 4.5k/7k/10 kHz, each ±1.5/3/4.5/6/9 dB stepped.
- **Level** ("the big knob") — tube *output* stage gain, ~61 dB range; higher = more color.
- **Output** — plug-in-only clean digital trim, −∞ (off) to +12 dB: crank Gain/Level for distortion, pull Output down to level-match.

**Use for house:** Not really a "preamp" in the box — it's a tube color/saturation stage. Mic mode + hot Level, Output pulled down = thick drive on bass, drum bus or vocal samples; the broad 610-B shelves (200 Hz / 4.5 kHz) are great "vibe EQ" strokes. Stock fallback: Saturator + EQ Eight shelves; owned-plugin alternative: Decapitone / Saturn 2.

**Manual:** https://help.uaudio.com/hc/en-us/articles/17475989779860-UA-610-Tube-Preamp-EQ-Collection-Manual

---

## Century Tube Channel Strip (`uaudio_century_channel_strip`)

**What it is:** UA's original-design (no single hardware ancestor) vintage-style "first take" tracking strip: tube mic preamp → 3-band EQ → autoformer-driven opto leveler → master, in serial left-to-right modular flow. EQ and Opto Leveler sections bypass individually. Unison integration is for Apollo/Arrow DSP use only; as a native insert it's a color strip.

**Main controls** (all from the UA manual):
- **Tube Preamp:** Gain switch Low/High (Low suits modern condensers / hotter sources, High adds more tube saturation — made for dynamics/ribbons); input **OL LED**; **Input Select** Line/Mic; **High Pass** 18 dB/oct @ 80 Hz; **Polarity ø**; **Pad** −20 dB (Mic only); **Level** (tube output-stage gain — higher = more tube distortion) with output OL LED.
- **Equalizer:** **High** shelf fixed 10 kHz ±12 dB; **Mid** semi-parametric, **Freq** 300 Hz–7.2 kHz, ±12 dB (Q narrows as gain increases); **Low** shelf fixed 110 Hz ±12 dB; **Out/In** bypass.
- **Opto Leveler:** single **Compression** knob (more rotation = more gain reduction) with built-in auto-gain compensation; GR meter; **Out/In** bypass.
- **Master:** VU output meter; **Output** −∞ to +12 dB clean digital gain; **Off/On** full bypass.

**Use for house:** One-knob utility strip for vocal samples and found percussion — HPF, a quick 10 kHz air shelf, and the auto-gain opto to lock a chopped vocal in place with zero fuss. Stock fallback: EQ Eight + Compressor, or a Channel-EQ/Compressor rack.

**Manual:** https://help.uaudio.com/hc/en-us/articles/11912560531860-Century-Tube-Channel-Strip-Manual

---

## Auto-Tune Artist (Antares)

**What it is:** Antares' professional **real-time** pitch corrector — effectively Auto-Tune Pro's Auto Mode with low latency for live/studio use. **There is no Graph Mode in Artist** (the official manual's complete control list contains none; graphical editing is Auto-Tune Pro territory). Two views: Basic (common controls) and Advanced (everything, incl. Edit Scale, MIDI, Create Vibrato).

**Main controls** (verified from the official Antares Auto-Tune Artist User Guide):
- **Global:** **Input Type** (Soprano, Alto/Tenor, Low Male, Instrument, Bass Instrument — pick the right one for tracking accuracy); **Key** + **Scale** (set Chromatic to tune to nearest semitone; appendix scales include equal temperament, historical, non-Western and experimental tunings); **Classic Mode** — the "Auto-Tune 5 sound" (brighter, more pronounced note transitions at fast Retune Speeds; disables Formant, Throat, Transpose and Flex-Tune); **Formant** (formant correction on/off) + **Throat** (throat-model length, Formant on only); **Transpose** ±1 octave in semitones, real time; **Detune** ±100 cents (A≠440 reference); **Tracking** (default 50; raise for breathy/noisy signals, lower if clicks/pops).
- **Basic View:** **Retune Speed** (ms; **0 = the hard Auto-Tune effect**, 10–50 typical for natural correction); **Flex-Tune** (correction only as the singer approaches the target note — preserves expressive gestures); **Humanize** (slower retune on sustained notes only, so fast speeds don't freeze long notes); **Natural Vibrato** (scale existing vibrato up/down); Pitch Display + Pitch Change Meter (cents); **Keyboard** with per-note On / Bypass (orange, passes uncorrected) / Remove (grey, tunes to next scale note), Latch/Momentary modes.
- **Advanced View:** Targeting Ignores Vibrato; **Create Vibrato** section (Shape, Rate, Onset Delay, Onset Rate, Variation, Pitch/Amplitude/Formant amounts); Edit Scale Display (per-note Bypass/Remove/Cents, Set Major/Minor); **MIDI** Target Notes / Learn Scale / All Octaves + MIDI parameter control; Settings: Auto-Key detection (Auto-Key sold separately), Low Latency mode, pitch reference, knob behavior.

**Use for house:** Chromatic/scale + Retune Speed 0 + Formant on = the instant hard-tune topline sound; Key/Scale to the track's minor key with Speed 20–50 + Flex-Tune for transparent correction of vocal samples. Live 12 stock fallback: Auto Shift (scale-aware real-time correction, less surgical).

**Manual:** https://help.antarestech.com/hc/en-us/articles/41105580772116-Auto-Tune-Artist-Help-Page (User Guide PDF linked there)

---

## Melodyne (Celemony)

**What it is:** Note-based offline pitch/time editor: it analyzes audio into individual **notes ("blobs")** you edit directly — pitch, vibrato/pitch drift, volume, sibilants, length, timing and formants — instead of a waveform. The binary is the same for every edition; the license decides the tier, so the installed edition can't be read from `plugins.txt`. Official edition ladder (celemony.com):
- **essential** — basic pitch and timing tools, melodic (monophonic) material.
- **assistant** — the full single-track vocal toolset: pitch, timing, vibrato, phrasing, formants, dynamics.
- **editor** — assistant + **DNA Direct Note Access** (edit individual notes *inside* polyphonic audio — chords on guitar/piano) and chord-aware sample adaptation.
- **studio** — everything, multitrack: edit notes across all tracks, multitrack workflow and macros, sound editor.

**Core workflow in Live 12:** **Ableton Live 12 does not support ARA** (confirmed through the Live 12.3 feature set, Oct 2025 — stem separation/Splice, still no ARA), so the "instant" ARA integration Melodyne has in Studio One/Cubase/Logic isn't available. In Live: insert Melodyne as a regular plug-in on the clip's track, press its **Transfer** button and play the clip once to capture it, then edit blobs (double-click/drag for pitch, right tool for timing; algorithm per clip: Melodic, Percussive, Polyphonic/DNA). Alternatively use the standalone app, or set Melodyne as Live's external Sample Editor and replace audio after editing. Transfer workflow detail (unverified wording, standard Melodyne operation); non-support of ARA in Live verified.

**Use for house:** Fix one sour note in a vocal sample without re-tuning the whole phrase; with editor/studio, re-pitch chords inside a sampled loop to fit your minor/Dorian progression. Pairs with Auto-Tune Artist: Melodyne for surgical offline repair, Artist for the real-time effect.

**Manual:** https://www.celemony.com/en/melodyne/what-is-melodyne — full manuals at https://helpcenter.celemony.com

---

## SIENNA GURU & SIENNA ROOMS (Acustica Audio)

**What they are:** Two plug-ins from Acustica's **Sienna** headphone monitoring suite (headphone correction + studio/room/speaker emulation, built from Acustica's sampling of ~200+ real headphones, control rooms and monitors). These are *monitoring* tools for the end of the master bus while working on headphones — **always bypass/remove before export**. The suite's tiers: **Reference/Reference Pro** = headphone correction only; **ROOMS** = correction + virtual control-room/speaker emulation; **GURU** = ROOMS plus an advanced panel for fine-tuning the virtual space. (Precise identification per sienna.acustica-audio.com; GURU control detail per Sound On Sound's review, as Acustica's page doesn't enumerate them.)

**Main controls:**
- **SIENNA ROOMS:** headphone-model selector (correction profile); room/monitor selection (sampled studios — e.g. House of Glass, Acustica's rooms; pairings of room+speakers are fixed); **Perfection** slider (morph between the real captured room and an idealized/corrected response); **Input Trim** (loudness-compensated drive); **Depth** (HRTF-style "Filtering ↔ Translation", 30% default); smart/AI presets + user slots.
- **SIENNA GURU:** ROOMS-style GUI plus a Guru panel adding (per SOS review): **Acustica++** (crossfeed ↔ binaural blend), **Width** (virtual speaker angle/distance), **Depth++** (more Sides signal), **Focus** (speakers-only vs speakers-in-room balance), **Pan++** (inter-aural level vs timing cues), L-R pan matching. (unverified against an official Acustica manual — Acustica publishes no public control-by-control doc for Guru.)

**Use for house:** Check low-end translation and stereo width of a club mix on headphones — ROOMS for "how does this sound on real monitors in a treated room", GURU to tune that virtual room to match speakers you trust. Monitoring only; never print it.

**Manual:** https://sienna.acustica-audio.com/ (overview; manuals ship with the Aquarius installer)

---

## LANDR FX Bass / Beats / Electric / Voice

**What they are:** Four of LANDR's five single-dial multi-FX macro plug-ins (the fifth, Acoustic, isn't in the inventory). Each is "loaded with expertly-crafted presets designed to add character and color" to one source type (official LANDR support): **Bass** — low-end/groove enhancement and iconic bass effects; **Beats** — punch/power presets for drums, from single kick/snare/hat to full loop or drum-bus settings; **Electric** — richness, gloss and classic effects for electric guitar and synths; **Voice** — EQ, reverb, saturation, delay and polish for vocals. Each plug-in has **40–50 presets** built from standard processors (EQ, compression, saturation, reverb, delay) plus creative (flanger/chorus, depending on plug-in) and corrective presets (sibilance, volume, noise — e.g. Voice's De-Ess/De-Mud).

**Main controls** (deliberately minimal): preset browser + **one main intensity/blend dial** that scales the whole preset chain ("choose your preset, dial in your desired intensity" — official), plus input and output level trims. No access to the individual processors inside a preset. Exact knob labels per plug-in (unverified — LANDR publishes no control-level manual).

**Use for house:** Sketch-stage color — Beats on a percussion loop or Voice on a vocal chop to audition a vibe in seconds, then rebuild keepers with stock devices (EQ Eight, Compressor, Echo, Hybrid Reverb) or FabFilter/Valhalla for real control. Not mix-bus material.

**Manual:** https://support.landr.com/hc/en-us/articles/4416552756503 (What is the LANDR FX Plugin Suite?) · https://support.landr.com/hc/en-us/articles/4416543905559 (What kind of FX are included?)
