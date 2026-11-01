<p align="center"><img src="images/logo.png" width="160" alt="AMS2 Server Control"></p>

<h1 align="center">AMS2 Server Control</h1>

<p align="center"><a href="README.md">Deutsch</a> · <b>English</b></p>

<p align="center"><a href="https://github.com/MaDDoX75/AMS2-Server-Control/releases/latest"><b>⬇ Download (latest version)</b></a> · <a href="CHANGELOG_EN.md">Changelog</a></p>

A Windows GUI for the **Automobilista 2 Dedicated Server**: install and update the server, set up races, run championships with points, manage drivers and race control – without editing config files.

> Preview version – feedback and bug reports are welcome.

## Installation

1. Put `AMS2-Server-Control.exe` anywhere – easiest is an empty folder or the dedicated server folder (next to `DedicatedServerCmd.exe`).
2. Start the EXE.
3. On the first start the **setup assistant** opens (see below). If an already configured server is found, the tool starts directly.

## Language

The tool is available in **German** and **English**. On the first start the Windows language is preselected. You can switch at the top right of the setup assistant, and later under *Settings → General → Sprache / Language* (the tool restarts afterwards). In-game chat messages (welcome, `!rank`, `!info`, race control …) follow the chosen language. The choice is stored in `AMS2-Server-Control.lang.txt` next to the tool.

## Setup assistant

Opens automatically on the first start and any time via *Settings → Experts → Setup assistant*.

1. **Server** – the tool searches all Steam libraries, the tool folder and its subfolders. You always choose:
   - use a **found installation**,
   - **install fresh via SteamCMD** (free, no Steam login, app 1338040) – suggested target is `<tool folder>\Server`, or
   - **choose a folder yourself**.

   When switching to another installation you can **copy your data**: settings, presets, championships, results, penalties and VIP list.
2. **Installation** – SteamCMD is downloaded if needed (it lives in a `steamcmd` folder *next to* the server folder) and installs the server with a progress bar and log. If Steam reports “Missing configuration” on the very first run, the tool retries automatically up to 3 times.
3. **Network** – a checklist: local IPv4 of this PC (tip: always assign it the same address in your router), the ports to forward (**8766, 27015, 27016**, TCP and UDP, IPv4 only – button *Copy ports*), a DS-Lite/CGNAT check via your router (UPnP) and the server log, bind IP and Windows Firewall.
4. **Done** – summary. When the server folder changes, the tool restarts.

## Getting-started assistant

Appears on the very first start of AMS2 Server Control and any time via *Settings → General → Getting-started assistant*. Something sensible is preselected on every page, so you can simply keep clicking “Next”.

1. Welcome · 2. Server name, password, max. players · 3. Track (cards with search, ★ = beginner tips) · 4. Cars (free choice, popular classes or any class) · 5. Length (*Short* / *Medium* / *Long*) · 6. Realism (*Relaxed* / *Balanced* / *Simulation*) · 7. Points on/off · 8. Summary → **Save & start server** or **Save only**.

## Main window

- **Overview** – live status, players, track, next championship race.
- **Quick race** – summary card at the top, track and car selection as cards, sessions, weather & time, rules & driving aids, race options and scoring. **Start race** saves and (re)starts the server, **Apply live** takes effect from the next session without a restart. A **pit lane** speed limit (track default or 40–200 km/h) is under Rules & driving aids. The page adapts to the window width. Presets save complete setups. **★ Choose race series** sets the classes (multiclass for IMSA, WEC and Le Mans Series) and the option **only tracks matching the class** hides kart, oval, RX and truck tracks for circuit cars and shows the historic layouts for historic cars.
- **Championships** – several races with their own points system and standings. Real calendars as templates (GT3 series 2022–2026, IMSA 2026 and 2019, WEC 2026, Le Mans Series 2005, FIA GT 2005, Porsche Supercup, Super Trofeo, DTM 1991/1992). Step 1 has its own **Vehicles** box (free choice, one class, multiclass with max. cars per class, fixed car); the setup applies immediately. **★ Race series** in step 1 sets the classes, filters the tracks and shows only that series' calendars; championships can be **exported/imported** (`.ams2champ`) with progress and results or as a fresh championship – existing ones are never overwritten; tracks missing in AMS2 are replaced by similar ones. The big **Start next race** button runs the next round.
- **Drivers** – live player list: private message, kick, ban, VIP slots; permanent ban list.
- **Chat** – admin chat with history.
- **Results** – every session is archived. Statistics with rankings, lap records and driver profiles, CSV export.
- **Monitor** – CPU, RAM, network and ping of the PC and the server, server log.
- **Settings** – export/import of all settings (`.ams2settings`), server name (optionally with track/championship appended), update check on start, password, network, welcome message, chat commands, in-game chat language, name in chat (»Admin: Hi«), scoring & points, VIP slots, performance & power, expert options, server installation & update.

