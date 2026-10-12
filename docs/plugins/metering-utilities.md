# Metering & utilities — verified reference

Verified against official vendor documentation, October 2026. Sources: minimeters.app
(homepage + help), Voxengo SPAN User Guide v3.24 (PDF), Youlean Loudness Meter 2 Manual
v2.2.1 (PDF) + youlean.co product page, TBProAudio mvMeter2 Manual (PDF, v2.7.x),
Mastering The Mix REFERENCE 2 manual + product page, pressplay-music.com,
waves.com support pages + waves.com/plugins/studiorack + Waves' June 2023 OBS
announcement. Anything not found in official docs is marked **(unverified)**.

Workflow anchors used below: **0 VU = -18 dBFS** gain staging while mixing, and the
**-9 to -11 LUFS short-term** stress test on drops when checking club loudness.

---

## MiniMeters (MiniMeters / directmusic)

**What it is**
A standalone metering **application** for macOS/Windows/Linux plus a plug-in suite.
Two ways to feed it:

1. **Standalone app** — monitors any stereo input, or system **output** capture
   (output capture needs macOS 14.2+; the dev flags known issues on macOS Tahoe —
   see minimeters.app/help/macos-tahoe-issues).
2. **MiniMeters — Audio Server** plug-in (VST3 / AU / CLAP; **no VST2 exists**) —
   insert it in Live (end of the master chain is the usual spot), then in the
   MiniMeters app: Settings → Audio Source → **"Audio Server (Plug-In)"**. The app
   then meters exactly what the DAW sends, independent of the system output.

Since v1.0 every module also ships as its **own plug-in** (VST3/CLAP/AU), plus a
combined "MiniMeters Plug-In" with a Quad Layout — so the sub-plugins Zizz sees in
the Live browser (Loudness, Oscilloscope, Spectrogram, Spectrum, Stereometer, VU,
Waveform) are the app's modules as individual in-DAW meters.

**Main controls / readouts (per module, from minimeters.app)**
- **Loudness** — immediate peak value plus a LUFS or RMS readout. Modes:
  **LUFS Momentary (0.4 s)**, **LUFS Short-Term (3.0 s)**, **RMS Fast (0.3 s)**,
  **RMS Slow (1.0 s)**.
- **VU** — classic VU needle. Two visual styles; channel select **L / R / Mid /
  Side**; a **Cal** input adjustment; **Peak (yellow)** and **Clip (red)**
  indicators. The exact Cal range/units are not published **(unverified)** — in
  practice set Cal so 0 VU reads at the -18 dBFS reference.
- **Oscilloscope** — real-time scope; **Follow Pitch** (zero-crossing tracking for a
  stable view), Cycle: Multi or Single.
- **Spectrogram** — FFT 1024–8192; Mel / Logarithmic / Linear scale; horizontal or
  vertical; tilt control; Sharper/Sharp/Classic; piano + frequency overlays;
  scrolling or static.
- **Spectrum** — FFT, Color Bars, or Both; FFT 1024–16384; smoothing; **L/R or
  M/S**; dB/Hz/Note overlay; **target curve by dragging in a WAV/MP3/FLAC**.
- **Stereometer** — Scaled / Linear / Lissajous display; Static / RGB / Multi-Band
  color; correlation meter single- or **multi-band**.
- **Waveform** — L/R/M/S or two channels; Static / Multi-Band / Color Map colors;
  peak history; speed; scrolling/static; shows **DAW timecode** when fed by a
  plug-in or the Audio Server.
- **Recording** — record the selected source, or clip the previous 10/60 s of audio
  and drag it out to another tool.

**Use for house** — run the app on a second screen fed by Audio Server; VU module
Cal'd to -18 dBFS keeps channel/bus gain staging honest, Loudness in LUFS Short-Term
covers the drop stress test without opening another meter.

**Manual:** https://minimeters.app/help

---

## SPAN (Voxengo) — free

