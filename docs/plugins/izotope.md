# iZotope — verified plugin reference

Sources: official iZotope online manuals at docs.izotope.com (Ozone 11, RX 11, Neutron 4, Insight 2, Tonal Balance Control 2, Vinyl), the official Plasma manual PDF at docs.native-instruments.com, and official izotope.com product/learn pages (Vocal Doubler, Ozone Imager). Control descriptions are taken from these docs; anything not confirmable is marked "(unverified)". Researched 2026-10-12.

---

# Ozone 11 (mothership + component plug-ins)

Ozone 11 runs as a mothership (modules chained inside one plug-in, with Master Assistant) or as individual component plug-ins. Signal-chain modules below. Full manual: https://docs.izotope.com/ozone11/en/index.html

## Ozone 11 Maximizer

**What it is:** Ozone's IRC (Intelligent Release Control) brickwall loudness maximizer/limiter, with Upward Compress and Soft Clip as additional loudness stages. Full-bandwidth — not multiband.

**Main controls** (verified):
- **Mode:** IRC Low Latency (IRC 1 behavior, lowest latency/CPU); IRC 1 (psychoacoustic limiting — fast on transients to prevent pumping, slow on steady bass to prevent distortion); IRC 2 (like IRC 1 but preserves transients more); IRC 3 (most aggressive, psychoacoustic model, very CPU-heavy/high latency; Character styles: Clipping / Crisp / Balanced / Pumping); IRC 4 (spectral — limits only the frequency bands contributing to peaks, dozens of psychoacoustically spaced bands; most CPU-intensive; Character styles: Classic / Modern / Transient).
- **Gain:** pushes the signal into 0 dBFS where limiting begins (replaces the old Threshold — you turn Gain up instead of Threshold down).
- **Output Level:** maximum output of the Maximizer (renamed from Ceiling).
- **Gain/Output Link:** adjusting one moves the other inversely — hear limiting without the "louder is better" bias.
- **True Peak:** limiter accounts for inter-sample/analog peaks after D/A conversion (small CPU increase).
- **Character:** overall response time (attack/release), continuous 0.0 Clipping → 10.0 Very Slow, behavior depends on Mode.
- **Learn Input Gain + Target LUFS:** listens for 5 s and sets Gain so output loudness matches the Target LUFS (iZotope: not for loudness compliance).
- **Upward Compress (dB):** transparent parallel upward compression applied before the IRC limiter — boosts quiet sections by up to the set dB; level-matched so 0 dBFS peaks stay put.
- **Soft Clip:** pre-limiter clipper, 4x oversampled; Amount = wet/dry (100% = full clip at 0 dBFS); modes Light (saturates from −3 dBFS), Moderate (−9 dBFS), Heavy (−30 dBFS).
- **Transient Emphasis:** shapes/preserves transients (e.g. drums) before limiting; higher amount = more pronounced transients post-limiting.
- **Stereo Independence:** separate Transient and Sustain sliders (linkable) for how independently the limiter treats channels; 100% on both = louder but can narrow the image.
- **Views:** Spectrum Analyzer, Gain Trace (attenuation from top, Upward Compress boost from bottom), Gain Reduction meter. **Delta** in the header monitors limiter attenuation + Upward Compress/Soft Clip boost.

**Use for house:** The −9 to −11 LUFS stress test — push Gain until club loudness and listen for kick pumping; IRC 4 Modern or IRC 2 keeps the 4-on-the-floor transients intact, True Peak on, Output Level −1.0 dBTP for streaming masters. Add Upward Compress (1–3 dB) to lift hat/percussion detail in breakdowns without touching kick peaks.

**Manual:** https://docs.izotope.com/ozone11/en/maximizer/index.html

## Ozone 11 Clarity

**What it is:** Adaptive spectral processor using hundreds of bands to "maximize spectral power" — contours the spectrum toward flat noise, taming resonances and unmasking background content ("pulls the blanket off" dull mixes). iZotope's blind tests found it increases perceived loudness at identical integrated LUFS.