## Help & updates

- **? Help** in the navigation opens the help window with the tabs **Guide**, **Features** (this README) and **Changelog** (all changes). The texts are built into the EXE.
- **Check for updates** looks for a newer version on GitHub (`MaDDoX75/AMS2-Server-Control`). If you want, the tool downloads the new `AMS2-Server-Control.exe`, closes, replaces the file and restarts. The server keeps running.
- The tool checks automatically on start (can be switched off under *Settings → Server → Display*).

## Race control (penalties)

Right-click a driver in a result → *Give penalty*: **point deduction** (position stays), **time penalty** (result is re-sorted, points recalculated) or **disqualification**. A reason is required, the penalty can be announced in chat. Penalized drivers are shown in red with ⚑ and a tooltip. All penalties can be listed and removed again; the original result is never changed.

## Server addon “tgc_manager”

The tool installs its own Lua addon when saving. It provides the welcome message, chat commands (`!help`, `!rank`, `!top`, `!best`, `!record`, `!info`, `!next`), points and the server ranking (also when the tool is closed), VIP slots and class limits.

## So friends can join

- The **bind IP** must be empty (with `127.0.0.1` only your own PC can join).
- Forward the ports **8766, 27015, 27016** (UDP and TCP) to this PC in your router, IPv4 only. Always assign the PC the same IPv4 address.
- With **DS-Lite** (no public IPv4 of your own) friends cannot connect from outside – the setup assistant checks this.
- Allow `DedicatedServerCmd.exe` in the Windows Firewall (asked on the first start).

## Files

Everything is stored in the `ServerControl` subfolder of the server folder: `settings.json`, `presets\`, `backups\`, `logs\`, `results\`, `chat\`, `championships\`, `penalties.json`. Next to the tool: `AMS2-Server-Control.path.txt` (chosen server folder) and `AMS2-Server-Control.lang.txt` (language).

## Building the EXE (developers)

Run `EXE bauen.bat`. It installs the `ps2exe` module if needed and builds `AMS2-Server-Manager_v<version>.exe`; an `icon.ico` next to it is used as the icon.

## About

**AMS2 Server Control**  
Developed by MaDDoX for THC Sim Racing.  
Version 0.197 · October 2026  
Website: https://github.com/MaDDoX75/AMS2-Server-Control

AMS2 Server Control © 2026 MaDDoX · The Game Central. All rights reserved.  
The Game Central [TGC] and the TGC logos are the property of MaDDoX.  
The THC Sim Racing logo [THC] is the property of THC Sim Racing.

## Legal

**Use:** The program may be used privately free of charge and passed on unchanged. Selling it or publishing modified versions requires the author's permission.

**No warranty:** Use at your own risk. The program writes `server.cfg` and other files of the dedicated server (a backup is made first each time). No liability is accepted for data loss, server outages or errors in standings and results.

**Not an official product:** This program is a fan project and is not affiliated with Reiza Studios. "Automobilista 2" is a trademark of Reiza Studios. The program controls the official AMS2 Dedicated Server through its configuration files, HTTP API and Lua interface and does not change anything in the game. SteamCMD and Steam are services of Valve.
