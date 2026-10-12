# Flagship synths & samplers — verified reference

Sources: official product pages and vendor copy — Xfer Records (xferrecords.com), u-he (u-he.com),
Vital Audio (vital.audio), Spectrasonics (spectrasonics.net), Native Instruments
(native-instruments.com), Arturia (arturia.com), Cherry Audio (cherryaudio.com).
Anything not confirmed on an official page is marked **(unverified)**. Verified 2026-10-12.

---

## Serum 2 (Xfer Records)

**What it is**
Xfer's flagship wavetable synth, expanded in v2 into a multi-engine synth (wavetable,
multisample, sample, granular, spectral). Free upgrade for Serum 1 owners, with lifetime
free updates. Ships with 626+ presets and 288 wavetables.

**What 2 added over Serum 1:** new Multisample, Granular and Spectral oscillator engines,
an expanded Sample engine, smooth wavetable interpolation and new warps, flexible FX
routing, an arpeggiator, and a clip sequencer.

**Architecture / main sections**
- **Oscillators — five engine types:**
  - **Wavetable:** Smooth Interpolation mode for "near-infinite frame positions"; filtering,
    FM, PD, ring mod, distortion; new warps, with dual warps on the main oscillator types.
  - **Multisample:** plays real-instrument multisamples (bundled orchestral/choir/piano/guitar
    library); supports user multisamples in the open SFZ format.
  - **Sample:** FM/PD/distortion, looping with snap loop detection, loop modulation, Rate
    control for tape-stop effects, slicing, tails mode.
  - **Granular:** granular texture engine (new in 2).
  - **Spectral:** real-time resynthesis of samples at the harmonic level with transient
    detection (new in 2).
- **Filters / envelopes / LFOs:** carried over from Serum's drag-and-drop modulation design —
  specific v2 counts/types not detailed on the product page (Serum 1 baseline: 3 env,
  8 LFOs, mod matrix — **(unverified for v2)**).
- **FX & sequencing:** flexible effect routing, arpeggiator, clip sequencer.

**Use for house**
The tech house bass default — wavetable warps + FM for growly, clicky basslines; spectral/
granular engines for texture one-shots and transition FX.

**Manual:** https://xferrecords.com/products/serum-2

---

## Diva (u-he)

**What it is**
u-he's zero-delay-feedback analog-modeling synth: mix-and-match oscillator/filter/envelope
modules taken from "classic hardware synthesizers," either as faithful single-synth setups
or hybrids. Widely regarded as a benchmark for analog authenticity.

**Architecture / main sections**
- **Oscillators — 5 models:** Triple VCO (three oscs, continuous waveform shape), Dual VCO
  (multi-waveform, PWM, sync, FM), DCO (pulse + saw + sub + noise summed), Dual VCO Eco
  (CPU-light, ring mod, no PWM/FM), Digital (multisaw and warpable waveforms).
  (The page does not name the hardware sources; the commonly cited Minimoog/Jupiter/Juno/
  MS-20/JP-8000 lineage is **(unverified)**.)
- **Filters — 5 ZDF models:** Ladder (24 dB, switchable 12 dB), Cascade (cleaner, rough/clean
  switch), Multimode (HP/BP/LP), Bite (Sallen-Key, two revisions), Uhbie (2-pole state-variable).
- **Envelopes:** two slots (amp + filter), three ADS(S)R models, keyboard follow, velocity.
- **LFOs:** two, host-syncable, multiple waveforms, restart/phase controls.
- **Trimmers & Modifications:** per-osc detune, voice variance/drift, glide; modulation
  processors (invert, quantize, rectify, lag, multiply, add).
- **FX:** two stereo slots — chorus (3 modes), phaser (2 modes), plate reverb, delay, rotary.
- **Voice/quality:** poly up to 16 voices, duophonic, mono, legato; host-syncable arpeggiator;
  oscilloscope; adjustable quality settings (incl. draft) with separate offline/bounce quality.

**Use for house**
First call for analog melodic house leads, warm Juno-style pads, and rounded mono basses —
run high quality on bounce, draft while writing.

**Manual:** https://u-he.com/products/diva/ (user guide PDF linked on page)

---

## Zebra2 / Zebra Legacy (u-he)

**What it is**
u-he's "wireless modular" synth: a semi-modular where modules are patched on a grid with no
cables and appear only when used. The current "Zebra Legacy" edition bundles Zebra2, all
commercial Zebra2 soundsets, ~400 "Zebra Oldies" presets, and ZebraHZ (The Dark Zebra —
Hans Zimmer edition).

**Architecture / main sections**
- **Oscillators:** 4 wavetable oscillators, 16 waves each, with integrated spectral effects;
  Wave Editor for drawing/morphing waveforms; unison 1/2/4/11 voices with detune + stereo spread.
