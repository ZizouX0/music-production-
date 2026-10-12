# Modulation, motion & creative FX — verified reference

Sources: official vendor pages/manuals — Cableguys ShaperBox 3 Manual v3.6.3 (PDF), Xfer Records, Output Movement User Guide, Native Instruments, Polyverse Music, IK Multimedia (via Sound On Sound review — official page unreachable at scan time), AIR Music Technology, Plugin Alliance, Dada Life press/DJ Mag, AudioThing manual PDF, KVR/Bedroom Producers Blog for small freeware. Anything not confirmed by an official source is marked **(unverified)**.

Per the three-option rule: these are **step 2** tools. Stock fallbacks are noted where obvious — always offer the Ableton stock device first.

---

## ShaperBox 3 (Cableguys)

**What it is:** A flexible serial effects rack of nine LFO-driven "Shapers" plus two Tools (Compressor, Oscilloscope). Every Shaper is driven by a drawable LFO wave editor and/or an envelope follower, triggers via **Sync / MIDI / Audio** (including external sidechain input), and can be split into **3 bands** with independent LFO + envelope per band. Shared controls: LFO wave editor (lines/curves/steps, Smooth), LFO length (beats/Hz/MIDI pitch), trigger mode, Multiband Editor, per-Shaper Mix, Master Mix, Wave Presets/Palette, per-Shaper oscilloscope.

**Main controls (per shaper, from the v3.6.3 manual):**

- **TimeShaper 3** — buffer scrub/stutter via LFO. *Time Range* (Linked/As LFO Length; Beat 1/2/4/8 bars; Fine 2.5/10/20 ms for tape-wow/vibrato), *Step Mode* (Smooth/Instant). Half-time, reverse, scratches, tape-stops.
- **PitchShaper** — drawable pitch ±24 st + formant. *Mode* (Complex / Vocals / Drums / Vintage), *Grain Size*, *Pitch*, *Formant* (Vocals & Drums modes), *Formant Link*, *Density*. Note grid highlights 5ths/octaves.
- **DriveShaper 2** — modulated distortion. *Drive*, *Grip* (quiet-signal attenuation), *Push* (DC offset/asymmetry), *Style* (12 types: Soft/Smooth/Hard Clip, Soft/Hard Square, Soft/Hard Rectify, Skew/Sine/Triangle/Saw/Extreme Fold), *Accent*, *Tone*, Input/Output gain.
- **NoiseShaper 2** — adds noise layers (60+ noises: Noise/Organic/Analogue/Cymbal/Percussion + user import). *Noise* (level), *Trim*, *Pitch* ±24 st, *HP/LP filter*, *Mono Noise*, *Noise Only*; envelope *Follow* or *Duck* modes.
- **ReverbShaper** — convolution reverb with LFO/envelope on *Send* and *Volume*. IR categories Hall/Epic/Special/Mechanical/Room/Non-Linear + user IRs; *Pre-Delay* (ms or synced), *Decay*, *Gated*, *Width* (0–200%), *Size* (IR resample), *Clear Tails*, independent *Dry/Wet*.
- **FilterShaper Core 3** — 3-band multimode filter, LFO + envelope per band. *Filter Type* (Low-pass/High-pass/Band-pass/Notch/Peak; Clean or Warm Sallen-Key flavors; 6/12/24 dB), *Cutoff* (20.6 Hz–21.1 kHz), *Resonance* (self-oscillation with Warm), *Stereo* (L/R cutoff offset ±60 st), *Dist*, *Safe Res*, *Hard Dist*. Audio-rate modulation (LFOs to 5.24 kHz).
- **LiquidShaper** — flanger/phaser. *Type* (Off/Flanger/Phaser), *Mode* (+/−), *Stages* (phaser, 2–8 peaks), *Center*, *Stereo*, *Feedback*.
- **CrushShaper 2** — lo-fi. *Bits* (16→1), *Push*, *Dither*, *Resample* (44.1 kHz→8.82 Hz), *Jitter*, *Pre-Filter*, *Treble*.
- **VolumeShaper 7** — LFO volume (gain −inf…0 dB), *Trim* (±24 dB), *Show External Sidechain* overlay. Quick Presets: Half-time, Sidechain, Trim, Send.
- **PanShaper 4** — level + psychoacoustic Haas panning. *Pan*, *Pan Law* (Stereo Balance 3/4.5/6/0 dB or Stereo Combined), *Pan/Haas* blend (100/0–0/100%), *Haas Range* (0–40 ms), Vectorscope.
- **WidthShaper 3** — modulates side-signal level only (always mono-compatible). *Width* (0–200%), *Gain*, Vectorscope.
- **Tools:** Compressor (envelope-follower based, own manual section) and beat-locked Oscilloscope with external-sidechain overlay.

