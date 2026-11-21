# Plugin workflow map — Zizz (tech house / melodic house, Live 12)

Every plugin here is in `inventory/plugins.txt` (2026-11-21 scan) or a stock
Ableton device marked "(stock)". Stock first per the three-option rule (`CLAUDE.md`);
descriptions follow `docs/plugins/` and `docs/eq-compressor-types.md`. Decapitone
unidentified, WaveShell contents unknown — see §16.

## Daily loadout (~90% of a session)

- **EQ Eight (stock)** — every cut, every channel, first.
- **Pro-Q 4** — when EQ Eight runs out (dynamic bands, M/S, spectrum grab).
- **soothe2** — harsh hats/vocal mids/synth fizz, automatically.
- **Glue Compressor (stock)** — drum bus and group glue, 2:1, 1–2 dB.
- **Pro-C 2** — clean channel compression with a proper sidechain.
- **Saturator (stock)** — "make it present" on any single sound.
- **Saturn 2** — multiband heat: drive bass mids, keep the sub clean.
- **Roar (stock)** — when saturation should be the sound design.
- **ShaperBox 3** — pump, filter motion, width rides, noise beds — one device.
- **ValhallaVintageVerb + ValhallaRoom** — the two return buses; **EchoBoy** the dub delay.
- **mvMeter2 (VU Standard) + Youlean** — 0 VU = −18 dBFS staging, LUFS/true-peak on the master.

---

## 1. Sound sources

Reach for this when a part needs an instrument — pick by how much design time the idea deserves.

First grab: **Operator / Wavetable / Analog / Drift (stock)** ⭐ — sketch there; move below when the patch needs more.

**Deep sound design**
- **Serum 2 (+ Serum)** — wavetable flagship; main lead/bass/pluck designer.
- **Vital** — free Serum-class wavetable; MPE and warp tricks.
- **Zebra2** — modular wireless synth; evolving cinematic pads and textures.
- **Voltage Modular (+ FX build)** — full modular rack when routing IS the idea.
- **FabFilter Twin 3** — polished subtractive synth with FabFilter modulation drag-and-drop.

**Analog character**
- **Diva** — the analog-sounding one; movie-grade filters for melodic-house bass/pads (CPU-heavy).
- **AIR Jura** — Juno-60 recreation: pads + the famous chorus = half the genre.
- **UAD PolyMAX** — lush '80s poly pads/chords that sidechain beautifully.
- **TyrellN6 / Surrealistic MG-1 Plus** — free VA color: Tyrell is the "mini Diva" (bass/stabs), MG-1 the raw Moog mono.

**Fast preset-players**
- **Nexus** — instant pluck/stab/lead presets + trance gate; layer and resample.
- **Analog Lab V** — all Arturia V Collection presets behind macros.
- **SynthMaster One** — wavetable presets with a strong built-in arp.
- **SyndtSphere / Astra** — free morphing-sphere pads; Splice's multi-engine sketch synth (overlaps Serum).

**Keys & acoustic**
- **Keyscape** — flagship pianos/EPs; the expensive keys.
- **Addictive Keys** — Studio Grand / CP-80 / Mark One; fast classic deep-house keys.
- **AIR Velvet / MiniGrand** — Rhodes/Wurli models (straight into RC-20); light piano stabs.
- **KORG M1** — THE M1 piano/organ presets; instant 90s house.

**Samplers & platforms**
- **Simpler/Sampler/Drum Rack (stock)** ⭐ — default for any sample.
- **Kontakt 7/8** — library player for third-party instruments.
- **Splice INSTRUMENT + LABS** — free organic textures/pads; LABS now lives inside Splice INSTRUMENT.
- **Lunacy CUBE** — 3D vector sampler; self-moving breakdown pads (automate Orbits).
- **AIR Hybrid 3** — workhorse VA+wavetable poly; Serum/Diva come first.