- **FM oscillators:** 4 FMOs with 8 alternative waveforms, "closely related to the famous
  Yamaha DX7."
- **Filters:** 4 VCFs with 23 modes + 4 cross-modulation filters (XMF, 15 types).
- **Comb filters:** Comb module with 8 modes and internal impulse generator (3 waveforms) —
  physical-modeling building block.
- **Envelopes:** 4 expanded ADSRs (extra sustain/loop/release options, 6 time bases,
  3 curve modes) + 4 syncable MSEGs with up to 32 segments.
- **LFOs:** 4 per-voice + 2 global, 8 waveforms plus user mode.
- **Modulation:** 12-slot matrix with depth modulation from a second source.
- **Grid:** 4×12 main patching grid (four lanes, signal flows top to bottom) + 3×6 FX grid.
- **Perform:** 4 assignable XY pads, each controlling up to 16 parameters.
- **FX:** 21 stereo effects (incl. 2× chorus/flanger, 2× delay, 2× EQ, 2× compressor, 2× reverb).
- **ZebraHZ extras:** 8 Diva-style filters, 4 comb modules, 8 MSEGs, 24 mod-matrix slots,
  4 polyphonic compressors, 3 resonators.

**Use for house**
Evolving melodic-techno pads, cinematic atmospheres and plucks — the MSEGs + XY pads make
long 16/32-bar motion easy.

**Manual:** https://u-he.com/products/zebralegacy/

---

## Vital (Vital Audio)

**What it is**
Matt Tytel's "spectral warping wavetable synth" — free Basic tier plus paid Plus/Pro tiers
(more presets/wavetables, unlimited text-to-wavetable). Full MPE support (ROLI, Linnstrument).

**Architecture / main sections**
- **Oscillators:** spectral-warping wavetable oscillators — warping "acts on a waveform's
  harmonics"; extremely low noise floor, sharp cutoff at Nyquist. Count of 3 wavetable
  oscillators + 1 sample source **(unverified — from product UI/press, not stated on the
  official page)**.
- **Wavetable editor:** built-in; create tables from scratch, pitch-splice or vocode converter
  for audio, and text-to-wavetable generation (rate-limited on free tier).
- **Filters:** shown with animated visual filter responses; the commonly cited 2 routable
  filters with analog/digital models **(unverified — from product UI/press)**.
- **Envelopes / LFOs:** "snappy envelopes"; custom and smooth LFO shapes, keytracked LFOs.
  Counts (3 env / 4+ LFOs / randomizers) **(unverified — from product UI/press)**.
- **Modulation:** drag-and-drop with live preview before committing; sources include perlin-
  noise randomization, velocity, aftertouch, MPE; stereo modulation; remappable mod curves.
- **FX:** present (chorus, delay, reverb, distortion, compressor etc.) but the official page
  lists no effect roster — chain details **(unverified)**.

**Use for house**
Free-tier Serum alternative for tech house basses and plucks; perlin-noise modulation gives
instant analog-ish drift on melodic leads.

**Manual:** https://vital.audio

---

## Keyscape (Spectrasonics)

**What it is**
A "collector keyboards" instrument: 36 sought-after keyboard instruments, carefully restored,
deeply multisampled and behavior-modeled over roughly a decade by Spectrasonics' sound team.

**Architecture / main sections**
- **Library:** ~77 GB, 500+ sounds across 36 instrument models plus hybrid "Duo" patches;
  optional ~30 GB "Lite" install for stage use.
- **Instruments:** acoustic/electric pianos and classic keyboards (vendor copy highlights the
  LA Custom C7 grand, Rhodes, Wurlitzer and Clavinet models among the 36) — exact model list
  per patch lives in the reference guide.
- **Duo patches:** hybrids combining two of the instruments into new sounds.
- **Per-patch controls:** each patch exposes custom performance/character controls (tone,
  mechanics, FX) tailored to that instrument — specific control sets per patch
  **(unverified here; see reference guide)**.
- **Omnisphere integration:** works as a satellite library inside Omnisphere 2's browser,
  where its sounds gain Omnisphere's full synthesis engine.

**Use for house**
Real Rhodes/Wurli/Clavinet stabs and the C7 for melodic house piano hooks — layer under a
synth pad, then process in Live (EQ Eight + Chorus-Ensemble as stock route).

**Manual:** https://www.spectrasonics.net/products/keyscape/

---

## Kontakt 7 & Kontakt 8 (Native Instruments)

**What it is**
NI's industry-standard sampling platform — the host for most third-party sample libraries
(free Kontakt Player runs Player-licensed libraries; full Kontakt opens everything plus the
instrument-building/creation tools). NKS maps library controls to Kontrol/Maschine hardware.

**Architecture / main sections**
- **Engine:** deep sampler with scripting-based instruments; "enhanced synth capabilities,
  including real-time wavetable, frequency modulation, and ring modulation oscillators."
