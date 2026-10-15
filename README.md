<div align="center">

# Crateful

**Simply sort your exported rekordbox.m3u8/.txt files.**<br>
Listen to a track, press one key, move on. Sort, split by BPM, rate, and see the hours you've saved.

![macOS app](https://img.shields.io/badge/macOS-app-000000?logo=apple&logoColor=white)
![Apple Silicon and Intel](https://img.shields.io/badge/Apple%20Silicon%20%2B%20Intel-universal-555555)
![Runs locally](https://img.shields.io/badge/runs-locally-3ad0bd)
![Free](https://img.shields.io/badge/price-free-ffb020)

**[Download Crateful for Mac](https://github.com/SeanCreaney/crateful-readme/releases/latest)**

![Crate Sort](docs/screenshots/crate-sort.png)

</div>

### Get started

1. Download **Crateful-mac.zip** from the [latest release](https://github.com/SeanCreaney/crateful-readme/releases/latest) and unzip it.
2. Drag **Crateful** into your **Applications** folder.
3. Open it. The first time, macOS says it can't check the app (it isn't from the App Store). Go to **System Settings → Privacy & Security**, scroll down, click **Open Anyway** and confirm. You only do this once.
4. Drop a rekordbox `.m3u8` export onto Crate Sort and start sorting. Everything saves as you go.

Needs macOS 11 (Big Sur) or newer. Works on Apple Silicon and Intel Macs.

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
| 1–9, 0 | your playlists and combos (add them with **+ Add Playlist** or the + key) |
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

Crateful works out of the box. If you want to change things, create `crateful.config.json` in `~/Library/Application Support/Crateful/` (Finder: **Go → Go to Folder…**) and restart Crateful. It can set:

| Setting | What it does | Default |
|---|---|---|
| `music_folder` | where sessions, splits and ratings are saved | `~/Music/crateful` |
| `start_at` | where each track starts playing (0 = top, 0.3 = 30% in) | `0` |
| `default_playlist` | name for a session's key-1 playlist when none is set | `Songs to Keep` |
| `rate_tags` | Crate Rate tag keys to start with (6–9, 0), each with a name, note and colour | none |
| `hand_seconds_per_track` | Crate Stats: seconds per track doing the same by hand | `18` (30 min per 100) |

</details>

## FAQ

**Does it change my music or my rekordbox library?**<br>
*No. Audio files are only read. Crateful writes playlists into its own folder (`~/Music/crateful`), and nothing reaches rekordbox until you import a playlist yourself.*

**Can a track go into more than one playlist, say House and Percussive?**<br>
*Yes. Add House and Percussive as playlists, then add one more key and tick both of them: that makes a combo. One press of it (say 3 = House + Percussive) puts the track in both and moves on. In Crate Rate, tags work the same way: switch on as many as you like, then Enter.*

**What happens when I import into rekordbox? Are my old playlists affected?**<br>
*Each `.m3u8` in `FOR IMPORTING/` comes in as a new playlist. Your existing playlists aren't touched, and tracks aren't duplicated: rekordbox matches them to the tracks already in your collection. If a playlist with the same name already exists, you'll get a second one beside it, so delete or rename the old one if the new one replaces it.*

**My music is organised in folders, with matching folders in rekordbox. Does Crateful change that?**<br>
*No. Crateful never moves, renames or copies your music. The playlists it makes just point to the files where they already are, so your folders on disk stay exactly as they are. In rekordbox, drag the imported playlists into whichever playlist folder you like.*

**Do I need rekordbox?**<br>
*Not for Crate Sort or Crate Rate: they work with any `.m3u8` playlist, whichever app made it. Crate Split needs rekordbox, because it reads rekordbox's `.txt` export (that's where the BPMs come from).*

**My music lives on an external drive. Does that work?**<br>
*Yes. Crateful plays each track from wherever the playlist says it is, external drives included. Just have the drive plugged in while you sort. Crateful's own sessions are saved on your Mac in `~/Music/crateful`.*

**Is my library uploaded anywhere?**<br>
*No. Crateful runs entirely on your Mac, sends nothing anywhere and doesn't open any network connection.*

**Do I need anything installed?**<br>
*No. Crateful is a normal Mac app: download, drag to Applications, open.*

**Which audio formats play?**<br>
*MP3, WAV, AIFF, FLAC and M4A/AAC.*

**Why does macOS warn me the first time I open it?**<br>
*Crateful is free and isn't sold through Apple, so it isn't signed with a paid Apple developer account. Use **Open Anyway** (see Get started) once and it opens normally after that. Only download it from this repository's Releases.*

**My drive isn't plugged in. What happens?**<br>
*Tracks show "File not found". Plug the drive in, go back to the session list and open the session again.*

**Does it work with Serato, Traktor or Engine DJ?**<br>
*Crate Sort and Crate Rate use plain `.m3u8` playlists, so they should. Crate Split reads rekordbox's `.txt` export specifically. Not tested yet: feedback welcome.*

## Disclaimer

Crateful is an independent project and isn't affiliated with or endorsed by AlphaTheta or Pioneer DJ. rekordbox is a trademark of AlphaTheta Corporation. Provided as is, without warranty. Only download Crateful from this repository's Releases.

## Support

Crateful is free. If it saves you hours, you can buy me a beer 🍺

<a href="https://buymeacoffee.com/seancreaney"><img alt="Buy me a beer" src="https://img.shields.io/badge/Buy%20me%20a%20beer-ffb020?style=for-the-badge&logo=buymeacoffee&logoColor=black"></a>

<div align="center">
<br>
<sub>A Lucky Cat Collective Creation</sub>
<br>
<sub><sub>ssentif eht ssentiw</sub></sub>
</div>
