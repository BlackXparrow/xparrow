<p align="center"><img src="promo/hero_banner.jpg" alt="Xparrow: Gear up. Plan smart. Fly free." width="100%"></p>

# Xparrow 1.1.0

**Gear up. Plan smart. Fly free.**

Xparrow is a fan-made desktop companion for Star Citizen. It shows outfits, weapons, ship loadouts, LIVE vs PTU changes, your session plan and a tablet MFD. Everything it shows is read from **your own** Star Citizen install on your PC.


> Promo video (38 s): [xparrow_promo.mp4](https://github.com/BlackXparrow/xparrow/releases/download/v1.1.0/xparrow_promo.mp4)

## Features

| | |
|---|---|
| **Outfits** | 3D armor and clothing viewer with turntable, colour variants and stats. |
| **Weapons** | FPS weapons, attachments and presets, with real numbers from the game data. |
| **Ship Loadout** | Components and guns per slot, swap and compare, and where to buy them. Ships without 3D keep full stats ("3D coming soon"). |
| **Ship Compare (LIVE vs PTU)** | Buffs, nerfs and new items between your LIVE and PTU builds, with a link to the official patch notes. |
| **Fleet** | Hangar planner with measured bays. |
| **Exploration** | Star map, live position and Loot Finder. |
| **Session Plan** | Today's loot list, map guidance and progress. |
| **Blueprints & Crafting, Wikelo, Black Market** | Recipes, contracts, contraband and where to find things. |
| **Overlay** | A small always-on-top panel for use while playing. |
| **Tablet MFD** | Power, weapons, shields and fire mode from a tablet or phone on your network, styled after each ship maker. It uses the binds you set in the game. |
| **Settings & Keybinding** | Your binds, curves and graphics settings, read from the game files. |
| **On-demand 3D** | Ships that have no 3D model yet can load it from your game files: *Load 3D from my game files* on the ship, or *Load all missing 3D* in Settings. |

<p align="center">
<img src="promo/t03_ship_loadout.jpg" width="49%"> <img src="promo/t12_ask_ptu.jpg" width="49%">
<img src="promo/overlay_ingame_1.jpg" width="49%"> <img src="promo/tablet_mockup_makers.jpg" width="49%">
</p>

## Download

From **Releases** (v1.1.0):

- `Xparrow-Setup-1.1.0.exe`: installer (Start menu shortcut, uninstaller).
- `Xparrow-Portable-1.1.0.zip`: portable. Unzip it and run `Xparrow-Portable-1.1.0.exe`. Nothing gets installed.

## First-run setup

1. Start Xparrow. The setup window finds your Star Citizen install (for example `C:\Program Files\Roberts Space Industries\StarCitizen\LIVE`). Pick it or browse to it. A PTU install in the same StarCitizen folder is linked too, for the LIVE vs PTU compare.
2. Pick a drive for Xparrow's data. It needs about **13 GB** when done and up to about **19 GB** while it builds.
3. Xparrow reads your game files and builds its data. **This is slower than a normal download because it reads your own game files.** It can be paused and resumed.
4. Ship 3D loads later, on demand. The first load takes a few minutes per ship and runs in the background at low priority.

Your game files are only **read**, never changed. When the game updates, Xparrow notices the new build and refreshes its data.

## Why it links your own game folders

Star Citizen's models, textures and data belong to Cloud Imperium Games. Xparrow **does not include or redistribute any of them**. The installer contains only Xparrow's own code. Everything you see is read locally from the game you installed, on your PC. Nothing is uploaded.

## Requirements

- Windows 10 or 11, 64-bit.
- Star Citizen installed (LIVE; PTU optional).
- About 13 GB of free disk space (19 GB while it builds), plus more if you load many ship 3D models.
- A GPU with WebGL2. Any card that runs Star Citizen works.
- Tablet MFD: a tablet or phone on the same network as the PC.

## Tablet setup

1. On the PC, right-click the Xparrow tray icon and choose **Tablet pairing (QR)**.
2. Scan the QR code with the tablet and open the page. Add it to the home screen for full screen.
3. The tablet sends your **own** game binds to the PC. A button stays greyed out until its action is bound in the game (for example *Set EMPs* or *Staggered / Together*).
4. Optional: tick **Settings > About > App > Start tablet when Windows starts**. Xparrow then starts hidden in the tray, so the tablet can connect at any time.

Allow Xparrow through Windows Firewall on **private** networks when Windows asks.

## Troubleshooting

- **Setup says it can't find the game:** browse to the folder that contains `Data.p4k` (usually `...\StarCitizen\LIVE`).
- **Not enough disk space:** choose another drive in setup. Xparrow stops before a drive drops below its safety margin.
- **A ship shows "3D coming soon":** press *Load 3D from my game files* on that ship. If it fails, the stats and loadouts still work. Use *Report 3D issue* to save a local report in `%APPDATA%\Xparrow\3d_reports\` that you can share.
- **The tablet doesn't connect:** make sure the PC and tablet are on the same network, Xparrow is running (tray icon), and the firewall allows it on private networks.
- **A tablet button is greyed out:** bind that action in Star Citizen (Options > Keybindings), then reopen the tablet page.
- **After a game patch the data looks old:** Xparrow refreshes when it sees the new build. The game launcher must finish updating first.

## FAQ

### What Xparrow can do

- Show outfits, weapons and ships in 3D, with stats read from your own game files.
- Plan ship loadouts: swap guns and components, compare them, and see where to buy them.
- Compare your LIVE and PTU builds: what got buffed, nerfed or added, with a link to the official patch notes.
- Plan sessions, blueprints and crafting, Wikelo contracts and Black Market runs.
- Show a star map and your position from `/showlocation` (the game copies it to the clipboard) and from `Game.log`.
- Run an always-on-top overlay while you play.
- Turn a tablet or phone into an MFD that presses the keys **you** bound in the game.
- Build missing ship 3D models from your own game files, on demand.

### What Xparrow can't do (and why)

- **No editing of aUEC, money, items or inventory.** Xparrow can't change anything on the game servers.
- **No memory reading or injection.** It never touches the running game process.
- **No changing game files.** The one exception is the MFD keybinds you approve in `actionmaps.xml`. Xparrow only writes those with the game closed, and it makes a backup first.
- **It can't press anything the game has no keybind for.** The tablet only sends keys that exist as game actions. *Staggered / Together* fire mode works because the game has actions for it (*Staggered fire on / off*).
- **MFD buttons only work when the matching action is bound in the game.** For example, *Set EMPs* needs *EMP preset* bound. Unbound buttons stay greyed out.
- **It can't see live in-game state** beyond what `Game.log` and `/showlocation` provide. Power, shield and fire-mode states on the tablet show what you pressed, not readings from the game.
- **It isn't affiliated with CIG.** It's a fan project.

### Q&A

**Is it safe and allowed?**
Xparrow only reads your game files and presses keys you bound yourself, like a keyboard macro pad. It doesn't read game memory, inject code or change server data. It's still a third-party tool, so you use it at your own risk.

**Why does it link my game folders?**
CIG's assets can't be redistributed, so Xparrow ships none. It reads them locally from your own install instead.

**Why is the first 3D load slow?**
Xparrow extracts the ship from your `Data.p4k` (more than 100 GB) and builds the model on your PC. That takes a few minutes per ship, at low priority in the background. After that, the model is cached.

**Does the tablet need the same Wi-Fi?**
Yes. The tablet connects to Xparrow on your PC over your local network, so both must be on the same network, and Windows Firewall must allow Xparrow on private networks.

## Credits and licences

- 3D export uses **StarBreaker** (`starbreaker_msvc.exe`), MIT licence. Its licence and notice ship in `tools/starbreaker/` (LICENSE, NOTICE). Thanks to its authors.
- Built with Electron, Three.js, Vite and glTF-Transform. Their licences are included in the app.

## Disclaimer

Xparrow is an unofficial fan project. It is **not affiliated with, endorsed by or sponsored by Cloud Imperium Games or Roberts Space Industries**. Star Citizen®, Squadron 42®, Roberts Space Industries® and Cloud Imperium® are trademarks of Cloud Imperium Rights LLC. Ship and maker names belong to their owners. No game assets are included in this project.
