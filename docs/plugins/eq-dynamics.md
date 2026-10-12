# EQ, dynamics & transient tools — verified reference

Sources: official vendor pages/manuals (oeksound, Tokyo Dawn Labs, Plugin Alliance, Mastering The Mix, W.A. Production, United Plugins, Native Instruments, Polyverse, Dharma Worldwide, Sonalksis, Krystal Dynamics via KVR/MuseHub listings, Luxora Audio via press). Anything not confirmed in official documentation is marked "(unverified)". Researched 2026-10. UrbanPuncher and iZotope/FabFilter tools are covered in other docs.

> **Identification notes (binder names → real products):**
> - **Mixboss** = **W.A. Production MixBoss** (top-down mixbus plugin, made with engineer Emrah Celik) — *not* AudioThing.
> - **RoyalCompressor** = **Royal Compressor** by **SounDevice Digital, published by United Plugins** (vari-mu emulation) — *not* W.A. Production.
> - **FirePresser / FireCharger / FireMaximizer** = **FireSonic** brand, published by **United Plugins** — *not* W.A. Production.
> - **HelperTransients2** = **W.A. Production Helper Transients 2** — confirmed.
> - **TBTECH Trinity Shaper** = **Three-Body Technology Trinity Shaper**, distributed by **Plugin Alliance** — confirmed.
> - **KSHMREssentialsKick** = **KSHMR Essentials Kick**, sold/distributed by **Dharma Worldwide (Dharma Studio)**; press reports it was developed by W.A. Production to KSHMR's spec (development credit unverified on the official page).
> - **KrystalComp / KrystalClip / KrystalField** = **Krystal Dynamics**, a free indie plugin project by a solo developer ("Nick", Patreon-funded) — not Fuse Audio Labs or Krotos. Docs are thin: KVR/MuseHub listings only.
> - **LUX Sub-Bass** = **Luxora Audio Lux Sub-Bass** (free, released Aug 2025). Same vendor as the "LUX Vocal Preamp" in the inventory (Luxora "Lox/Lux Vocal Preamp").
> - **GatekeeperMIDI** = a second installed component of Polyverse Gatekeeper that accepts MIDI note input in hosts that can't route MIDI to audio-effect plugins (unverified — Polyverse's manual documents only one plugin with DAW-side MIDI routing).

---

## soothe2 (oeksound)