**UJAM performers & Usynth**
- **Usynth (USYNTH)** — one plugin hosts all Titles; check the Title switcher — DRIVE and FLUID are house/melodic-techno packs.
- **Groovemate ONE (GM-ONE)** — humanized shaker/clap grooves; drag the MIDI out and reskin.
- **Virtual Bassist ROWDY (VB-ROWDY)** — picked live-bass phrases; indie-dance flavor only.

Also on disk: **FabFilter One** (basic one-osc synth; teaching tool), **Retromulator** (discoDSP hardware-synth emulator — needs ROM dumps, little use without them).

## 2. EQ

Reach for this when something is wrong (cut), inconsistent (dynamic), or merely dull (character). Taxonomy: `docs/eq-compressor-types.md`.

First grab: **EQ Eight (stock)** ⭐ — all surgical cuts, HPF junk, mud at 200–400.

**Wrong → fix (transparent)**
- **Pro-Q 4 (also Q2/Q3)** — deluxe surgical: dynamic bands, M/S, collision view, spectrum grab.

**Problem comes & goes (dynamic)**
- **soothe2** — automatic resonance/harshness finder; delta-listen before trusting it.
- **TDR Nova** — free 4-band dynamic EQ; the "duck 6–9 kHz only when hats spike" tool.
- **Ozone 11 Dynamic EQ** — mastering-grade dynamic bands on the 2-bus.

**Nicer (character): lows — punch — shine — group**
- **Ozone 11 Vintage EQ** — Pultec: boost+cut same low freq = bigger AND cleaner kick/bass.
- **LOVEND** — free one-knob low-end lift (60–180 Hz) when a kick/bass is just thin.
- **NI Solid EQ** — SSL-console punch; angry boosts for drums/synths that sound polite.
- **Maag EQ2** — Air Band shelf (10–40 kHz): sheen without harshness on hats, vocals, 2-bus.
- **MIXROOM** — target-curve EQ (320 Hz–20 kHz); match leads/pads/bus to a reference fast.

**Creative filters (motion, not correction)**
- **Auto Filter (stock)** ⭐ — every sweep and build first.
- **Volcano 3 (+2)** — four modulated vintage-voiced filters; serious filter sound design.
- **Supermodal** — modal/body resonance sweeps a normal filter can't do (vowels, physical bodies).
- **Simplon / FabFilter Micro** — tiny 2-filter / 1-filter utilities for quick jobs.
- **Filtron** — free Polyverse SVF built to be driven by Gatekeeper's CV.

## 3. Compressors — the seven hands

Reach for this when level needs controlling; pick the hand by job, not brand.

First grab: **Compressor / Glue Compressor (stock)** ⭐ — clean channel work and bus glue.