**What it is**
Free real-time FFT spectrum analyzer (AU/VST/VST3/AAX) with full level metering,
EBU R128, K-system and correlation metering. Analysis only — touches no audio
(except the optional band-solo sweep).

**Main controls / readouts (verified, User Guide v3.24)**
- **Mode system** (the "Mode" selector / Spectrum Mode Editor): per-mode you set
  **Fourier block size in samples**, **FFT window overlap %**, **visual slope**, a
  **secondary spectrum** type (e.g. real-time maximum, all-time maximum) and visual
  **smoothing**. Default slope is **4.5 dB/octave**, which lifts the display's high
  end compared with most analyzers — change it in the Spectrum Mode Editor if
  comparing against other tools.
- **Hold** freezes spectrum updates for visual comparison; **Underlay** overlays a
  second channel group (load the "Dual Mono" routing preset + Underlay = Right to
  see L and R together). Hold **Ctrl/Cmd** for narrow-band sweep/solo. Right-click
  copies the frequency under the cursor to the clipboard.
- **Metering selector** (meter biasing): dBFS / dBFS.30 / dBFS.15 (range variants),
  **dBFS+3** (AES-17-style +3 dB on RMS), **K-20 / K-14 / K-12** (+ "C" calibrated
  variants; 600 ms RMS ballistics, unweighted), and **LUFS / LU** per ITU-R
  BS.1770-4 / EBU R128: **ML = momentary (0.4 s)**, **SL = short-term (3 s)** on the
  meter, with **integrated loudness** on the "Integr" stats panel (updates 2×/s,
  covers the last 5 minutes since reset).
- **Statistics panel:** RMS/Integr, **Max Crest Factor** (vs a 50 ms peak-RMS
  window), **True Peak / sample Peak** with the **TP** switch, true-peak clipping
  counts, Reset button.
- **Correlation meter:** 500 ms averaged correlation of the first two channels, plus
  3-second averaged L/R balance in dB.

**Use for house** — the free "is the kick/bass pocket clean?" check: M/S spectrum for
sub-mono discipline, correlation ≥ 0 for club PA safety, LUFS SL mode doubles as a
quick drop-loudness readout.

**Manual:** https://www.voxengo.com/files/userguides/VoxengoSPAN_en.pdf/getbyname/Voxengo%20SPAN%20User%20Guide%20en.pdf

---

## Youlean Loudness Meter 2 (Youlean)

**What it is**
LUFS loudness meter (free + Pro), VST2/VST3/AU/AAX and standalone. Analysis only —
never alters audio.

**Main controls / readouts (verified, Manual v2.2.1 + youlean.co)**
- **Mini view:** the **main meter bar shows Momentary loudness**, the **meter
  triangle shows Short-Term**, a bracket on the scale shows **Loudness Range**.
  Numerical **readouts:** Short-Term LUFS, **Integrated LUFS**, Loudness Range (LU),
  Dynamic Range / peak-to-short-term loudness (LU), Peak-to-Loudness Ratio (LU).
  **Hold-max row:** Momentary Max, Short-Term Max, **True Peak Max** — values turn
  red past thresholds you set in Settings; click a value to reset.
- **True peak:** TP max readout, custom true-peak alert threshold, and the histogram
  marks every spot where TP crossed the threshold.
- **Presets** (set the loudness standard): Film/TV/Gaming — ITU-R BS.1770-4,
  EBU R128, EBU R128 S1, ATSC A/85, OP-59, ARIB TR-B32, AGCOM 219/09/CSP, ASWG-R001
  HOME/PORTABLE (free). **Streaming (Pro):** AES Streaming, Spotify, YouTube, Apple
  Music, Tidal in the v2.2.1 manual; the current product page also lists Apple
  Podcast, Deezer, Netflix, Amazon Alexa/Music, HBO, Disney+, EBU R128 S2. Manual
  notes YouTube/Apple presets are approximations (unpublished algorithms). Up to 10
  custom presets (Pro).
