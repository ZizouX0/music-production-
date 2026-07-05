# Local Setup — the parts only you can do (macOS)

Everything in this repo (skills, commands, `.mcp.json`, `CLAUDE.md`) is
already wired. These are the **[NEEDS ME]** steps from the setup brief,
batched. Do them top to bottom on your Mac; ~15 minutes.

## 1. Prerequisites (Terminal)

```bash
# uv — runs the Ableton MCP server
curl -LsSf https://astral.sh/uv/install.sh | sh

# FFmpeg + FluidSynth (audio tools / MIDI→WAV preview)
brew install ffmpeg fluid-synth

# Python dep for the midi-generation skill
pip3 install midiutil==1.2.1

# Verify
uv --version && python3 --version && ffmpeg -version | head -1 && fluidsynth --version | head -1
```

Python must be 3.10+.

## 2. Ableton remote script (session control)

The script is vendored in this repo at
`tools/AbletonMCP_Remote_Script/__init__.py`.

1. Create a folder named **exactly** `AbletonMCP` in Ableton's Remote
   Scripts directory and copy `__init__.py` into it. Try in this order:
   - `~/Library/Preferences/Ableton/Live 12/User Remote Scripts/AbletonMCP/`
   - or right-click `Ableton Live 12 Suite.app` → Show Package Contents →
     `Contents/App-Resources/MIDI Remote Scripts/AbletonMCP/`

   ```bash
   mkdir -p ~/Library/Preferences/Ableton/"Live 12"/User\ Remote\ Scripts/AbletonMCP
   cp tools/AbletonMCP_Remote_Script/__init__.py \
      ~/Library/Preferences/Ableton/"Live 12"/User\ Remote\ Scripts/AbletonMCP/
   ```

2. Restart Ableton, then: `Settings → Link, Tempo & MIDI → Control
   Surface → AbletonMCP` (Input and Output: **None**).

3. The server uses **TCP port 9877**. If Claude reports connection
   failures, check nothing else is on it: `lsof -i :9877`.

The MCP server itself needs no install — `.mcp.json` starts it with
`uvx ableton-mcp` when you open this repo in Claude Code (approve the
project MCP server when prompted). For Claude Desktop instead, add to
`claude_desktop_config.json`:

```json
{ "mcpServers": { "AbletonMCP": { "command": "uvx", "args": ["ableton-mcp"] } } }
```

4. Restart both Ableton and Claude after all of the above.

## 3. SoundFont for MIDI→WAV preview

The `midi-generation` skill renders audio previews with FluidSynth and
needs a General MIDI SoundFont. Either:

- Download a free GM soundfont — e.g. **GeneralUser GS**
  (https://schristiancollins.com/generaluser.php) or FluidR3_GM — and drop
  the `.sf2` into `.claude/skills/midi-generation/soundfonts/` (the skill's
  docs reference `A320U.sf2`; any GM .sf2 works, just tell Claude its
  filename), or
- skip it — MIDI file generation still works, only the WAV preview won't.

`.sf2` files are large; keep them untracked (already gitignored).

## 4. Connectors (browser OAuth — paid tier)

In Claude: `Settings → Connectors`
- Connect **Ableton** (official docs assistant — NOT session control).
- Confirm **Splice** is still connected (sample search needs an active
  Splice Sounds subscription).
- Adobe/Canva: already connected, leave alone.

## 5. Smoke test (after restarting Ableton + Claude)

Open this repo in Claude Code with a Live set open and ask:

> "Read my current Live set, suggest one mix fix using only stock devices,
> and generate a 4-bar chord idea in C minor as a draggable MIDI file —
> don't change anything until I approve."

Also good: "Make me a 4-bar melodic house loop in C minor using stock
devices." If MCP tools hang or AbletonMCP doesn't appear in Live's Control
Surface list, run `/ableton-debug`.

## Not installed (on purpose — ask if you want them)

- **jpoindexter/ableton-mcp** (200+ tools) / **AbletonBridge** (322 tools) /
  **uisato/ableton-mcp-extended** — deeper Live control; swap into
  `.mcp.json` if ahujasid feels limiting.
- **s2d01/daw-midi-generator-mcp** — drag-drop MIDI to `~/Music/DAW/Claude_MIDI/`;
  overlaps with the `midi-generation` skill so it was skipped.
- **audio-engineering-patterns**, **MixMaster AI**, **Loooom**,
  **bitwize mastering-engineer/genre-reference**, and all AI-generation
  tools (§7 of the brief) — optional/situational per the brief.
