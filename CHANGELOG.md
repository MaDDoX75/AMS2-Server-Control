# Changelog – AMS2 Server Control

[Deutsch](CHANGELOG_DE.md)

Recent versions in English. The complete history (German) is in [CHANGELOG_DE.md](CHANGELOG_DE.md).

### v0.2 – Discord + network
- **Discord notifications** (new tab Community → Discord): webhooks for server status, results and championships, stored encrypted, with **Send test**; **server online/offline** as one message that is kept up to date; **result** after every race (podium, class winners, fastest lap, standings, optional BUSTED IDIOTs); **new championship** at the first race or with the »Discord« button; server name to copy for the AMS2 server browser search; German or English
- **Network check** under Settings → Network with a **traffic light on the overview**: Windows Firewall (»Allow in firewall« button), public IPv4 / DS-Lite, port 9000 exposure, automatic **Steam server browser check** after the server starts (no API key), **open ports via UPnP**
- **Router guide**: FRITZ!Box step by step with pictures, plus Speedport, Vodafone Station, o2 HomeBox, TP-Link, ASUS, Netgear and other routers with short guides and manufacturer links; IP and ports filled in; also in the setup assistant

### v0.199
- **Championship without restart**: after the race the next race is loaded automatically – live if players are online (everyone stays in the lobby), otherwise by restart. Chat shows next track, top of the standings and your ballast. If the success ballast changes, the server restarts 30 s after an announcement (the server only reads the ballast at start-up – tested)
- **Menu tidied up**: new **»Community«** page (below »Penalties«) with »Welcome & chat«, later Discord and website; **VIP list, reserved slots and admin commands** on the **Drivers** page (tab »VIP & admins«); **championship without restart, announcements and random weather** under **Championships → Automation**; settings keep »BoP & class limit«. Every moved tab has its own save buttons
- **Idiot Rule** (replaces rowdy protection, off by default): crashes in the race count as points by the **impact strength** the server reports – hard hit 1, contact ½, light touch 0; with AI ½, same opponent again ½, start phase (20 s) ½ except hard hits, **pushing off** (the other car hits the wall shortly after) +½, pile-up (4+ cars in 5 s) at most 1 – except for the cause hitting 3 or more cars. Points expire after an adjustable time (default 5 min). Warning at 2, final warning at 4, kick at 6 points with the message **»BUSTED IDIOT«**; repeat offenders get a ban; VIPs and admins exempt
- **Driver status**: normal → flagged (kicked once, warnings come earlier) → BUSTED IDIOT (kicked several times); flagged drivers get a note when joining, optional public warning; **second chance** after an adjustable number of clean races (default 5)
- **Test mode** for the Idiot Rule: AI counts fully, admins count too, no real kick/ban, every crash with points in the chat window – plus raw data of crash and track-cut events
- **Penalty record and achievements per Steam ID**: warnings, kicks, bans, last incident, statistics; achievements (milestones, first win, serial winner, podium hunter, pole setter, time hunter, iron man, fair play) are kept forever – existing results are added on first start. Right-click in the driver list: show record, raise/lower status, reset record
- **Race ban** for repeat offenders (new default instead of hours): first ban 3 races, then add the same again (3 → 6 → 9) or double (3 → 6 → 12), at most 12 races (all adjustable), optionally permanent from the Xth ban. The tool counts down after every race and kicks banned drivers when they join
- New **»Penalties«** page in the left menu: **overview** of flagged drivers (status, warnings, kicks, ban no., remaining ban, last incident; right-click actions), **ban list** (race/time bans and permanent bans – previously on the drivers page), **race control penalties** and **settings** (the Idiot Rule moved here)
- **Welcome message in the game chat no longer cut off**: long private messages (welcome, championship standing, ballast, `!rank`) are split into short lines, one every 2.5 seconds; custom texts can be split with `|`, new placeholder `{races}`
- **Results table narrower**: short headers (Laps, Time, Gap, Best, Pts, %) with the full name as tooltip; the CSV keeps the full names
- **»Warnings«** column in the driver list and the championship table (e.g. »⚠ 2 · 1× kick« or »⛔ 2 more races«), yellow for flagged, red for banned drivers / BUSTED IDIOTs
- Main window starts wider (1600 × 900); **Monitor** moved to the bottom of the menu next to Help and Settings
- Default server name is now **»AMS2 Server Control Server«**; every installation gets a unique **server ID**
- **Admin commands in the game chat**: `!skip`, `!skiprace`, `!restart`, `!kick name`, `!ai on/off`, `!admin` – only for listed Steam IDs
- **Continuous mode (community mode)** per championship: nobody online → skip the race without scoring; at the end start over (points carry on or new season with archive); optionally roll the weather for every race
- **Championship step 2**: race series as track source – »no race series« shows all tracks, a series only its races; add single races or all (replace or append), mix series, ✓ for races already in the calendar
- **🎲 Random**: random season, roll weather (weighting adjustable), random track and random date (quick race and championship)
- The next track is announced in the chat after the race (also with rotation)
- Server option »Anti-griefing collisions« is now called **»Ghosting for wrong-way & stopped cars«** (explained in the tooltip)
- **Start server** starts the next race of the championship currently open on the championship page (instead of the quick race)
- **Right-click** in the driver list and VIP list: **Copy Steam ID** and **Add / remove as admin**
- **Save in the settings** keeps a running championship (it used to switch to the quick race); only »Start race« / »Save only« in the quick race switch to the quick race
- `!skiprace` skips the race **without restart**: the next championship race is loaded live and everyone stays on the server – in the lobby the track changes immediately; during a session it is loaded for the next event and the chat explains the way: let the race start → back to the pits → back to the lobby; skipped races do not count. If there is no further race, a note is shown
- `!skiprace` during a session: if the next race is already loaded, it says »Already loaded: … comes as soon as you are back in the lobby«; »skipped« is cleared when the race is loaded again or marked as not driven
- `!skiprace` never restarts the server – not even when the success ballast changes (note in the chat)
- 🎲 buttons in orange with a black die so it is easy to see
- **Time-lapse races**: quick race → sessions with buttons 20/30/45/60/90/120 min (or any, e.g. 40) and »felt duration« 6/12/24 h – the tool picks the matching time-lapse step (1x–60x) for time of day and weather and shows what passes in the game (incl. »through the night« note). Per race in championships; endurance races from real calendars (6 h and more) become 60 minutes with matching time-lapse
- 🎲 random weather rolls as many weather slots as set; »like race« is kept
- Race cards show skipped races (»⏭ skipped«)