- **Histogram view:** modes **Continuous / Elapsed / Time Code** (stores loudness
  against timecode and enables loudness overdub) / **System Time**; loudness target
  line from Settings; window size + scroll/zoom; loudness-vs-dynamics graph switch.
  **Distribution view:** loudness distribution + PLR-short-term (dynamics)
  distribution.
- **Transport behavior:** pause all, pause only Integrated+LRA, reset all, **auto
  reset on host play**. **Drag & drop** a WAV/MP3/OGG/FLAC (or OS-supported
  audio/video) for instant offline analysis (discards current measurements).
  Mono/stereo/5.1 (DTS/ITU/Film routing). Pro adds PDF/PNG/SVG export and A/B states.

**Use for house** — the master-bus stress test: loop the drop and check **-9 to -11
LUFS short-term** with True Peak Max kept around -1 dBTP; Integrated + the Spotify
preset tell you what streaming normalization will do afterwards.

**Manual:** https://youlean.co/wp-content/uploads/2019/04/Youlean-Loudness-Meter-2-V2.2.1-MANUAL.pdf

---

## mvMeter2 (TBProAudio) — free

**What it is**
Free multivariable meter (VST/VST3/AU/AAX) modeled on classic analog VU/PPM
behavior, with RMS and EBU R128 modes, single or dual meter display.

**Main controls / readouts (verified, official manual)**
- **Meter modes:** **Peak**; **RMS** (600 ms integration, -20/+3 scale); **RMS+3dB**
  (600 ms, +3 dB AES-17 compensation); **EBU R128** (2014; ML momentary + SL
  short-term); **classic VU** (dB + VU scale); **classic PPM** (BBC and EBU scales).
- **Channels:** single meter — stereo / L / R / Mid / Side; dual meter — L/R or M/S.
  In stereo single-meter mode: RMS/VU/PPM average the channels, Peak takes the max,
  EBU ML/SL sum per the R128 spec.
- **Config page:** **Reference Level in dBFS for the current meter mode** — the
  manual's own example: *"reference level for classic VU meter is -18 dBFS"*;
  meter **Delay** (sync with latent busses); **OL LED mode** (needle-over-0 or
  digital-peak-over-level) + OL LED level; **needle hold time**; **DAW sync**
  (meter reset on play).