**Main controls** (verified):
- **Amount:** scales the spectral gain processing; at 100, max boost/cut is 6 dB.
- **Tilt (dB/oct):** the target the spectrum is contoured toward. 0 = pink noise; +3 dB/oct ≈ white noise (brighter); −3 dB/oct ≈ brown noise (darker).
- **Attack / Release (ms):** how fast Clarity reacts to incoming signal / returns to no gain change.
- **Difference Meter + Action Region:** EQ-style display of the adaptive tonal changes; processing constrainable with handles between 300 Hz and 20 kHz.
- **Header:** Delta monitoring; channel processing modes Stereo, Mid/Side, or Transient/Sustain.

**Use for house:** On a dull melodic-house master, 10–20 Amount with the action region above ~2 kHz opens pads/vocals without harshness — free perceived loudness before the Maximizer. Try Mid/Side mode to brighten only the sides and keep the center (kick/bass) untouched.

**Manual:** https://docs.izotope.com/ozone11/en/clarity/index.html

## Ozone 11 Stabilizer

**What it is:** Adaptive mastering EQ that reacts to incoming audio and applies frequency corrections to tonally balance the signal toward a target or tame resonances.

**Main controls** (verified):
- **Target:** target tonal balance profile (same profiles visible in Master Assistant; "All-purpose" is based on the Tonal Balance Control "Bass Heavy" curve). A reference-file target set in Master Assistant appears as an "Assistant" target, saveable as a module preset.
- **Mode:** **Shape** (boosts and cuts toward target, loudness-neutral — equal boost/cut) or **Cut** (only cuts resonances exceeding the target's upper bounds).
- **Amount:** scales the adaptive corrections; at 100, max boost is 9 dB.
- **Speed:** how fast corrections react; higher = more precisely timed but may introduce artifacts.
- **Smoothing:** contour of corrections in Shape mode — 100 looks like 3–4 filters, 0 like many filters; lower = more precise but riskier.
- **Sensitivity:** how often resonances are detected — 0 permits all but the most excessive; 100 suppresses any deviation from the target.
- **Tame Transients:** reacts instantly to tonally correct transient material.
- **Low / Mid / High Amounts:** scale processing below 100 Hz / 100 Hz–5.6 kHz / above 5.6 kHz.
- **Difference Meter** shows adaptive tonal changes; Delta in header is useful for hearing what Cut mode removes.

**Use for house:** Cut mode at low Sensitivity is a transparent resonance-tamer for busy tech-house drops (synth stab ring, cymbal buildup) — gentler than manual notches. Keep the Low amount down so it never wrestles your kick/bass tuning.

**Manual:** https://docs.izotope.com/ozone11/en/stabilizer/index.html

## Ozone 11 Low End Focus

**What it is:** Intelligently reduces muddiness and increases low-end impact — fixes low-end issues not easily improved with EQ or dynamics.

**Main controls** (verified):
- **Mode:** **Punchy** (faster response, emphasizes transient content) or **Smooth** (slower response, enhances sustained content).
- **Contrast:** spectral contrast between low- and high-level content in the action region. Positive = attenuates "out-of-focus" low-level content, brings out transients, punchier. Negative = blurs the low end like saturation / analog-compressor smoothing.
- **Gain:** makeup gain applied to the action region.
- **Difference Meter + Action Region:** adaptive EQ-style display; action region range 20–300 Hz, with cutoff handles, manual entry, and a **Solo** that isolates the pre-processing input inside the region.
- **Header:** Delta; Stereo, Mid/Side, or Transient/Sustain processing.

**Use for house:** Punchy mode + positive Contrast on the 30–120 Hz region separates kick attack from a rolling sub bassline when sidechain alone isn't enough; solo the action region to confirm you're only touching kick+bass. Negative Contrast can glue a too-clicky low end on deep-house cuts.

**Manual:** https://docs.izotope.com/ozone11/en/low-end-focus/index.html

## Ozone 11 Imager

**What it is:** Multiband (up to 4 bands) stereo width processor with vectorscope metering.

**Main controls** (verified):
- **Width (per band):** gain applied to side-channel content; positive widens, negative narrows, −100 makes the band effectively mono. Mono/effectively-mono input needs Stereoize enabled for Width to do anything.
- **Amount (header):** scales all band Widths 0–100% (0% = bypass all bands).
- **Link Bands:** move all Width controls together.
- **Stereoize:** adds mono-compatible synthesized width (only available when a band's Width is raised). **Mode I** = Haas-based decorrelation (delayed mid copy injected into sides); **Mode II** = newer alternative, different tonal quality, preserves transients better at higher settings. Plus Amount slider and power button.
- **Recover Sides:** when narrowing, recovers side information into the center instead of discarding it — gain offset + solo of the recovered signal.
- **Learn:** auto-places crossover points at spectral minima.
- **Views:** Crossover Spectrum, Correlation Trace (red = out of phase, white = in phase, post-Ozone output), Stereo Width Spectrum. **Vectorscope:** Polar Sample, Polar Level, Lissajous, plus Correlation meter bar (+1 top / −1 bottom; widening pulls it down) and Stereo Balance meter.
- Header channel modes: Stereo or Transient/Sustain.

**Use for house:** Classic club-safe move: 2–3 bands, lowest band (sub to ~120 Hz) Width −100 for mono low end, widen only above ~250 Hz (pads/hats +20–40); watch the correlation bar for mono compatibility on big systems. Recover Sides keeps energy when you mono the low band.

**Manual:** https://docs.izotope.com/ozone11/en/imager/index.html

## Ozone 11 Impact

**What it is:** Microdynamics processor — multiband (up to 4 bands) expansion/compression of a signal's microdynamics with one slider per band.

**Main controls** (verified):
- **Impact (per band):** positive = expands microdynamics (open, punchy); negative = compresses them (dense, glued).
- **Envelope:** time for the gain adjustment to return to baseline after a microdynamic event; in ms, or beat divisions when **Sync** (host-tempo) is enabled.
- **Auto-gain:** RMS-based automatic makeup per crossover band, keeping the gain traces' "center of mass" at 0 dB.
- **Link Bands:** adjust all band Impact amounts together.
- **Amount (header):** scales all band Impact 0–100%.
- **Stereo Link (header):** same adjustment to L/R based on mid-signal microdynamics; unlinked (default) works on elements in their stereo position.
- **Learn:** auto crossover placement; **Delta** monitoring; channel modes Stereo and Mid/Side.
- **Gain Traces:** scrolling per-band display of the microdynamic adjustment.

**Use for house:** Positive Impact on the kick/snare band with Envelope synced to 1/16 adds pump-free punch to a flat drum bus; slight negative Impact on the mid band glues stabs in a dense tech-house drop. Great "groove restorer" after heavy limiting upstream.

**Manual:** https://docs.izotope.com/ozone11/en/impact/index.html

## Ozone 11 Equalizer

**What it is:** Ozone's main mastering EQ — analog-matched filter shapes for warmth or digital linear-phase filters for surgical work, with node-based spectrum editing, Alt-Solo, and extra curves.
**Key controls:** per-node Filter Shape (incl. Vintage Low Shelf), Frequency, Gain, Q/Slope; Phase (Analog/Digital) options; channel modes incl. Mid/Side and Left/Right.
**Use for house:** Broad-stroke tonal shaping of the master — e.g. gentle low-shelf warmth and a 2–5 dB high-shelf air lift in M/S.
**Manual:** https://docs.izotope.com/ozone11/en/equalizer/index.html

## Ozone 11 Dynamic EQ

**What it is:** Node-based EQ whose bands move with the music — controls specific frequencies that are only sometimes too loud, with precision a static EQ can't match.
**Key controls:** per-node Filter controls + Threshold controls; dynamic mode direction (boost/cut); Global Filter Mode Analog (minimum-phase IIR) or Digital (linear-phase FIR, higher CPU); channel modes Stereo, Mid/Side, Left/Right, Transient/Sustain.
**Use for house:** Duck 200–350 Hz mud only when pads swell, or tame 2–4 kHz stab harshness only in the drop — leaves the rest of the track untouched.
**Manual:** https://docs.izotope.com/ozone11/en/dynamic-eq/index.html

## Ozone 11 Dynamics

**What it is:** Up to four bands of analog-modeled compression and limiting for mastering-grade dynamics shaping.
**Key controls:** per band Compressor + Limiter Thresholds (two handles), Ratio (compressor default 2:1, negative ratios = upward compression; limiter default 10:1), Attack, Release, Knee, Parallel (per-band dry/wet); Level Detection Peak / Envelope / RMS.
**Use for house:** Gentle 1.5–2:1 RMS-detection glue on the master bus, or a touch of upward compression on the low-mid band to thicken breakdowns.
**Manual:** https://docs.izotope.com/ozone11/en/dynamics/index.html

## Ozone 11 Exciter

**What it is:** Up to four bands of saturation with multiple harmonic modes.
**Key controls:** per-band Amount and Mix; Modes: Analog, Retro, Tape, Tube, Warm, Triode, Dual Triode; Oversampling (reduces aliasing, more CPU); Link Bands; Post Filter view.
**Use for house:** A few percent of Tape or Triode on the mid/high bands adds analog sheen to digital synth stacks; keep the sub band clean.
**Manual:** https://docs.izotope.com/ozone11/en/exciter/index.html

## Ozone 11 Master Rebalance

**What it is:** Machine-learning gain riding of Vocals, Bass, or Drums inside a finished stereo mix — no stems needed.
**Key controls:** Focus (Vocals / Bass / Drums, one at a time) and Gain for the focused element; blue focus vs. gray residual spectrum display.
**Use for house:** Rescue mastering jobs where the kick/bass sits 1–2 dB off and you can't get a new mixdown.
**Manual:** https://docs.izotope.com/ozone11/en/master-rebalance/index.html

## Ozone 11 Match EQ

**What it is:** Linear-phase matching EQ (over 8,000 bands) that captures a Reference spectrum snapshot and an Apply To snapshot, then builds the matching curve.
**Key controls:** Capture/Stop/Clear for both snapshots; Fine Tune: Smoothing (higher = less precise) and Amount; matched-curve low/high cutoff handles. iZotope recommends Amount under 50% — chase overall tonal shape, not an exact match.
**Use for house:** Snapshot a commercial tech-house reference (or your best release) and apply a smoothed, <50% match to pull a new master into the same tonal family.
**Manual:** https://docs.izotope.com/ozone11/en/match-eq/index.html

## Ozone 11 Spectral Shaper

**What it is:** High-resolution spectral attenuation of problem frequencies inside a variable full-spectrum action region (soothe-style smoothing for masters).
**Key controls:** Mode (Low/Medium/High intensity), Amount, Tone (spectral tilt of the processing, brighter/darker), Attack, Release; Learn auto-places the action region; Difference Meter + Gain Reduction Trace views; Stereo, M/S, Transient/Sustain.
**Use for house:** Tames fizzy hat/cymbal buildup or sharp synth air (6–12 kHz region) more gently than a static shelf cut.
**Manual:** https://docs.izotope.com/ozone11/en/spectral-shaper/index.html

## Ozone 11 Vintage Compressor

**What it is:** Emulation of a feedback compressor with a detection filter in the feedback loop, combining elements of classic analog units.
**Key controls:** Mode (Sharp / Balanced / Smooth), Threshold (soft knee in some modes), Ratio, Attack, Release (transient release; sustained compression releases slower), Gain, Auto Gain (adaptive RMS makeup); Detection Filter view.
**Use for house:** Slow, smooth 1–2 dB of color-glue on melodic house masters where the digital Dynamics module feels too clinical.
**Manual:** https://docs.izotope.com/ozone11/en/vintage-compressor/index.html

## Ozone 11 Vintage EQ

**What it is:** Emulated Pultec EQP-1A (top row) and MEQ-5 (bottom row) program EQs.
**Key controls:** EQP-1A: Low Freq 20/30/45/60/100 Hz with simultaneous Low Boost + Low Cut (the classic boost-then-dip trick), High Boost 3–16 kHz with interactive Q, High Cut shelf 5/10/20 kHz. MEQ-5: Low-Mid boost 200 Hz–1 kHz, Mid cut 200 Hz–7 kHz, High-Mid boost 1.5–5 kHz.
**Use for house:** The Pultec low trick at 30 or 45 Hz — boost and cut together — gives deep-house low end weight plus a mud dip in one move.
**Manual:** https://docs.izotope.com/ozone11/en/vintage-eq/index.html

## Ozone 11 Vintage Limiter

**What it is:** Limiter modeled after the Fairchild 670 for louder, fuller, analog-flavored masters.
**Key controls:** Mode (Analog = fast attack, tight bass, "thick"; Tube = balanced feedback limiting; Modern = vintage character blended with IRC limiting), Threshold, Ceiling (iZotope suggests −0.3 dB when dithering, −0.6 to −0.8 dB before MP3/AAC), Link, True Peak, Character (attack/release, Fast 0.0 → Slow 10.0).
**Use for house:** Character-stage limiting before the Maximizer, or the whole job on warmer, less loud deep-house masters.
**Manual:** https://docs.izotope.com/ozone11/en/vintage-limiter/index.html

## Ozone 11 Vintage Tape

**What it is:** Studer A810 two-track tape emulation — tape frequency response (magnitude + phase) and saturation without hiss/wow/flutter.
**Key controls:** Speed (7.5/15/30 IPS), Input Drive (internally level-compensated), Bias (negative = more HF distortion; positive = dynamic-range limiting flavor), Harmonics (even-order amount), Low Emphasis (head-bump gain, up to +10 dB), High Emphasis (default 4.0 ≈ flat; lower = HF rolloff, higher = shimmer).
**Use for house:** 15 IPS with a touch of Low Emphasis thickens drum-machine grooves; mind the head bump against your kick tuning.
**Manual:** https://docs.izotope.com/ozone11/en/vintage-tape/index.html

---

# RX 11 (modules / plug-ins)

Full manual: https://docs.izotope.com/rx11/en/index-en.html — per-module pages linked below. For a producer: these are your vocal-cleanup and sample-restoration toolkit.

## RX 11 Breath Control

Detects breaths in vocal/dialogue recordings by harmonic profile (not level-threshold based) and suppresses them. Controls: Gain mode (fixed dB reduction of every breath) vs. Target mode (reduces breaths down to a target dBFS level — more natural), Sensitivity, Output Breaths Only for auditioning.
Manual: https://docs.izotope.com/rx11/en/breath-control.html

## RX 11 Connect

Round-trips clips from your DAW to the RX Audio Editor and back ("Send for Repair") or one-way for analysis ("Send for Reference"). Plug-in only; the full-module offline editing happens in the RX app.
Manual: https://docs.izotope.com/rx11/en/rx-connect.html

## RX 11 De-click

Removes short impulse noises — digital clicks, mouth noises, phone interference, vinyl clicks. Controls: Algorithm (Single Band, Multi-band Periodic/Random, Low Latency for real-time), Sensitivity (how many clicks are detected), Frequency Skew, Click Widening, Output Clicks Only.
Manual: https://docs.izotope.com/rx11/en/de-click.html

## RX 11 De-clip

Repairs digital/analog clipping by interpolating waveform peaks above a threshold. Controls: Threshold (set just below the clip level, guided by the histogram meter), Threshold Link (asymmetric clipping), Suggest, Quality (Low/Medium/High), Makeup Gain, Post-limiter (true-peak, prevents >0 dBFS after repair).
Manual: https://docs.izotope.com/rx11/en/de-clip.html

## RX 11 De-crackle

Removes dense, low-level crackle (many close-together clicks) — run after De-click for best results. Controls: Quality (Low/Medium/High), Strength (amount detected and repaired), Amplitude Skew, Output Crackle Only.
Manual: https://docs.izotope.com/rx11/en/de-crackle.html

## RX 11 De-ess

Attenuates sibilance ("S/F/X/SH" sounds). Controls: Classic mode (broadband gain envelope) vs. Spectral mode (multiband, only attenuates the sibilant highs), Threshold (Relative-to-speech or Absolute dBFS), Cutoff Frequency, Spectral Flattening, Spectral Tilt, Speed (Fast/Slow).
Manual: https://docs.izotope.com/rx11/en/de-ess.html

## RX 11 De-hum

Removes tonal noise: AC hum, electrical buzz, EMF interference. Static mode (Base Frequency + Filter Q notches) for simple hums; Dynamic mode (Learn the full tonal profile, Adaptive option, Sensitivity, Bands, Filter Q, frequency range selectors) for complex buzz that overlaps speech.
Manual: https://docs.izotope.com/rx11/en/de-hum.html

## RX 11 De-plosive

Reduces mic pops/plosives (detected 20–80 Hz) while preserving voice fundamentals; use before any high-pass filter. Controls: Sensitivity (what counts as a plosive — bigger lever than Strength), Strength (reduction amount), Frequency Limit (upper bound, plosives usually 20–300 Hz).
Manual: https://docs.izotope.com/rx11/en/de-plosive.html

## RX 11 De-reverb

Reduces (or with negative values increases) room reverb based on detected wet/dry ratio. Controls: Learn (suggests settings from a reverberant selection), Reduction (target wet/dry — the main strength control), Reverb Profile (per-band amounts), Tail Length (≈RT-60), Artifact Smoothing.
Manual: https://docs.izotope.com/rx11/en/de-reverb.html

## RX 11 Dialogue Isolate

ML separation of speech from noise AND reverb (new in RX 11) into three components with independent Voice / Reverb / Noise gain faders, plus Sensitivity and Quality (Good/Real-time; Best/Offline is Advanced-only). Works on vocals in a pinch, though it's trained on dialogue.
Manual: https://docs.izotope.com/rx11/en/dialogue-isolate.html

## RX 11 Guitar De-noise

Three sections for guitar-specific noise: Amp (Learn + Sensitivity + Resolution for pickup/amp hum with hundreds of harmonics), Squeak (Sensitivity/Reduction/Duration for fret squeaks), Pick (Sensitivity/Reduction to soften pick attacks).
Manual: https://docs.izotope.com/rx11/en/guitar-de-noise.html

## RX 11 Monitor

Utility plug-in that routes the RX Audio Editor's playback through your DAW's audio driver (for hosts that monopolize the device — set Driver Type to RX Monitor in RX preferences). No processing controls.
Manual: https://docs.izotope.com/rx11/en/rx-monitor.html

## RX 11 Mouth De-click

Lighter de-clicker tuned for mouth noises/lip smacks over long selections. Controls: Sensitivity, Frequency Skew, Click Widening. Tip from the manual: two passes sometimes beat one.
Manual: https://docs.izotope.com/rx11/en/mouth-de-click.html

## RX 11 Repair Assistant

Analyzes audio (Voice or Music mode) via Learn and builds a suggested repair chain: Clean Up (De-noise via Dialogue Isolate, De-reverb, De-hum, De-click), Tone (Tilt/Scoop EQ, lo/hi-cut), De-Ess, plus per-section Audition buttons. Open Module Chain export is Advanced-only.
Manual: https://docs.izotope.com/rx11/en/repair-assistant.html

## RX 11 Spectral De-noise

The deep broadband/tonal noise reducer: Learn a noise profile (or Adaptive Mode for changing noise), then Threshold and Reduction — each split into Tonal and Noisy (random) parts — with Quality algorithms A–D. For hiss, HVAC, line noise, room tone in samples and field recordings.
Manual: https://docs.izotope.com/rx11/en/spectral-de-noise.html

## RX 11 Voice De-noise

Zero-latency de-noiser (64 psychoacoustic bands acting as a multiband gate) for voice. Controls: Adaptive mode or Learn (manual), Optimize for Dialogue vs. Music (Music mode doesn't attenuate sustained sung notes), Filter Type Surgical/Gentle, six Threshold Nodes + master Threshold, Reduction (max dB per band). Use this one live in the DAW; Spectral De-noise is heavier.
Manual: https://docs.izotope.com/rx11/en/voice-de-noise.html

## RX 11 Music Rebalance (ARA)

ML stem separation inside a mixed file: Vocal / Bass / Drums / Other gain faders with per-stem Mute/Solo, Sensitivity per stem, Quality Good/Better/Best, and Stem Split (renders four stems to tabs in the RX app). Available as ARA plug-in (VST3/AU) and AudioSuite/AAX. Perfect for flipping full-mix samples: pull the vocal or kill the drums before resampling.
Manual: https://docs.izotope.com/rx11/en/music-rebalance.html

---

# Neutron 4 Elements

**What it is:** The entry tier of Neutron 4 — the mothership's AI Assistant View for channel-strip processing on individual tracks. The Assistant analyzes the input and sets up processing; you steer with Intent controls. (Tier limitation per iZotope marketing: Elements lacks the full Detailed View module editing of Neutron 4 — unverified detail; the Intent controls below are verified from the official Neutron 4 manual.)

**Main controls** (verified, Assistant View):
- **Tone Match:** amount of static EQ matching + Sculptor processing toward the selected target or custom reference curve.
- **Punch:** Amount (below 100% = compression/consistency, above 100% = expanded, punchy dynamics), Attack, Sustain — driving Compressor 2's Punch mode.
- **Distort:** Drive, Processing Mode (Classic = subtle excitation, Trash = dramatic distortion, four modes each), XY Pad harmonic blend, Tone (−100 low-freq emphasis … +100 high-freq emphasis) — driving the Exciter.
- **Width:** global stereo width (I/O panel).
- **Target Library:** instrument targets + custom reference targets from your own audio files; Relearn re-runs the Assistant.

**Use for house:** Fast channel-strip starting points — drop it on a bass or stab bus, pick the instrument target, push Punch above 100% for drum groups. (Per the three-option rule: try stock Glue Compressor/Saturator first; Neutron earns its slot for the tone-match workflow.)

**Manual:** https://docs.izotope.com/neutron4/en/assistant/index.html (full manual: https://docs.izotope.com/neutron4/en/index.html)

# Insight 2

**What it is:** Full metering suite for mix/master monitoring.
**Main meters** (verified): Levels (true-peak + RMS per channel, up to 7.1.2), Loudness (ITU-R BS.1770: Integrated, Short-term, Momentary + Max, LRA, True Peak Max, broadcast/streaming target presets and custom targets), History (loudness traces over time), Spectrogram (up to 8 sources via Relay), Spectrum Analyzer, Sound Field (vectorscope + surround scope), Intelligibility meter (speech, via Relay), customizable Layouts.
**Use for house:** End-of-chain dashboard for the −9 to −11 LUFS club-master check: watch Integrated/Short-term LUFS, True Peak, and the vectorscope at once while A/B-ing against targets.
**Manual:** https://docs.izotope.com/insight2/en/index.html

# Tonal Balance Control 2

**What it is:** Spectrum meter that compares your track against genre target curves (factory or custom, built from a track or a folder of tracks).
**Main controls** (verified): target curve menu + custom curve creation (from audio file/folder; AIFF/WAV/MP3/M4A/FLAC/OGG); Broad View (four ranges: Low 20–250 Hz, Low-mid 250 Hz–2 kHz, High-mid 2–8 kHz, High 8–20 kHz) and Fine View; Crest Factor meter for low-end dynamics (left = too dynamic, right = too compressed); band Solo; band indicators turn white when in range; IPC links to Ozone/Neutron EQs so you can fix the balance from inside TBC.
**Use for house:** Build a custom curve from a folder of your favorite tech-house references and mix/master into it; the low-end Crest Factor meter tells you if kick+sub are over-squashed.
**Manual:** https://docs.izotope.com/tbc2/en/index.html

# Ozone Imager 2 (free)

**What it is:** Free single-band version of Ozone's Imager: stereo width up or down on any track, Stereoize for mono sources, three vectorscope meters.
**Main controls:** Width slider (negative narrows toward mono, positive widens); Stereoize with **Mode II** (subtle enhancement) and **Mode I** (colorful phasing effect) per the official product page; vectorscope metering (Polar Sample / Polar Level / Lissajous — per the Ozone module docs). No dedicated per-control manual is published for the free plug-in (unverified beyond the product page); control behavior matches the Ozone Imager module documented above.
**Use for house:** Track-level width rides where full Ozone is overkill — widen a mono synth hook with Stereoize II, or pull a loop's low end toward mono. Stock fallback: Ableton Utility (Width / Mono Bass).
**Manual:** product page https://www.izotope.com/en/products/ozone-imager.html ; module reference https://docs.izotope.com/ozone11/en/imager/index.html

# Vinyl

**What it is:** Free lo-fi vinyl simulation — turntable character, noise, and warp.
**Main controls** (verified): Decade (bandwidth-limiting filter eras, affects audio + dust/scratches), RPM (33/45/78 changes periodic rate of warp/dust/scratches, not pitch), Spindown (slowdown pitch drop), Lo-fi (vintage-sampler artifacts), Wear (HF rolloff + input-level-dependent distortion), Mechanical Noise / Electrical Noise gains, Dust Amount/Gain, Scratch Amount/Gain, Warp Amount + Warp Model, Input/Output gain (input gain drives the character).
**Use for house:** Lo-fi/deep-house texture: light Dust + Mechanical Noise on an intro so quiet bars aren't "digitally quiet," or Spindown as a transition FX into a drop. No factory presets — save your own via Live's rack.
**Manual:** https://docs.izotope.com/vinyl/en/index.html

# Vocal Doubler

**What it is:** Free natural vocal-doubling plug-in with a single interactive XY control.
**Main controls** (verified from iZotope's official learn article): **Amount** (level of the added doubles; dry always passes unless Effect Only); **Separation** (macro for spaciousness/stereo imaging — farther from center = wider); **Variation** (pitch + timing differences of the doubles, subtle to extreme); **Effect Only** switch (mutes the dry signal — use on a return track). iZotope suggests Amount under 100% with extreme Separation/Variation. No dedicated manual page exists (unverified beyond product + learn pages).
**Use for house:** Instant width on vocal chops and hooks without phasey chorus; Effect Only on a return lets you ride the double like a send. Stock fallback: Ableton Chorus-Ensemble or a Utility-width doubled track.
**Manual:** https://www.izotope.com/en/products/vocal-doubler.html (controls: https://www.izotope.com/en/learn/vocal-doubler-on-non-vocals)

# Plasma

**What it is:** Tube-style dynamic saturation driven by "Flux Saturation": the signal is split into many spectral bins; bins below the tuning-profile target get boosted and passed through an overdrivable tube-saturation circuit — harmonic enhancement where needed without distorting the rest.
**Main controls** (verified from the official manual):
- **Tuning Profile:** dropdown telling the spectral algorithm which frequencies to boost; four master-bus styles (Balanced, Bright, Warm, Scooped) plus many mix-element profiles.
- **Flux Saturate:** main amount knob, roughly in dB (X dB ≈ max boost per frequency); first half of range = subtle mastering moves, second half = radical tone shaping for mixing/parallel use.
- **Attack (ms):** how fast the spectral processor adapts — fast shapes transients, slow lets them through.
- **Release (ms):** return to baseline — long lingers, very fast gets "watery"/lossy-sounding artifacts.
- **Overdrive:** gain-staging into the non-linear tube stage; low = mostly clean, high = fuzzy distortion, blown-out transients.
- **Display section:** Channel Processing mode (Stereo, Mid/Side, Transient/Sustain — needs stereo instantiation), per-channel power/solo, Action Region handles (frequency bounds of Flux Saturation), Difference meter. Header: Delta, Bypass, Presets, Reset.
**Use for house:** Mix-bus or stab-bus "energy" tool — Warm profile + low Flux Saturate on a melodic house master, or Transient/Sustain mode to saturate only sustain for thicker pads while drums stay clean.
**Manual:** https://docs.native-instruments.com/pdf-guides/plasma/Plasma_Manual.pdf