### v0.1985
- **New design: toggle switches** instead of check boxes – orange = on, grey = off, the knob slides (everywhere incl. the setup assistant)
- **Modern right-click menus**: dark, rounded, orange highlight, icons in front of the entries
- **Dark title bar** for all windows (Windows 10/11); on Windows 11 also an orange window border
- Dark scroll bars (attempt via Windows dark mode – may stay light depending on the Windows version)
- Tables: column headers no longer wrap (»Best lap« was cut off), columns are at least as wide as their header
- »Start server« automatically loads the next championship race when the loaded one has already been driven
- Default date for new races is midsummer (21 June, southern hemisphere 21 December)

### v0.198
- New **✎ Presets** page (navigation, below Monitor): preset cards with New, Edit, Duplicate, Delete and »Race it in quick race«
- Presets are created only on that page – the quick race keeps »Load preset« at the top
- **Preset mode**: edit in the quick race editor with an orange banner and »Save preset« / »Cancel« – the quick race is set aside and comes back unchanged
- **Red/green save buttons**: red with »●« for unsaved changes, green when everything is saved (settings, quick race, preset mode, championship editor)
- Championship step 1 tidied up: info lines removed, **»Load starting values from«**, the race series button shows the chosen series
- **GT3 race series** now add GT3 Gen1 **and** GT3 Gen2
- Server addon renamed to **TGC_Server_Manager** (was tgc_manager) – ranking and results are kept
- **Tooltips** for the navigation and the main buttons
- **Default date is midsummer** instead of »today«: new races get 21 June (southern hemisphere such as Bathurst/Interlagos: 21 December), following races +14 days within summer – sunshine into the evening. Real series calendars keep their original dates
- Championship: if the loaded race has already been **driven**, **»Start server«** automatically loads the next championship race (with ballast and standings)
- **Help window** with rounded design and its own **Changelog** tab
- Championship: **right-click → »Set as next race«** – »Start next race« then loads exactly this race; »Clear the mark« restores the order
- **Fill grid with AI fixed:** the server only adds AI on free slots (AI slots = grid size − max. players). The option now sits next to the grid settings with »→ 16 slots for AI«; if no slot is free the tool offers to halve max. players when saving
- **Message and input windows in the tool's design** (dark, rounded, pill buttons) instead of grey Windows boxes
- Championship: **right-click a driver in the standings → »Change ballast for the next race …«** (this race only, marked ✎)
- Results: sessions **sorted by date** again (newest first), the table fits the window width
- Success ballast now follows the most recently **driven** race (by time), not the calendar order
- Championship step 1: **all options as in the quick race** (driving aids, pit & technology, race flow incl. »fill grid with AI«, fairness, advanced)
- Race cards now also show **practice and qualifying**
- Quick race: the selected section tab is highlighted