- **FET (lightning, aggressive):** **UAD 1176** — clap smack, parallel drum energy, all-button crush.
- **Opto (slow, invisible):** **UAD LA-2A** — vocal/bass leveling, 3–5 dB, never pumps. (Century's opto leveler: one-knob version.)
- **VCA-bus (glue):** **Glue Compressor (stock)** ⭐ 2:1, 1–2 dB; **NI Solid Bus Comp** is the same SSL G unit — prefer Glue.
- **VCA-snap (drum punch):** **stock Compressor** hard-knee/fast; **NI VC 160** for the dbx-style kick/snare crack; **NI Solid Dynamics** adds a gate in the same strip.
- **Vari-mu (thick tube):** **RoyalCompressor** — mixbus/pad density, 1–2 dB; HOLD modes level without pumping.
- **Digital clean:** **Pro-C 2** — control without color, best-in-class sidechain; **KrystalComp** free spare with SC EQ. Gates: **Pro-G** (stock Gate ⭐ first).
- **Multiband:** **OTT** — the melodic-techno pad sound, Depth 20–30%; **Pro-MB** surgical; **Ozone 11 Dynamics** for mastering; **KrystalField** free up+down density.

**Character blends & one-knobs:** **FirePresser** (four classic comps on one pad — fast colored bus comp), **Supercharger** (one-knob tube fattener for percussion/claps), **Neutron 4 Elements** (AI channel strip; Punch >100% on drum groups).

## 4. Saturation & distortion — heat scale

Reach for this when a sound needs harmonics: warm = invisible, hot = audible, burning = the point. One deliberate saturator per path.

First grab: **Saturator (stock)** ⭐ — Soft Sine low drive = warm; cranked curve = hot.

**Warm (busses, refinement)**
- **HG-2** — the king: Density + Air on drum bus / 2-bus for analog weight, "expensive".
- **UAD 610-A/B / Century** — tube preamp color per track (hot Level, Output pulled down); Century adds HPF + air + opto in one strip.
- **SDRR2tube / Saturation Knob / Little Radiator** — free/cheap tube rounding and parallel grit.
- **LUX Sub-Bass** — 12AU7 low-end warmth so a sub reads on small speakers.
- **Plasma** — spectral tube saturation only where energy is missing; mix-bus "life".

**Hot (main mixing level)**
- **Saturn 2 (+ Saturn)** — multiband: saturate bass MIDS only, sub stays clean — the small-speaker trick.
- **Fresh Air** — free dynamic exciter; opens dull tops smoother than a shelf.
- **FireCharger** — one-knob spectral energy + tape warmth on dull loops.
- **SausageFattener** — two knobs of fat on a drum bus; watch the output gain.

**Burning (sound design)**
- **Roar (stock)** ⭐ — 3 stages, multiband/M-S routing, feedback: growls, builds, destruction.
- **Cyberdrive Core** — multi-mode distortion for aggressive stab color.
- **Electrum / Bassment Cores, UAD Showtime amp** — amp sims for lo-fi amp color on keys/chops/bass.

(Decapitone: unidentified — do not use until verified; see §16.)

## 5. Transients & punch

Reach for this when attack got soft (post-compression) or a loop is too roomy.

First grab: **Drum Buss (stock)** ⭐ — transients + crunch + boom in one device.

**Detector shapers (threshold-free attack/sustain)**
- **SPL Attacker Plus** — one knob of snap on kicks/claps; built-in peak catch.
- **Trinity Shaper** — Attack/Body/Sustain, multiband + sidechain EQ; the surgical one.
- **NI Transient Master / HelperTransients2** — simple attack/sustain reshaping of loops.

**Curve/LFO tools:** **ShaperBox 3 (VolumeShaper) / Gatekeeper / LFOTool** — hand-drawn punch and duck curves; see §9.

**One-knob punch**
- **UrbanPuncher** — Punch + Saturation (+ Destroy) for parallel-style kick/clap weight.
- **KSHMR Essentials Kick** — Sub/Pressure/Tape kick strip before fine EQ.

## 6. Clippers & limiters

Reach for this when peaks must be shaved (clip) or walled (limit) — loudness is a dynamics job.

First grab: **Limiter (stock)** ⭐ for the wall; **Saturator Hard Clip (stock)** for quick shaving.

**Clippers (shave peaks, keep density)**
- **KClip3** — the mastering/drum-bus clipper: 8 modes, multiband, LUFS target.
- **KNOCK Clipper** — per-track drum clip, hard↔soft curve, never over 0 dB.
- **GClip / FreeClip / Mesa Lite / KrystalClip** — free utility clips for single hits and quick jobs.

**Limiters (the ceiling)**
- **Pro-L 2 (+ Pro-L)** — main mastering limiter; styles + true-peak + loudness metering.
- **Ozone 11 Maximizer** — IRC limiting + Soft Clip + Upward Compress; the −9…−11 LUFS stress test.
- **Ozone 11 Vintage Limiter** — Fairchild flavor for warmer, less loud masters.
- **FireMaximizer** — morphs clipper/saturator/limiter/multiband; fast club premasters.

## 7. Reverbs

Reach for this when a sound needs a place to live. Returns, not inserts, for anything shared.

First grab: **Hybrid Reverb (stock)** ⭐ — convolution + algo covers most single-track jobs.

**Two-return bus recipe:** Return A = ValhallaRoom (Dense/Large Room, 0.3–0.8 s) for drums/percussion glue;
Return B = ValhallaVintageVerb (Concert Hall, 2–4 s, 1980s color) for pads/leads/vocals — both 100% wet, low-cut ~250 Hz.

**Workhorse spaces**
- **ValhallaRoom** — realistic rooms; Bass Mult <1× keeps lows clean under a 4/4 kick.
- **ValhallaPlate** — vocal/clap plate; Chrome or Copper, 20–30 ms predelay.
- **Pro-R 2 (+ Pro-R)** — musical decay-rate EQ; the "surgical" reverb when a tail must be sculpted.

**Vintage character**
- **ValhallaVintageVerb** — flagship 80s-hardware color; first-call pad/synth verb.
- **Comet** — morphing reverb (5 preset slots + Glide); automate the morph into a drop.

**Creative & freeze**
- **ValhallaShimmer** — +12 st pitch-shimmer lift for breakdowns.
- **ValhallaSupermassive** — free huge FDN clouds and swells (Pleiades/Sirius).
- **NI Raum** — creative reverb with Freeze; pad-tail risers.
- **ThingsTexture** — granular reverb, M/S mode keeps the center dry.
- **HyperspaceCore / Space In-Your-Face** — free XY-morphing algo verb for percussion/FX; Dada Life two-knob instant big wash.

## 8. Delays

Reach for this when a part needs echo, groove or dub space.

First grab: **Echo (stock)** ⭐ — character delay with modulation and reverb built in.

**Character**
- **EchoBoy** — THE dub box: Space Echo style, ping-pong 1/8-dotted, Groove/Feel locks to the pocket.
- **EchoBoy Jr** — seven styles, zero menu-diving; slapback and quick throws.
- **ValhallaDelay** — tape/BBD/Ghost modes; Duck modes keep repeats out of the groove automatically.

**Clean-modern**
- **Delay (stock)** — simple sync delays.
- **Replika** — free pristine digital / vintage digital / diffusion wash; cheap ping-pong throws.

**Creative-modulated**
- **Timeless 3 (+ Timeless 2)** — modulated delay sound design; everything modulates everything.
- **ValhallaFreqEcho** — free frequency-shift echo; barberpole dub sirens.
- **ValhallaUberMod** — 32-tap modulated delays; also the string-ensemble/chorus monster (§9).

## 9. Motion & modulation

Reach for this when static parts need movement — pump, filter rides, width, builds.

First grab: **Auto Pan / Compressor sidechain (stock)** ⭐ for pump; **Chorus-Ensemble / Phaser-Flanger (stock)** ⭐ for mod color.

**Sidechain-pump (no-routing ducking)**
- **Kickstart 2** — one-knob pump; the instant answer on bass/pads.
- **ShaperBox 3 (VolumeShaper)** — drawable curves, 3 bands, audio-trigger; the precise answer.
- **LFOTool** — classic curve pump + MIDI-switchable graphs (12 per preset).
- **Gatekeeper** — sample-accurate trance gates and hand-drawn duck curves; CV/MIDI out drives Filtron.

**Filters:** Auto Filter (stock) ⭐, then §2's creative filters (Volcano 3, Supermodal, Filtron).

**Chorus / flanger / phaser**
- **AIR Jura Chorus** — the Juno BBD chorus as a device; instant analog width on single-osc pads.
- **Retronaut Core** — vintage chorus/vibrato with tape wow; melodic-house keys.
- **ValhallaUberMod** — Dimension-style stereo and Solina string ensembles.
- **ADA Flanger / ValhallaSpaceModulator** — deep analog jet flange on percussion/noise risers; free barberpole sweeps.
- **Orbitron Core** — six-mode modulator for generic pad/top movement.

**Rhythmic multi-FX:** **Movement** — two FX engines animated by LFOs/steps/sidechain; one-device groove-locked motion on static loops.

**Risers & builds**
- **Endless Smile** — Dada Life one-knob build; automate Intensity over 8–16 bars, snap to zero at the drop.
- **Eternal Return / RVRSE** — infinite Shepard riser under snare rolls; tempo-synced reverse-reverb swells from any one-shot.
- **Power Grid Disruptor** — hold-to-build Disrupt button + glitch patterns + impacts.
- **UJAM Finisher MICRO** — free one-knob 25-mode multi-FX; automate Amount into drops.

## 10. Stereo width & imaging

Reach for this when something is too mono — never on kick/bass; always check mono fold-down.

First grab: **Utility (stock)** ⭐ — Width + Bass Mono covers most of it.

- **Ozone Imager 2** — free track-level width ± with Stereoize for mono sources.
- **Ozone 11 Imager** — multiband width on the master; low band −100 = mono sub, widen above ~250 Hz.
- **Wider** — free, fully mono-compatible 200% width with low-frequency bypass.
- **Wide Awake** — Dada Life drastic rainbow-stereo; pads/tops only, check mono.
- **ShaperBox 3 (WidthShaper/PanShaper)** — width and Haas-pan rides that move with the track.

## 11. Vocal tools

Reach for this when a vocal (or chop) needs tuning, repair, character or placement.

First grab: **stock chain** ⭐ — EQ Eight → Compressor → sends (Auto Shift for rough scale-tuning).

**Tune**
- **Auto-Tune Artist** — real-time: Retune 0 = the hard effect; 20–50 + Flex-Tune = transparent.
- **Melodyne** — offline note-level repair (no ARA in Live: use Transfer); fix one sour note, re-pitch sampled chords.

**Repair (RX 11 suite)**
- **De-ess / Breath Control / De-click / De-plosive** — daily vocal cleanup (also **Pro-DS** for pro de-essing).
- **Voice De-noise** (zero-latency, in-DAW) / **Spectral De-noise** (deep, offline) — hiss and room tone.
- **De-reverb / Dialogue Isolate / Music Rebalance** — dry out roomy recordings; pull the vocal out of a full-mix sample.

**Character**
- **LittleAlterBoy** — formant down = deep-house vocal color; Quantize + Drive = pop hook effect.
- **Manipulator** — granular pitch/formant mangling; robot/alien hooks, MIDI-playable.
- **Formant** — free formant XY shifting of chops per section.
- **LUX Vocal Preamp** — free one-knob 12AX7 tube warmth before the chain.

**Doubler:** **Vocal Doubler** — free natural doubling; Effect Only on a return.

**Strips:** **UAD Century** (HPF + air + opto in one pass for chops), **QuickVox Core** (quick polish — the full chain outclasses it), **LANDR FX Voice** (sketch presets only).

## 12. Lo-fi & texture

Reach for this when clean is boring — intros, breakdowns, "analog" movement on loops.

First grab: **Vinyl Distortion + Erosion + Redux (stock)** ⭐ — Live's lo-fi kit.

- **RC-20 Retro Color** — the go-to: noise + wobble + degrade; automate Magnitude for "tape dying" transitions.
- **iZotope Vinyl** — free turntable noise/warp/spindown; quiet bars stop being digitally quiet.
- **UJAM Finisher RETRO** — 50 decade-themed modes, one knob; section-to-section vibe changes.
- **ShaperBox 3 (CrushShaper/NoiseShaper)** — synced bitcrush and breathing vinyl/air beds.

## 13. Sound design & mangling

Reach for this when the sample IS the instrument and it needs to become something else.

First grab: **Roar / Shifter / Corpus / Spectral Resonator (stock)** ⭐ — Live 12's mangling kit.

- **Manipulator** — granular pitch/formant/harmonics smearing (see §11).
- **ShaperBox 3 (TimeShaper/PitchShaper)** — scrubs, stutters, tape-stops, drawn pitch rides.
- **Supermodal / ThingsTexture** — resonant-body filtering as sound design; granular washes from any source.
- **MixBox** — 500-series rack (~70 modules); quick filter+sat+spring chains on loops.
- **LANDR FX Bass / Beats / Electric** — one-dial preset color for sketching; rebuild keepers with real tools.

## 14. Metering

Reach for this always — meters run while everything else gets decided. Workflow numbers first.

First grab: **mvMeter2 "VU Standard" preset** ⭐ — 0 VU = −18 dBFS; ride every channel/bus to ~0 VU.

- **Youlean Loudness Meter 2** — mixdown: True Peak ≤ −5 dBFS on the master; master: −9…−11 LUFS short-term stress test on the drop, TP alerts.
- **SPAN** — free spectrum: M/S view for sub-mono discipline, correlation ≥ 0 for club PA safety.
- **REFERENCE** — level-matched A/B vs 2–3 pro tech-house tracks; per-band level/width/punch.
- **MiniMeters (+ module plugins)** — second-screen dashboard via the Audio Server plugin; VU Cal'd to −18.
- **Insight 2** — all-in-one end-of-chain dashboard (LUFS, TP, vectorscope) during the club-master check.
- **SIENNA ROOMS / GURU** — headphone room/speaker emulation, last on the master — ALWAYS bypass before export.

## 15. Mastering suite

Reach for this at the end — after the mix passes the §14 numbers. Ozone 11 modules by job:

First grab: **stock EQ Eight → Glue → Limiter** ⭐ for quick club bounces; Ozone for real masters.

- **Tone:** **Equalizer** (broad strokes, M/S) · **Vintage EQ** (Pultec low trick) · **Stabilizer** (adaptive balance, Cut mode = resonance tamer) · **Match EQ** (<50% toward a reference).
- **Dynamics:** **Dynamics** (1.5–2:1 RMS glue) · **Dynamic EQ** (duck mud/harshness only when it appears) · **Vintage Compressor** (color glue) · **Impact** (microdynamic punch restorer).
- **Low end:** **Low End Focus** — Punchy + positive Contrast separates kick attack from rolling sub.
- **Top & air:** **Exciter** (Tape/Triode on mid/high bands) · **Clarity** (free perceived loudness, action region >2 kHz) · **Spectral Shaper** (fizzy cymbal buildup).
- **Width:** **Imager** (mono the low band; see §10).
- **Rescue:** **Master Rebalance** — ride vocals/bass/drums inside a finished stereo file.
- **Ceiling:** **Maximizer / Vintage Limiter** (see §6) — Output −1.0 dBTP.
- **Target check:** **Tonal Balance Control 2** — custom curve from a folder of tech-house references; Crest Factor meter polices kick+sub squash.

**Bus chains:** **The God Particle** (Jaycen Joshua mix-bus chain — hit the green input target, bypass other 2-bus dynamics), **MixBoss** (top-down sketch glue with mono/car/phone checks).

## 16. Utilities & unidentified

Reach for this for plumbing, analysis and housekeeping.

First grab: **Utility (stock)** ⭐ — gain, width, phase, mono.

- **Sonalksis FreeG** — long-throw fader + RMS/peak metering for honest gain staging between devices.
- **s(M)exoscope / WaveObserver** — free oscilloscopes: kick transient shape, kick+sub phase, duck-depth checks.
- **Splice Sounds / Sounds Listener / SpliceBridge** — in-DAW sample search, search-with-sound, key/tempo-matched previews (needs active Splice plan).
- **Reason Rack Plugin** — Reason's rack as a plugin; a whole second toolbox when its devices are wanted.
- **GatekeeperMIDI / LFOTool_MFX / SynthMaster1FX / MiniMeters Audio-Server / RX 11 Connect & Monitor** — companion/host builds of plugins above, not separate tools.
- **Waves StudioRack for OBS** — streaming-side only; irrelevant inside Live.
- **Decapitone** — UNIDENTIFIED vendor (user-folder install, not confirmed to be Soundtoys Decapitator). Do not use on sessions until verified in Live's GUI.
- **WaveShells 15.5–17.1** — containers only: which Waves plugins are licensed is unknown. Check the Live browser before recommending any specific Waves device.
