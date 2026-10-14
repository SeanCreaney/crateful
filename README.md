<div align="center">

# Crateful

**Simply sort your exported rekordbox.m3u8/.txt files.**<br>
Listen to a track, press one key, move on. Sort, split by BPM, rate, and see the hours you've saved.

![macOS](https://img.shields.io/badge/macOS-tested-000000?logo=apple&logoColor=white)
![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?logo=python&logoColor=white)
![Runs locally](https://img.shields.io/badge/runs-locally-3ad0bd)
![Dependencies](https://img.shields.io/badge/dependencies-none-ffb020)

![Crate Sort](docs/screenshots/crate-sort.png)

</div>

### Get started

> [!IMPORTANT]
> **Coming soon.** Crateful isn't available to download yet. Watch or star this repo to hear when the first release is out.

When it's out, you'll download it from **Releases**, run it with one command, and it opens in your browser. Nothing else to install: it only needs Python 3.10+, which macOS can install for you.

> [!NOTE]
> Built and tested on macOS with rekordbox exports. Sorting and rating use plain `.m3u8` playlists, so other DJ software should work too, but hasn't been tested yet.

## The tools

| | |
|---|---|
| **Crate Sort**<br>Drop a `.m3u8` export and give every track one key. Enter for Trash, M for part of a mix, ↓ to decide later, 1–9 and 0 for your playlists. Combos put a track in several playlists at once. **Finish** writes everything into `FOR IMPORTING/`, ready for rekordbox. | ![Crate Sort](docs/screenshots/crate-sort.png) |
| **Crate Split**<br>Drop a rekordbox `.txt` export and get one playlist per BPM, e.g. `2026-10 Downloaded Tracks - 120.01-120.99`. Tracks on an exact whole BPM can get their own playlist. Optionally starts a sorting session for each one. | ![Crate Split](docs/screenshots/crate-split.gif) |
| **Crate Rate**<br>1–5 stars plus your own tags (e.g. *Purple: Euphoric*), then Enter to save and continue. A tempo fader (±6 / 10 / 16 / WIDE) with master tempo lets you hear how a track holds up sped up, and −/+ jumps to the next whole BPM. | ![Crate Rate](docs/screenshots/crate-rate.png) |
| **Crate Stats**<br>Tracks sorted and rated, your real pace, and the time saved compared with doing it by hand. Every key press is timed, with breaks left out. | ![Crate Stats](docs/screenshots/crate-stats.png) |

## Crateful vs sorting by hand

| | rekordbox by hand | Crateful |
|---|:---:|:---:|
| One key per track, no dragging or scrolling | ✗ | ✓ |
| Add a track to several playlists in one go | ✗ | ✓ |
| Know exactly where you left off, and how far through you are | ✓ | ✓ |
| Park unsure tracks and get taken back to them at the end | ✗ | ✓ |
| Split a dump into one playlist per BPM in one go | ✗ | ✓ |
| See how long it took and the time you saved | ✗ | ✓ |
| Time per 100 tracks (real sessions) | ~30 min | **~5 min** |

## Keys

<details>
<summary><b>Crate Sort</b></summary>

| Key | Does |
|---|---|
| Enter | Trash |
| M | Mixed (part of a mix) |
| ↓ | Pending Decision: revisited at the end |
| 1–9, 0 | your playlists and combos (add them with **+ Add playlist** or the + key) |
| ↑ | back to the last track |
| Space | play / pause |
| ← → | jump 15 s (Shift: 60 s), or click the waveform |
| N | next unsorted track |
| C | colour (RGB) waveform |

</details>

<details>
<summary><b>Crate Rate</b></summary>

| Key | Does |
|---|---|
| 1–5 | star rating (press again to clear) |
| 6–9, 0 | your tags: switch on or off, as many as you like |
| Enter | save and continue |
| ↓ | Pending Decision |
| [ ] | BPM down / up to the next whole number |
| \ | tempo back to 0 |
| T | master tempo on / off |

</details>

## Getting results into rekordbox

Drag the `.m3u8` files from a session's `FOR IMPORTING/` folder into rekordbox (or **File → Import → Import Playlist**). Tracks match your existing collection by file location, so cues, grids and ratings stay intact.

## Settings

<details>
<summary>Optional: <code>crateful.config.json</code></summary>

Crateful works out of the box. If you want to change things, an optional `crateful.config.json` file next to the app lets you set:

| Setting | What it does | Default |
|---|---|---|
| `music_folder` | where sessions, splits and ratings are saved | `~/Music/crateful` |
| `port` | the page opens at `http://127.0.0.1:<port>/` | `8765` |
| `open_browser` | open the page in your browser on start | `true` |
| `start_at` | where each track starts playing (0 = top, 0.3 = 30% in) | `0` |
| `default_playlist` | name for a session's key-1 playlist when none is set | `Songs to Keep` |
| `rate_tags` | Crate Rate tag keys to start with (6–9, 0), each with a name, note and colour | none |
| `hand_seconds_per_track` | Crate Stats: seconds per track doing the same by hand | `18` (30 min per 100) |

Command-line options (`--root`, `--port`, `--start`) override the file for that run.

</details>

## FAQ

**Does it change my music or my rekordbox library?**<br>
*No. Audio files are only read. Crateful writes playlists into its own folder (`~/Music/crateful`), and nothing reaches rekordbox until you import a playlist yourself.*

**Is my library uploaded anywhere?**<br>
*No. It runs only on your machine (`127.0.0.1`), sends nothing anywhere, and only its own page can talk to it.*

**Do I need anything installed?**<br>
*Just Python 3.10 or newer, which most Macs already have. There are no packages to install.*

**Why Safari?**<br>
*It plays FLAC and AIFF. Chrome doesn't play AIFF.*

**My drive isn't plugged in. What happens?**<br>
*Tracks show "File not found". Plug the drive in and reload the page.*

**Does it work with Serato, Traktor or Engine DJ?**<br>
*Crate Sort and Crate Rate use plain `.m3u8` playlists, so they should. Crate Split reads rekordbox's `.txt` export specifically. Not tested yet: feedback welcome.*

## Disclaimer

Crateful is an independent project and isn't affiliated with or endorsed by AlphaTheta or Pioneer DJ. rekordbox is a trademark of AlphaTheta Corporation. Provided as is, without warranty. Only download Crateful from this repository's Releases.

<!--
## Support

> [!TIP]
> If Crateful saves you hours, you can [buy me a coffee](https://buymeacoffee.com/YOUR-NAME).
-->

<div align="center">
<br>
<sub>A Lucky Cat Collective Creation</sub>
<br>
<sub><sub>ssentif eht ssentiw</sub></sub>
</div>