**What it is:** Dynamic resonance suppressor. Detects and attenuates harsh/resonant frequencies in real time with narrow self-adjusting notches — not a static EQ, not a conventional compressor. (Note: oeksound's site now redirects to soothe3; the soothe2 manual remains online.)

**Main controls** (all verified from the official manual):
- **soft/hard mode** — soft is more transparent and less level-dependent; hard is more powerful and level-dependent. Depth behaves differently per mode.
- **depth** — how much processing is applied; acts like sensitivity/threshold. Not an absolute dB amount; range extends well past typical use.
- **sharpness** — how deep and narrow the cuts are; higher = deeper, narrower notches (too high can add artifacts).
- **selectivity** — which resonances get suppressed; higher targets only the most prominent resonances, lower cuts almost everything.
- **attack / release (speed section)** — reaction and recovery speed of the notches; displayed values are reference constants (actual timing is frequency-dependent). Slower release can reduce phase-distortion artifacts.
- **stereo section** — mid/side or left/right mode; **stereo link** (100% = summed analysis, identical processing; 0% = dual mono); **stereo balance** (processing weight per channel).
- **quality section** — **oversample** (increases frequency resolution of the reduction filter; helps lows and high sharpness), **resolution** (eco/high/ultra refresh rate of detection; eco ≈ half CPU but can artifact), separate **offline rendering quality**, **quality lock** (keeps quality when switching presets).
- **sidechain** — external input drives detection (reduction follows the sidechained signal), with headphone listen; inputs must be time-aligned.
- **output** — **mix** (wet/dry), **trim** (gain-compensates wet signal for A/B), **delta** (hear only what's being removed; right-click locks across presets), soft **bypass**.
- **sensitivity curve / bands** — low cut + high cut with selectable slopes, plus 4 bands (peaking, low/high shelf, band shelf, band reject, tilt). Works like an inverse/sidechain EQ: boosted areas get processed more. Per band: on/off, **band listen** (solo the band's delta), freq, **sens** (processing weight), Q, stereo balance, curve type.
- Also: A/B states with copy, undo/redo, hidden automatable **input trim**, resizable GUI.

**Use for house:** The go-to for harsh hi-hats/rides, resonant vocal mids and whistly synth tops — soft mode, moderate depth, check with delta. Also tames boxy loop resonances before EQ. Stock fallback: EQ Eight narrow cuts or Live 12 "EQ + dynamics via Compressor sidechain EQ" can only approximate it statically.

**Manual:** https://www.oeksound.com/manuals/soothe2

---

## OTT (Xfer Records)

**What it is:** Free 3-band upward *and* downward compressor — a recreation of Ableton's aggressive "OTT" Multiband Dynamics preset. Current version 1.37 (free).

**Main controls:** Xfer publishes no manual; the official freeware page lists only downloads/version. Controls below are the plugin's UI labels, confirmed by multiple press descriptions but **(unverified against official docs)**:
- **Depth** — overall intensity; effectively a dry/wet of the multiband processing.
- **Time** — scales attack/release of all bands together.
- **In Gain / Out Gain** — drive into the compressor (more in = more squash) and output level.
- **Upward / Downward ("Upwd"/"Dnwd")** — separate amounts for upward and downward compression across the bands.
- **Per-band gains (H/M/L)** — output level per band, draggable band thresholds on the display.

**Use for house:** Melodic techno/house pads and plucks that need that dense, glossy "everything forward" sound; parallel on hats or full synth bus at low Depth. Stock fallback: Multiband Dynamics "OTT" preset — it's literally the original.

**Manual:** https://xferrecords.com/freeware (support: https://support.xferrecords.com)

---

## TDR Nova (Tokyo Dawn Labs)

**What it is:** Free parallel dynamic equalizer: parametric EQ layout where every band also has a full dynamics section. Covers parametric EQ, dynamic EQ, frequency-selective compression, multiband and wideband compression.

**Main controls** (verified from official page + manual):
- **4 dynamic bands** — per band: Frequency (10 Hz–40 kHz), Q, Gain (±12 dB, applied after dynamics detection), Shape (low-shelf / bell / high-shelf).
- **Per-band dynamics** — Threshold button (enables dynamics; ALT+click = STICKY mode, ignores wideband compression), Threshold knob, Ratio, Attack, Release; **SPLIT** gives the band its own independent detector listening to its own bandwidth (off = follows the wideband detector).
- **W-Band (wideband) section** — gain ±12 dB plus its own Threshold/Ratio/Attack/Release for the signal outside the bands.
- **HP/LP filters** — on/off, FREQ, slopes in seven steps 6–24 dB/oct (band slopes up to 72 dB/oct per the product page).
- **Quality** — Eco (~100 kHz internal bandwidth), Precise (default, ~200 kHz), Precise+ (adds internal nonlinearity); "always render at highest quality" option.
- **Monitoring/output** — **GR DELTA** (hear only what the dynamics are doing), band solo, analyzer source In/Out/SC/Off, external sidechain, **EQ auto gain**, OUT GAIN with equal-loudness marker, **DRY MIX** (100% = bypass), Sum/Diff (M/S) and L/R processing, A/B, presets, undo/redo.

**Use for house:** Dynamic de-harsh on hats (band at 6–9 kHz that only ducks when they spike), controlling a bass note that booms on one pitch, or gentle mastering-style tonal riding. Stock fallback: EQ Eight (static) or Multiband Dynamics.

**Manual:** https://docs.tokyodawn.net/nova-manual/ (product: https://www.tokyodawn.net/tdr-nova/)

---

## Mäag Audio EQ2 (Plugin Alliance)

**What it is:** Official plugin of Mäag Audio's EQ2 hardware: a two-band boost-only EQ built around the famous **Air Band** shelf, with a more flexible low/mid bell than the EQ4.

**Main controls** (verified from the Plugin Alliance page):
- **INPUT ATTN** — input attenuator, 0 to −12.5 dB (normalize the signal before boosting).
- **LMF SWITCH** — bell width: up = tight bell (red), down = wide bell (white).
- **LMF SELECTOR** — bell frequency: Sub, 40, 57, 65, 88, 150, 220, 250, 400 Hz, 1 kHz, 1.4 kHz.
- **LMF GAIN** — boost up to +12 dB (tight) / +15 dB (wide).
- **AIR BAND** — boost-only shelf at 2.5, 5, 10, 15, 20 or 40 kHz (frequencies below the shelf peak are also affected).
- **AIR BAND GAIN** — +12 dB (at 40 kHz) up to +17 dB (at 2.5 kHz).
- **BAND IN/OUT** — switches each band in/out of the circuit.

**Use for house:** Air Band at 15–40 kHz for silky top on vocals, ride loops and master-bus sheen without harshness; LMF at 40–88 Hz to fatten a kick/bass. Stock fallback: EQ Eight high shelf (digital, less flattering) or Saturator + shelf.

**Manual:** https://www.plugin-alliance.com/en/products/maag_eq2.html

---

## MIXROOM (Mastering The Mix)

**What it is:** Intelligent EQ for the 320 Hz–20 kHz range (companion to BASSROOM for lows). Analyzes your audio against genre/instrument target curves or your own reference tracks and suggests EQ moves, visualized as bands in a 3D "room".

**Main controls** (verified from the official manual page):
- **Presets / Target EQ Curve** — pick a genre or instrument preset (bottom-left); a green target curve appears, built from the accumulated analysis of your audio ("Reset Targets" restarts it).
- **Custom targets** — import up to 20 reference tracks; analyze a chosen section (e.g. the drop).
- **Add Smart Bands** — auto-loads bands that match the target curve (appears after ~3 s of analysis; differences under ±0.5 dB ignored).
- **Bands** — gain by moving a band forward/back in the room; frequency 320 Hz–20 kHz; draggable Q; solo, bypass, delete; high-shelf/bell toggle on bands above 1.6 kHz.
- **Modes** — **MIX** (surgical: >4 dB, narrow Q) vs **MST** (mastering: <4 dB, broad Q, limits enforced); **LIN** (linear phase) vs **MIN** (minimum phase).
- **Mid/Side** — per-band M, S or stereo blend (drag the stereo icon).
- **Output** — bypass (icon warns if EQ shifts loudness >2 dB), output gain slider with **level-match pointer** for gain-matched A/B; A/B with copy; ±2/4/8/12 dB display range; audio-input heat-map; gain scale 0–200%.

**Use for house:** Fast tonal matching of leads/pads/vocals to a melodic-house reference; MST mode on the mixbus for broad polish. Stock fallback: EQ Eight by ear against a reference (REFERENCE/SPAN for metering).

**Manual:** https://www.masteringthemix.com/pages/mixroom-manual

---

## MixBoss (W.A. Production)

**What it is:** Mixbus ("top-down mixing") processor developed with engineer Emrah Celik: multiband compressor, enhancer, EQ, tonal-balance tool and limiter in one, meant on the mix bus before you mix individual tracks.

**Main controls** (verified from the official product page):
- **Multiband compressor** with linear-phase crossovers; **Control** knob = master dry/wet of compression; low/mid/high LED activity meters.
- **Enhance** knob with three combinable modes: **Color** (saturation), **Depth** (front-to-back spatial enhancement), **Wide** (stereo widening).
- **Push EQ** — musical EQ, switchable pre/post compression.
- **Balance** — nudges tonal balance toward a profile derived from top-charting songs.
- **Mixbus limiter** — loudness without heavy distortion.
- **Mix** — parallel blend; plus 4x oversampling, polarity flip, input/output controls.
- **Monitoring simulations** — Grotbox (small speaker), Car, Phone, Mono checks, gain-matched.
- A/B, undo/redo, presets, resizable GUI.

**Use for house:** Light top-down glue and tone on the mixbus while sketching (Control low, Enhance subtle); the mono/car checks are handy for club translation. Stock fallback: Glue Compressor + EQ Eight + Utility (mono) on the master.

**Manual:** https://www.waproduction.com/plugins/view/mixboss (PDF manual linked from product page)

---

## Supercharger (Native Instruments)

**What it is:** Free one-knob tube compressor from the KOMPLETE line. (The paid Supercharger GT adds Gentle/Punch/Slam characters, saturation types Mild/Moderate/Hot, mid/side, sidechain filter.)

**Main controls** (verified from the NI product page):
- **Compress** — the macro knob: adds compression, harmonic saturation and presence while auto-compensating make-up gain (set input gain once first).
- **Punch** — button; adds detail/emphasis to transients (press describes it as a slower-attack behavior).
- **Dirt** — button; extra saturation layer for aggressive, overdriven sounds.
- Input trim, output level (±20 dB) and wet/dry **Mix** are documented in NI's Supercharger GT manual; the free Supercharger's exact extra controls beyond Compress/Punch/Dirt are **(unverified)** on the product page.

**Use for house:** Quick fattening of percussion loops, claps and tops — Compress + Punch for snap; Dirt for gritty parallel drums. Stock fallback: Compressor or Glue Compressor + Saturator.

**Manual:** https://www.native-instruments.com/en/products/komplete/effects/supercharger/ (GT manual: https://docs.native-instruments.com/online-guides/supercharger-gt-manual/en/overview)

---

## Royal Compressor (SounDevice Digital / United Plugins)

**What it is:** Vari-mu (valve) compressor modeled from three hardware units of a famous Beatles-era British vintage compressor; the three units' differences became three selectable models in one plugin.

**Main controls** (verified from the official documentation):
- **Input** — input gain; 0 = 0 dB, 10 = +24 dB (drives compression amount, vari-mu style).
- **Model A/B/C** — Model A: slowest attack (70 ms), cleanest; Model C: fastest (17 ms), most colourful.
- **Recovery** — stepped release, 6 (slowest) to 1 (fastest), plus five red **HOLD** positions (holds compression to the latest peak, very long release).
- **Saturation** — valve saturation independent of compression amount; 100% = character of the original hardware.
- **Autogain** — auto output compensation as input gain changes.
- **Trim** (0 to −100 dB) and **Output Attenuator** — level calibration and output volume.
- **Mix** — dry/wet (applied after Input, before Saturation); **Phase** — phase-linear mode (adds latency); gain-reduction meter; power/bypass.

**Use for house:** Warm glue on vocal or music buses; HOLD settings give smooth, pumping-free leveling on pads. Stock fallback: Glue Compressor (slow attack, auto release) + Saturator.

**Manual:** https://unitedplugins.com/RoyalCompressor/documentation

---

## FirePresser (FireSonic / United Plugins)

**What it is:** Multi-compressor that runs four classic analogue-style compressor emulations in a blendable chain. The official page calls them "iconic classic units" without naming the hardware (any specific identification would be unverified).

**Main controls** (verified from the official page):
- **Rainbow Pad** — one X/Y-style control setting how strongly each of the four compressors contributes.
- **Compressor order** — drag the compressor labels to reorder the chain.
- **Detector** — opens advanced settings for all engaged compressors at once.
- **Turbo** — adds more overall squash.
- **Wet/Dry** — parallel blend (recommended after loading a preset); analogue-style saturation is part of the engines; resizable GUI; presets.

**Use for house:** Drum-bus or vocal compression when you want blended "best of several comps" color fast; Turbo + Wet/Dry for parallel drum crush. Stock fallback: Compressor → Glue Compressor in series.

**Manual:** https://unitedplugins.com/FirePresser/

---

## FireCharger (FireSonic / United Plugins)

**What it is:** Intelligent spectral dynamic processor + tape-style saturator + high-frequency exciter; analyzes the track and pushes it toward an "ideal" spectral energy. Usable on the mixbus or single tracks.

**Main controls** (verified from the official page):
- **Anodize** — amount of spectral "charge"/energy the track gains.
- **Magnetize** — vintage tube tape-machine saturation for warmth.
- **Tone** — high-frequency dynamic exciter (brightens the top).
- **Dry/Wet** — how radical the overall change is; resizable GUI.

**Use for house:** One-knob life/sheen on dull loops, samples or a flat premaster; gentle Anodize on a synth bus. Stock fallback: Saturator + EQ Eight high shelf (or Spectral Resonator for creative cases).

**Manual:** https://unitedplugins.com/FireCharger/

---

## FireMaximizer (FireSonic / United Plugins)

**What it is:** Loudness maximizer that morphs between four algorithms — clipper, saturator, limiter and multiband limiter — to balance aggression vs transparency. Aimed at mastering, also usable on drums/guitars/vocals.

**Main controls** (verified from the official page, which names few parameters):
- **Algorithm blend** — continuous blend across clipper / saturator / limiter / multiband limiter (an X/Y pad-style control; exact parameter names not listed on the page — **(unverified)**).
- **Oversampling** — up to 16x.
- 64-bit processing, smart bypass, auto-sleep during silence, resizable GUI.

**Use for house:** Loudness on club premasters or crushing a drum bus where you'd otherwise chain clipper+limiter. Stock fallback: Saturator (clip mode) into Limiter.

**Manual:** https://unitedplugins.com/FireMaximizer/

---

## Gatekeeper + GatekeeperMIDI (Polyverse)

**What it is:** Sample-accurate volume modulation plugin — gate, trance-gate/envelope sequencer and volume-automation tool with click-free smoothing. Made with Infected Mushroom.

**Main controls** (verified from the official page and manual):
- **8 independent volume envelopes**, each MIDI-programmable; up to 1024 nodes per sequence (patterns up to ~20 hours); 31 envelope brush/curve types; 4 copy slots; shortcut editing system.
- **Grid/Rate** — 1 bar down to 1/128, dotted/triplet/swing, or TIME mode in seconds; envelope speed 0.1x–10x; AutoPlay syncs to host tempo; tempo-mapped looping; **Sustain Loop** (holds loop until note release, legato for overlaps); **Envelope Mode** (moving a node shifts following nodes); **Trigger** button.
- **SMOOTH** slider — removes clicks/pops while staying punchy.
- **Boost x10**, **Input Volume** (up to +12 dB), **Clip selector** (Off / Clip / Soft Clip).
- **PAN** per envelope (drivable from the MIDI Modulation Panel).
- **MIDI Note Learn** — restrict an envelope to specific keys (responds to any note if none learned).
- **CV output** (unipolar/bipolar, for modular) and **MIDI CC output** per envelope (CC 119 program change, CC 123 all-notes-off, CC 120 panic).
- **GatekeeperMIDI:** not documented as a separate product in the official manual — MIDI triggering is done by routing MIDI in the DAW (the manual notes that in Ableton only the VST2 handles MIDI I/O fully). The separately installed "Gatekeeper MIDI" component is the variant that accepts direct MIDI note input in hosts that need it **(unverified)**.

**Use for house:** Precise trance-gate chops on pads/vocals, sidechain-style ducking curves drawn by hand (tighter than Auto Pan), and rhythmic FX builds. Stock fallback: Auto Pan (sidechain trick), Shaper (MPE) in Live 12, or volume automation.

**Manual:** https://polyversemusic.com/docs/gatekeeper-manual/ (PDF: https://polyversemusic.com/downloads/manuals/Gatekeeper%20Manual.pdf)

---

## SPL Attacker Plus (SPL / Plugin Alliance)

**What it is:** One-knob transient designer "Microplug" — the attack half of SPL's Transient Designer, using Differential Envelope Technology (level-independent: boosts attack regardless of input level, no threshold to set).

**Main controls** (verified from the Plugin Alliance page):
- **Attack** — single knob; amount of transient punch/edge added.
- **Soft peak limiter** — built-in, with gain-reduction meter (catches the boosted peaks).
- **Dry/Wet** — parallel blend.
- Toolbar: undo/redo, A/B/C/D setting banks, reset; scalable UI. No frequency selection or output control is documented.

**Use for house:** Add snap to kicks, claps and percussion loops that got soft after compression; Dry/Wet keeps it natural. Stock fallback: Drum Buss "Crunch/Transients" or Compressor with slow attack.

**Manual:** https://www.plugin-alliance.com/en/products/spl_attacker_plus.html

---

## Helper Transients 2 (W.A. Production)

**What it is:** Simple transient shaper from W.A. Production's free/cheap "Helper" series: boost or cut attack and sustain independently, with channel-mode and filter options.

**Main controls** (verified from retailer listings carrying vendor copy — W.A.'s own page for this product was not reachable; treat exact ranges as **(unverified)**):
- **Attack** — amplification or attenuation of the transient.
- **Sustain** — amplification or attenuation of the sustained portion.
- **Processing mode** — original signal or its Mid, Side, Left or Right component.
- **Low-pass / high-pass filters**, **input and output gain**.

**Use for house:** Reshape sampled drum loops — pull sustain down to dry out roomy percussion, push attack on toppy hats. Stock fallback: Drum Buss or Multiband Dynamics transient tricks.

**Manual:** https://www.waproduction.com (product listing: https://www.pluginboutique.com/products/3338-Helper-Transients-2)

---

## Trinity Shaper (Three-Body Technology / Plugin Alliance)

**What it is:** Transient shaper that adds a third stage — **Body** — between the usual Attack and Sustain, so you can tune the core/tail of a sound separately from its transients. Released via Plugin Alliance (2024).

**Main controls** (verified from Plugin Alliance/Sound On Sound coverage of the official release):
- **Attack / Body / Sustain** stages — Body adjusts the core and tail independently of transients.
- **Single-band or multiband mode** — multiband splits into three bands, each with its own Attack, Body and Sustain.
- **8-band parametric sidechain EQ** (functions from Kirchhoff-EQ), with internal, external, mid/side and L/R routing.
- **Built-in limiter with soft clipper**; waveform display.
- **ADAA** (anti-derivative anti-aliasing) and 2x/4x/8x/16x oversampling.

**Use for house:** Surgical drum shaping — e.g. keep the kick's click, fatten its body, shorten the tail; multiband mode for full loops. Stock fallback: Drum Buss + Multiband Dynamics.

**Manual:** https://www.plugin-alliance.com/products/trinity-shaper

---

## KSHMR Essentials Kick (Dharma Worldwide)

**What it is:** Free "lite" version of the KSHMR Essentials channel-strip suite, containing its Kick bank: a one-panel processor to make kicks bigger and punchier, with KSHMR's own presets/guidelines. Sold/distributed on Dharma Studio; press reports the code was developed by W.A. Production (unverified on the official page).

**Main controls:**
- Kick bank per the official Dharma page: **Sub** (adds low end), **Mid**, **Air** (high-mid/presence shaping), **Pressure** (multiband compression), **Tape** (subtle saturation).
- Press coverage of the free Kick version also lists **Trans** (transient sizing) and a **stereo width** control, for eight parameters total **(unverified on the official page)**.
- Suite-wide (official page): one-knob macro operation, auto-gain, clipping controls, L/R and M/S auditioning.

**Use for house:** Quick glue/weight on a tech-house kick before fine EQ — Sub for weight, Pressure for density, Tape to round the click. Stock fallback: EQ Eight + Saturator + Glue Compressor on the kick.

**Manual:** https://www.dharmaworldwide.com/product/kshmr-essentials-plug-in

---

## KrystalComp (Krystal Dynamics)

**What it is:** Free "precision digital compressor" for mixing/mastering (VST3/AU, macOS/Windows) by Krystal Dynamics, a solo-developer free-plugin project (Patreon-funded). No formal manual exists; details from the developer's KVR/MuseHub listings.

**Main controls** (per official KVR listing, v1.1.2):
- Threshold, Ratio, Attack, Release, **Hold**, variable **Knee**.
- **RMS or Peak detection**; input and makeup gain; **automatic loudness matching**; **Mix** (parallel).
- **Internal/external sidechain** with a sidechain EQ (low-pass, high-pass, bell) and sidechain audition button.
- Real-time waveform display; input/output/GR meters.

**Use for house:** Clean utility compression on bass or vocals where you want a free, transparent digital comp with SC filtering. Stock fallback: Ableton Compressor (which also has sidechain EQ).

**Manual:** https://www.kvraudio.com/product/krystalcomp-by-krystal-dynamics/details (vendor: https://www.patreon.com/krystal_dynamics)

---

## KrystalClip (Krystal Dynamics)

**What it is:** Free clipper for peak control and harmonic coloration (VST3/AU).

**Main controls** (per MuseHub/press listings; MuseHub page was not directly reachable — **(partially unverified)**):
- Multiple distinct clipping algorithms (listings vary between three and four).
- **Delta** button (hear what's removed) and **LUFS metering** (added in recent versions).

**Use for house:** Shave kick/drum-bus peaks before the limiter for louder, denser club mixes. Stock fallback: Saturator in clip mode, or Limiter.

**Manual:** https://www.musehub.com/plugin/krystalclip

---

## KrystalField (Krystal Dynamics)

**What it is:** Free "mastering-grade dynamic processor": dual engines doing downward and upward compression simultaneously (OTT-adjacent but single-band, mastering-oriented). VST3/AU.

**Main controls** (per official KVR listing, v1.1.0):
- **Dual processors** for simultaneous downward + upward compression; target-based **threshold** controls; unified **attack/release**; independent **ratio** and **knee** per direction.
- Detection modes: **RMS, Peak, LOUD**; automatic makeup gain; **Mix** (parallel); **lookahead** up to 20 ms.
- **Low-frequency sidechain bias**; **hard/soft clipping** modes; bypass for A/B; GR + short-term LUFS metering; waveform display; themes.

**Use for house:** Gentle density on a melodic-house mixbus or stem — upward compression lifts pad tails without squashing transients. Stock fallback: Multiband Dynamics (single band, upward+downward) or Glue Compressor.

**Manual:** https://www.kvraudio.com/product/krystalfield-by-krystal-dynamics/details

---

## Lux Sub-Bass (Luxora Audio)

**What it is:** Free low-end saturation plugin (released Aug 2025, VST3/AU/AAX) built around a 12AU7 tube emulation, for bass, 808s and drum buses; from the same vendor as the Lux/Lox Vocal Preamp (12AX7) in the inventory. Powered by Luxora's "Hyper Technology Engine". No official manual found; details from press (Bedroom Producers Blog, GearNews) and the KVR listing.

**Main controls** (from press coverage — **(unverified)**, vendor publishes no manual):
- **Saturation** — tube-style low-end depth/warmth.
- **EQ section** — preset sub-shaping curve, can be engaged/bypassed, helps prevent mud.
- Input level implied (push the input for more drive); built-in oversampling (not user-facing). Press notes high CPU usage with EQ engaged.

**Use for house:** Thicken a rolling tech-house bass or sub so it reads on small speakers. Stock fallback: Saturator (sine-ish shaper, low drive) or Roar on the sub band.

**Manual:** none published — https://www.kvraudio.com/product/sub-bass-by-luxora-audio / https://bedroomproducersblog.com/2025/08/04/luxora-audio-fre/

---

## FreeG Mono / Stereo (Sonalksis)

**What it is:** Free high-resolution gain fader/metering utility — a long-throw channel fader with pro metering, in mono and stereo versions. Useful anywhere you need clean gain staging or an extra fader point (e.g. post-insert level rides).

**Main controls** (verified from the official page and KVR release notes):
- **Master fader** (large, long-throw) with **Fine** mode for sensitive calibration.
- **Trim** — coarse input-level adjustment; range configurable in preferences.
- **Pan** (with selectable **pan law**), **Mute**, **Phase flip**, bypass; mono-compatibility option.
- **Metering** — peak meter with superimposed instantaneous **RMS** bar; multiple ballistic types; peak and RMS readouts; **Pre/Post** metering (Pre = pre-fader/pre-pan/pre-trim input).

**Use for house:** Gain-staging between devices (keep −6 to −18 dB headroom into saturators/comps) and automating level rides without touching the mixer fader. Stock fallback: Utility — FreeG only earns its slot for the metering and long-throw fader.

**Manual:** https://sonalksis.com/freeg.html