**Use for house:** VolumeShaper is the cleanest no-routing alternative to sidechain compression for kick-ducked bass/pads (stock fallback: Ableton Compressor sidechain or Auto Pan); FilterShaper/WidthShaper add 16-bar filter and width builds; NoiseShaper's Duck mode lays breathing vinyl/air beds over tech-house grooves.

**Manual:** https://downloads.cableguys.com/Cableguys-ShaperBox-3-Manual.pdf (support page: https://cableguys.com/support/shaperbox)

---

## LFOTool + LFOTool_MFX (Xfer Records)

**What it is:** LFO shaping utility: applies drawable LFO curves to the incoming audio and can output MIDI CC to control other plugins/hardware. **LFOTool_MFX** is the companion "MIDI FX" build (introduced in v1.5, originally for Logic's MIDI FX slot) whose purpose is generating MIDI CC into an instrument placed after it, rather than processing audio.

**Main controls:** point-and-tension-curve LFO graph editor; **12 graphs per preset**, switchable by MIDI note or automation; up to **4 graphs active simultaneously**, assignable to **Cutoff, Resonance, Pan** (and volume/gain via the graph itself); *Rate* in BPM-sync (with swing) or Hz; sample-accurate sync; MIDI CC output; preset shapes menu. (Per-filter type list not published on the product page — check in-plugin; **(unverified)** beyond cutoff/res/pan/volume targets.)

**Use for house:** classic one-knob pump on bass/pad buses when you don't want real sidechain routing (stock fallback: Auto Pan in width-0 mode or Shaper in Live 12); tremolo-gate plucks and offbeat bass filtering at 124 BPM.

**Manual:** https://xferrecords.com/products/lfo-tool

---

## Movement (Output)

**What it is:** Rhythmic multi-FX "rhythm engine": two independent effect engines whose parameters are animated by four modulation sources ("Rhythms") per patch.

**Main controls (from the official User Guide):** 2 FX engines (A/B), each with its own Rhythms — a Rhythm is an **LFO** (12 waveshapes), a **step sequencer** (1–32 steps), or the **sidechain input's** envelope follower (*Gain, Attack, Release, Offset* controls); all rates host-synced from 8 bars down to 1/64; *Flux* lets one Rhythm's rate modulate the other's; up to **38 parameters** modulatable at once (marketing cites 76 knob targets / 152 via XY **(figures conflict; manual says 38)**); macro **XY pad** for performance; preset browser.

**Use for house:** drop it on static pads/vocal loops to add synced filter-width-space motion in one device; sidechain-input Rhythm gives groove-locked movement keyed to your kick.

**Manual:** https://output.com/app/uploads/2020/06/Movement_User_Guide.pdf

---

## Replika (Native Instruments) — free

**What it is:** Free delay (cut-down sibling of Replika XT). Confirmed free on NI's product page.

**Main controls:** three delay modes — **Modern** (pristine digital), **Vintage Digital**, **Diffusion** (reverb-like wash); stepped *Time* control through musical subdivisions; *Tone* (low/high tuning); modulation section (3 knobs + 2 buttons) switchable between a **phaser** and a **filter** (LP/HP/notch); stereo modes **normal / wide / ping-pong**. Feedback and mix knobs exist in-plugin **(not itemized on the product page — unverified wording)**.

**Use for house:** dub-style 1/4- and 1/8-dotted ping-pong throws on stabs and vocals (stock fallback: Echo/Delay); Diffusion mode doubles as a cheap pad-smearing pseudo-reverb.

**Manual:** https://www.native-instruments.com/en/products/komplete/effects/replika/

---

## Supermodal (Polyverse) — **not Native Instruments**

**What it is:** Modal filter plugin by **Polyverse Music** (the task's "NI?" guess is wrong). Uses hundreds of tuned bandpass filters to model resonant bodies, paired with a parallel state-variable filter.

**Main controls:** **27 modal modes** (9 models × 3 variations — physical bodies, flangers/phasers, vocal filters, mathematical resonators) with *Decay*, *Damping* and *Partials* controls; **SVF**: morph HP↔BP↔LP, 24 dB/oct, resonance past self-oscillation, *Drive*; *Blend* slider crossfades SVF↔modal; **4 modulation slots, 6 sources** (Meta knob, ADSR, envelope follower, sequencer, MIDI/CV trigger, randomizer), cross-modulatable, independent L/R; 200+ presets.

**Use for house:** vowel/body resonance sweeps on percussion loops and melodic-techno plucks that a normal filter can't do (stock fallback: Auto Filter, or Corpus for resonant-body color); envelope-follower mode gives talky grooving toplines.

**Manual:** https://polyversemusic.com/products/supermodal/

---

## Manipulator (Polyverse)

**What it is:** Granular pitch/formant/timbre mangler for monophonic audio (made with Infected Mushroom) — from subtle pitch correction/harmonizing to heavy vocal mangling. Zero-latency, real-time.

**Main controls:** 10 effects including **pitch shifter, formant shifter, harmonics shifter, sound smearing, granular alternator, pseudo-stereo**; **5 modulators**; real-time **MIDI input** to play pitch (up to 4-voice polyphony from a mono source). (Full per-knob list lives in the manual; FM/detune names **(unverified)**.)

**Use for house:** robot/alien vocal hooks and formant-shifted chant loops for melodic tech house; MIDI-play a one-word vocal into a new melody.

**Manual:** https://polyversemusic.com/products/manipulator/

---

## Wider (Polyverse) — free

**What it is:** Free stereo widener that is **fully mono-compatible** (phase cancels to the original mono signal on fold-down).

**Main controls:** single *Width* slider up to **200%** (100% = full stereo); v2.0 adds **low-frequency bypass** (keeps lows mono below a chosen frequency) and a **Mono** audition button.

**Use for house:** widen synth stabs, hats and pads without wrecking club mono PA fold-down — keep it off kick/bass (stock fallback: Utility width, with mono-low via Utility's Bass Mono).

**Manual:** https://polyversemusic.com/products/wider/

---

## Filtron (Polyverse) — free; **not an AIR plugin**

**What it is:** Free dynamic **12 dB state-variable filter** from Polyverse (identified via Polyverse/press — the inventory's AIR grouping is a mix-up). Morphs across lowpass → bandpass → highpass.

**Main controls:** filter type morph, cutoff/resonance; designed to be **modulated externally via its sidechain input** using CV-generator plugins such as Polyverse Gatekeeper (also in your inventory) — it has no deep built-in LFO of its own **(control-by-control list unverified; check the Polyverse manual)**.

**Use for house:** pair with Gatekeeper for CV-style synced filter grooves; otherwise stock Auto Filter does the everyday job.

**Manual:** https://polyversemusic.com/products/filtron/

---

## Comet (Polyverse) — confirmed: Polyverse reverb, not AIR

**What it is:** Reverb plugin by Polyverse ("unparalleled lushness"), aimed at vocals, melodic instruments and drums. The inventory's bare "Comet" is this — no AIR reverb of that name exists in the AIR catalog checked.

**Main controls:** **5 preset slots with morphing** between them, *Glide* (morph time), *Pre-Delay* (ms or synced subdivisions), **parameter locking** across presets, *Detune* algorithm, input-gain-driven **Saturation** module; every parameter automatable + MIDI/CV controllable. (Size/decay/color knob names not itemized on the page **(unverified)**.)

**Use for house:** morphing between a tight room and a huge wash as a transition effect (automate Glide into the drop); detuned shimmer on melodic-house leads (stock fallback: Hybrid Reverb).

**Manual:** https://polyversemusic.com/products/comet/

---

## MixBox (IK Multimedia)

**What it is:** Virtual **500-series-style rack/channel strip**: a resizable shell with **4 or 8 vertical module slots** in series, filled from ~**70 processing modules** adapted from T-RackS, AmpliTube and SampleTank. (Official product page returned 404 at scan time; details verified via the Sound On Sound review.)

**Main controls / module categories (10):** **Amps, Channel Strip, Delay, Distortion, Dynamics, EQ, Filter, Modulation, Reverb, Saturation.** Channel Strip modules are based on IK's 4000-series console emulations; dynamics include LA-2A/1176-style units. No internal patch cables or utility (M/S, splitter) modules. Module counts vary by source (70–77) **(exact current count unverified)**.

**Use for house:** quick lo-fi/color chains for sampled loops — filter + saturation + spring reverb in one window (stock fallback: an Ableton Audio Effect Rack of EQ Eight/Saturator/Echo).

**Manual:** https://www.ikmultimedia.com/products/mixbox/

---

## ADA Flanger (Plugin Alliance / Brainworx) — **not AIR**

**What it is:** Brainworx emulation of the A/DA Flanger analog pedal (endorsed by A/DA's founder), sold by Plugin Alliance. The inventory's AIR grouping is incorrect.

**Main controls:** *Threshold*, *Manual*, *Range*, *Speed*, *Enhance* (resonance); **even/odd harmonics** switch; 40:1 delay sweep ratio; plugin extras: *Wet/Dry Mix*, DAW **tempo sync**, toggle between **1979** and **2009-reissue** voicings.

**Use for house:** slow, deep jet-flange on percussion loops and white-noise risers (stock fallback: Phaser-Flanger in Live 12).

**Manual:** https://www.plugin-alliance.com/en/products/ada_flanger.html

---

## AIR Jura Chorus (AIR Music Technology)

**What it is:** Chorus effect based on the stereo chorus of AIR's Jura synth (i.e. the Juno-60's famous BBD chorus), "optimised for enhancing the sound of digital oscillators."

**Main controls:** two chorus modes — **Chorus I, Chorus II** — usable individually **or combined** (I+II), plus a *Mix* control. (Anything beyond that **(unverified)**.)

**Use for house:** instant analog width on Drift/Wavetable single-osc patches — the melodic-house pad trick in one click (stock fallback: Chorus-Ensemble).

**Manual:** https://www.airmusictech.com/ (effects catalog)

---

## Jura (AIR Music Technology) — instrument, for identification only

**What it is:** The separate "Jura" entry in the inventory is AIR's **Juno-60 synthesizer emulation** (2023) — an instrument, not an effect. Classic view mirrors the hardware panel; Expanded view adds a second envelope, extended LFO shapes, VCF saturation/drive, extended polyphony/unison/chord modes and a delay/reverb/3-band-EQ FX section, including the two-mode chorus with mix control. Covered here only to disambiguate it from AIR Jura Chorus.

**Manual:** https://www.airmusictech.com/virtual-instruments/jura/

---

## Formant (Minimal Audio) — free **(identification: most likely match)**

**What it is:** The bare "Formant" in the inventory best matches **Minimal Audio's free Formant** (Sept 2025): a formant shifter that moves a sound's resonant peaks without changing pitch, released as a teaser for their Evoke vocal suite. No other current plugin is named exactly "Formant" **(vendor identification probable, not certain — confirm in Live's browser info pane)**.

**Main controls:** central **XY pad** for formant character/shift; **tilt EQ** for darker/brighter balance. Internet activation required.

**Use for house:** cheap vocal-chop color — shift chopped vocal loops darker/brighter per section without re-pitching (stock fallback: Live 12 Shifter/simpler warp-formant tricks).

**Manual:** https://www.minimal.audio/ (product page; also https://www.pluginboutique.com/products/15630)

---

## Endless Smile (Dada Life) — **not DJ Swivel**

**What it is:** One-knob build-up effect by **Dada Life** (developed with Tailored Noise) — the task's DJ Swivel attribution is wrong. Turning the knob clockwise stacks filters, delays, reverbs, phasers/barber-poles and distortions into a rising build; snapping it back to zero is the drop.

**Main controls:** one big **Intensity** knob (readout 0–110%); preset menu ranging soft → extreme. VST2/VST3/AU; last update v1.3.0 (Oct 2022).

**Use for house:** automate Intensity over the 8–16 bars before every drop — purpose-built for exactly this (stock fallback: Auto Filter sweep + Echo feedback ride on a return).

**Manual:** https://dadalife.com/ (plugins page) **(official page not fetched — controls verified via press: MusicRadar/Mixonline)**

---

## Eternal Return (Dada Life) — identified: Dada Life, not Inear Display

**What it is:** Riser effect from Dada Life's **Secret Sauce** bundle (with Space In-Your-Face and Wide Awake): an endlessly rising Shepard-tone-style effect that "keeps rising forever" — great on noisy sources like snare build-ups.

**Main controls:** two knobs — **Amount** and **Pitch** (per DJ Mag and the Max for Live wrapper; rise speed is edited in the plugin window). Ultra-minimal UI by design.

**Use for house:** infinite-riser tension under 16-bar builds without ever resolving — layer under a snare roll; pull Amount to zero at the drop (stock fallback: Operator pitch-enveloped noise + Auto Filter).

**Manual:** https://dadalife.com/ **(official product page not fetched — controls verified via DJ Mag/MusicTech press)**

---

## RVRSE (SamuFL / Samuel Ferraz-Leite) — identified: not NoiseAsh, not Output

**What it is:** Free, open-source (MIT) **reverse-reverb riser** plugin: turns any one-shot into a tempo-synced reverse-reverb swell. VST3/AU/CLAP + standalone; pay-what-you-like, source on GitHub.

**Main controls:** *Length* (riser duration, 1/4 beat up to 16 beats); **stutter** effect. (Further knobs **(unverified)** — young plugin, thin documentation.)

**Use for house:** instant reverse-vocal/crash swells into downbeats — the classic tech-house transition without manual reverse-bounce workflow (stock fallback: reverse the clip + Hybrid Reverb, frozen & flattened).

**Manual:** https://www.kvraudio.com/product/rvrse-by-samufl (and the developer's GitHub/store)

---

## ThingsTexture = Things – Texture (AudioThing) — **not Baby Audio**

**What it is:** First plugin of **AudioThing's** "Things" series (the Baby Audio guess is wrong): a **granular reverb** with pitch shifting and mid/side mode, inspired by the soundtrack of the game *The Swapper*.

**Main controls (from the official manual):** *Balance* (granular ↔ reverb blend), *Mid/Side* mode (granular applied to Side only; reverb always on both), *Pitch* (grain pitch shift), *Diffusion*; newer versions add brightness/contrast-style tone controls **(tone-control naming unverified)**.

**Use for house:** shimmering granular washes behind melodic-house breakdowns; M/S mode keeps the center dry so the groove stays tight (stock fallback: Hybrid Reverb's shimmer algorithms).

**Manual:** https://www.audiothing.net/docs/AudioThing_ThingsTexture.pdf

---

## WaveObserver (Press Play) — free analyzer

**What it is:** Free oscilloscope / level-monitoring plugin (Wave Observer) for time-domain analysis, Win/Mac, VST/VST3/AU. A paid Pro tier adds AAX, selection analysis and themes.

**Main controls:** two observer modes — **envelope** (long-sweep dynamics) and **waveform** (cycle-stabilized single waveforms); zoom (1 sample/px up to 4 s per view); **freeze** with scroll-back history; peak level meter. Reported GPU/blank-window issues on some systems.

**Use for house:** check kick/bass phase alignment and sidechain ducking depth visually while tuning VolumeShaper/LFOTool curves.

**Manual:** https://kvraudio.com/news/press-play-releases-wave-observer---free-monitoring-plug-in-50506 **(official Press Play site not verified at scan time)**

---

## s(M)exoscope (Smartelectronix) — free oscilloscope

**What it is:** Classic free oscilloscope by Bram de Jong & Sean Evans (Smartelectronix); modern 64-bit/VST3 port by Armando Montanez (JUCE, 30 fps).

**Main controls:** time period (zoom) and amplitude; **trigger speed** and **retrigger threshold**; trigger modes incl. free/rising; fixed-size UI. (Complete knob list not officially documented — **(partially unverified)**.)

**Use for house:** eyeball kick transient shape and bass waveform symmetry when carving the kick-bass pocket; zero-cost alternative to ShaperBox's Scope.

**Manual:** https://www.kvraudio.com/product/s-m-exoscope-by-smart-electronix (original: http://bram.smartelectronix.com)