### v0.197
- Championship step **3 Drivers**: entry list (number, name, Steam ID, team, ballast, power, drag), take drivers from results or the server
- Fixed names, allow list (option), team standings (all drivers or best 2 per race)
- Success ballast: »based on the last race« or »cumulative with decay«
- Balance of performance for all races (Settings → Players & VIP), own class per championship race
- Personal greeting with points, `{link}` placeholder, VIP announcement
- Chat: Steam ID in the chat log, colours (VIP gold, admin orange, server grey), right-click ban / copy Steam ID / open profile

### v0.196
- New name: **AMS2 Server Control** (`AMS2-Server-Control.exe`); the data folder `ServerManager` is renamed to `ServerControl` automatically
- New: help window with guide and features & changelog, update check and automatic update via GitHub releases
- Championship step 1: grid & AI, rules & driving aids and race options; step 2: practice/qualifying length, up to 4 weather changes, own start time and weather for practice and qualifying, »apply to all races«; step 3: dropped results and a table per class
- New race options: time and weather progression, qualifying stint and lap limit, minimum online rank and strength
- Exports go to `ServerControl\export` by default
- Carbon background removed again

### v0.195
- New: in-game chat language (same as the tool, German, English) and »Name in chat« for your own messages (»Admin: Hi«)
- New: track or championship name appended to the server name (can be switched off)
- New: pit lane speed limit (track default or 40–200 km/h)
- New: export/import of settings and of championships (with progress and results, or fresh); existing championships are never overwritten
- Championship editor step 1: setup applies immediately, own vehicles box
- New: optional carbon background
- Quick race, settings and championship editor adapt to the window width
- Rotation removed

### v0.194
- New: **race series** in quick race and in the championship editor, chosen in the modern look (cards, categories GT3 / Endurance / One-make cups / Classics)
- A race series sets the classes automatically – including multiclass: IMSA 2026 (LMDh, LMP2, GT3), IMSA DPi 2019 (DPi, LMP2, GTE, GT3), WEC 2026 (LMDh, GT3), Le Mans Series 2005 (LMP1, LMP2, GT1, GT2), FIA GT 2005 (GT1, GT2), Porsche Supercup, Lamborghini Super Trofeo, DTM Group A plus the GT3 series
- New real calendars: IMSA 2026, IMSA 2019, WEC 2026, Le Mans Series 2005, FIA GT 2005, Porsche Supercup 2026, Super Trofeo Europe 2026, DTM 1991 and 1992
- New: track filter »only tracks matching the class« / »Matching the class« (track type and car era)
- WEC 2026 uses LMDh instead of the AMS2 class »Hypercars« (road supercars)
- Fix: VIR is now the full layout in the calendars, Suzuka is replaced by Kansai GP

### v0.193
- Fix: the setup and getting-started assistants only open automatically on the very first start – even if they are cancelled. Afterwards they are available under Settings → General / Experts. (Exception: if no server is found at all, the setup assistant still asks.)
- State file `AMS2-Server-Manager.state.txt` next to the tool

### v0.192
- New: complete English translation of the interface, all messages and both assistants
- Language selection German/English under Settings → General and in the setup assistant on the first start
- In-game chat messages in the chosen language

### v0.191
- New: getting-started assistant for beginners
- Setup assistant: SteamCMD next to the server folder, automatic retries, servers in tool subfolders are found, window adapts to the screen height, clearer colours and messages
- Fixes: crash in step 3 of the setup assistant, monitor CPU/RAM display

### v0.19
- New: setup assistant (find/install server via SteamCMD, copy data, network check), server update via SteamCMD