- **Factory presets** (meter mode @ reference level, from the manual's table):
  **VU Standard = VU @ -18 dBFS**, PPM (IIa-BBC) @ -18, PPM (IIa-EBU) @ -18,
  RMS-20/-14/-12 = RMS+3dB @ -20/-14/-12, EBUR128 ML/SL @ -23 LUFS,
  Peak @ 0, RMS Standard @ 0, RMS+3dB (AES-17) @ 0.
- **Gain tools:** **Pre-Gain** knob per channel (±36 dB per changelog; right-click
  for numeric entry), **Gain Match** (auto-sets pre-gain so the max value hits the
  mode's reference), **Gain Link** (dual display), instance label, needle mode
  (off/current/max), current + max readouts (click max to reset), 5 themes, GUI
  scaling to 400%.

**Use for house** — the **VU Standard preset is exactly the -18 dBFS workflow**:
drop it on channels/busses and ride everything to ~0 VU for consistent headroom into
Glue Compressor and the stock chain.

**Manual:** https://www.tbproaudio.de/assets/content/manuals/mvMeter2%20manual.pdf

---

## REFERENCE (Mastering The Mix)

**What it is**
Reference-track comparison plugin: load pro tracks, A/B them level-matched against
your mix/master, last on the master bus. The **Trinity Display** and **Wave
Transport** below are REFERENCE 2 terminology (per its official manual); the current
REFERENCE 3 reworks the analysis into Masterscope / Mix Descriptors / Mix Balance /
Match % — check which version is installed in the Live browser.

**Main controls / readouts (verified, REFERENCE 2 manual + MTM pages)**
- **Trinity Display** — per frequency band, three readings against the reference:
  **Level Lines** (perceived volume of that band vs the same band in the reference),
  **Stereo Spread** (stereo width of your track and the reference per band), and
  **Punch Dots** (short-term dynamic range per band vs the reference). Click a band
  to **solo** it and zone in on differences.
- **Level Match** — real-time gain matching so loudness doesn't bias the comparison.
  MTM's recommendation: keep it **on**, set to **"Match To Original"** and **"All
  Tracks"** for both mixing and mastering. The auto gain shows on the gain slider;
  moving that slider manually disengages matching. **Turn Level Match off before
  bouncing** if using "Match to quietest" or "All to -14 short-term LUFS", since
  those modes alter your own track's loudness.
- **Wave Transport** — the waveform strip: **drag & drop reference tracks onto it**,
  and create **multiple loops** to jump between sections (your drop vs their drop,
  your break vs their break).

**Use for house** — level-matched A/B against 2–3 pro tech house releases; the
per-band level/width/punch readout answers "is my low end as loud, as mono and as
punchy as the reference?" without loudness bias.

**Manual:** https://www.masteringthemix.com/pages/reference-2-manual

---

## WaveObserver (Press Play) — free

**What it is**
Free **oscilloscope / time-domain monitoring** plugin (macOS 10.15+: VST3/AU/AAX;
Windows 10+: VST3/AAX) for mixing, mastering and sound design. It is **not** a
spectrum analyzer — time domain only.

**Main controls / readouts (verified, pressplay-music.com)**
- Continuous display of **left, right or stereo** input.
- **Three observer modes:** **Stream** (continuously scrolling signal), **Sweep**
  (left-to-right playhead like a hardware scope), **Waveform** (stabilization
  algorithm holds individual cycles/oscillations steady on screen).
- **Time range** from **1 ms up to 4 s** across the view.
- **Freeze** function with scroll-back through display history.
- **Peak level meter** included.
- Paid **Wave Observer Pro** exists with more features (e.g. a threshold-crossing
  indicator per release notes) **(Pro feature list unverified from official page)**.

**Use for house** — zoom into the kick's first 50 ms to judge transient shape and
check kick + sub phase alignment visually before reaching for SPL Attacker or a
clipper.

**Manual:** https://www.pressplay-music.com/wave-observer/

---

## WaveShell1-VST3/AU 15.5 / 16.0 / 16.6 / 16.7 + Waves StudioRack for OBS (Waves)

**What it is**
**WaveShells are containers, not plugins.** Per Waves' own support docs, the actual
Waves plugins install into a central Waves "Plug-Ins V*xx*" folder, and a
**WaveShell** file placed in the host's plugin folder acts as the **software
gateway** that connects the host (Live) to them. Several shells with different
version numbers (here 15.5–16.7) simply mean Waves products from different
versions/purchases live in different shells; Waves staff confirm shells **cannot be
merged**, and shells are managed/updated through **Waves Central**, never by moving
files manually.

Consequence for this rig: **the shell names reveal nothing about which Waves plugins
are actually licensed/installed** — check the Live browser (the shells expand to the
individual devices there) or Waves Central before recommending any specific Waves
device. This matches the CLAUDE.md rule: Waves plugins stay "unverified" until seen
in the browser.

**StudioRack / "Waves StudioRack for OBS":** StudioRack is Waves' **free plugin
chainer** (waves.com/plugins/studiorack — "smart plugin chainer", now with the
StudioVerse AI-searchable chain library). Per Waves' June 2023 announcement, Waves
plugins became OBS Studio compatible by **inserting StudioRack as a filter on an OBS
audio source** and loading Waves plugins inside it — the "for OBS" entry in the scan
is that streaming-side integration, not a separate music plugin. Irrelevant inside
Live; relevant only if Zizz streams sessions.

**Use for house** — housekeeping only: treat WaveShell entries as "Waves is
installed, inventory unknown"; verify the specific device in the browser before it
enters a suggestion (step 2 of the three-option rule).

**Manual:** https://www.waves.com/support/how-to-use-waves-plugins-when-using-custom-vst-folder · https://www.waves.com/plugins/studiorack