- **Factory content (K8):** 900+ Factory Library instruments, plus Conflux, Hybrid Keys and
  12 Leap Expansions.
- **New in Kontakt 8 (vs 7):**
  - **Tools:** a creative layer that works with any Kontakt instrument — Phrases, Chords,
    Patterns, Chord Builder, Velocity Curve, Humanizer, Scale Lock, Arpeggiator, After Touch.
  - **Leap:** "ultra-fast and playful" loop playback/manipulation instrument.
  - **Conflux:** new hybrid sound-design instrument using original PPG wavetables.
  - **Hybrid Keys:** sampled pianos/synths/mallets with tape warble and noise controls.
- **Kontakt 7 baseline:** same core sampler/platform; the 7-era browser and factory library
  remain usable — K8-specific additions above are what Zizz gains by loading 8 instead of 7.

**Use for house**
Host for one-shot/texture libraries and keys; K8's Phrases/Chord Builder tools are quick
melodic-idea generators on any loaded instrument.

**Manual:** https://www.native-instruments.com/en/products/komplete/samplers/kontakt-8/

---

## Analog Lab V (Arturia)

**What it is**
Arturia's preset player: thousands of curated sounds drawn from the V Collection instruments
and Pigments in one browser, without loading each full instrument. (Arturia now brands the
editions Play/Intro/Pro; "Analog Lab V" is the V-generation release — Pro-level feature set
described below.) Full instrument panel editing requires a V Collection license.

**Architecture / main sections**
- **Library:** 2000+ curated sounds (Pro tier) from the V Collection instruments and Pigments —
  pianos, organs, analog and digital synth recreations.
- **Macros:** 4 macro controls on every sound for instant editing without the full panel.
- **Browser:** filter by type (bass, pads…), style (bright, dark…), genre (ambient, techno…),
  sound bank, sound designer and instrument; favorites tagging.
- **Studio view:** effects plus multi editing — combine 2 instruments as layered or
  keyboard-split Multis.
- **Stage view:** perform from prepared Playlists via Arturia keyboards or MIDI Program Changes.
- **Controller integration:** auto-mapped on Arturia keyboards; easy mapping to other MIDI
  controllers.

**Use for house**
Fast preset-surfing for Juno/Prophet/DX-flavored pads and keys when a part needs a sound now;
promote the patch to the full V Collection instrument later if deeper editing is needed.

**Manual:** https://www.arturia.com/products/software-instruments/analoglab/overview

---

## Voltage Modular + Voltage Modular FX (Cherry Audio)

**What it is**
Cherry Audio's software modular platform — an empty virtual cabinet you fill with modules
(Core bundle: 90+ modules, plus Misfit Audio Electro Drums' 15). Runs standalone and as
instrument *and* effect plugin (the FX build hosts module chains in an audio-effect slot)
**(effect-plugin detail from vendor listing copy; exact "Voltage Modular FX" packaging
unverified on the product page)**. A module store lets you buy and auto-install modules
and presets from inside the app.

**Architecture / main sections**
- **Cabinet/rack:** add modules to cabinets, with optional auto-alignment.
- **Patching:** virtual patch cables with **unlimited cables per jack**; Busses feature to
  reduce cable clutter.
- **Variations:** unlimited per-patch variations, playable individually or stepped through
  with triggers or CV.
- **Engine:** 64-bit double-precision math, zero-latency module processes; integrated
  Recording section renders 32-bit float audio from the main outs.
- **Module Designer:** separate tool for building your own modules (Java-based)
  **(language detail unverified)**.

**Use for house**
Generative percussion, CV-sequenced acid-ish lines, and the FX build for modular delay/
filter mangling on sends — a sound-design playground more than a daily driver.

**Manual:** https://cherryaudio.com/products/voltage-modular

---

## Surrealistic MG-1 Plus (Cherry Audio)

**What it is**
Free, "super authentic" recreation of the Realistic MG-1 — the Moog-built synth sold in
Radio Shack stores in the early 80s — with modern additions. 130+ presets; AU/VST/VST3/AAX
and standalone.

**Architecture / main sections**
- **Tone sources:** dual-oscillator monophonic section plus a polyphonic oscillator bank
  (the MG-1's organ-style poly section).
- **Filter:** "super fat" 24 dB ladder filter.
- **Ring mod:** bell-tone ring modulation.
- **LFO:** tempo-syncable.
- **Modeling/automation:** ultra-accurate analog modeling; full DAW automation.
- **Contour/envelope and added "Plus" FX section:** present on the instrument but not
  itemized in the vendor copy retrieved — details **(unverified; see user guide)**.

**Use for house**
Free grit machine: the poly bank + ring mod makes raw, lo-fi chord stabs and the mono section
does simple Moog-y basses — character picks, not precision tools.

**Manual:** https://cherryaudio.com/products/surrealistic-mg-1-plus
