# Changelog – AMS2 Server Control

[English](CHANGELOG.md)

### v0.2 (06.11.2026) – Discord + Netzwerk
- **Discord-Benachrichtigungen** (neuer Reiter Community → Discord): Webhooks für Server-Status, Ergebnisse und Meisterschaften, verschlüsselt gespeichert, mit **Test senden**; **Server online/offline** als eine Nachricht, die laufend aktualisiert wird; **Ergebnis** nach jedem Rennen (Podium, Klassensieger, schnellste Runde, Tabellenspitze, optional BUSTED IDIOTs); **neue Meisterschaft** automatisch beim ersten Rennen oder per Knopf »Discord«; Servername zum Kopieren für die Suche im AMS2-Serverbrowser; Deutsch oder English
- **Netzwerk-Check** unter Einstellungen → Netzwerk mit **Ampel auf der Übersicht**: Windows-Firewall (Knopf »Firewall freigeben«), öffentliche IPv4 / DS-Lite, Port 9000 nach außen offen, **Steam-Serverbrowser-Check** automatisch nach dem Serverstart (ohne API-Schlüssel), **Ports per UPnP freigeben**
- **Router-Anleitung**: FRITZ!Box mit Bildern Schritt für Schritt, dazu Speedport, Vodafone Station, o2 HomeBox, TP-Link, ASUS, Netgear und andere Router mit Kurzanleitung und Hersteller-Link; IP und Ports schon eingesetzt; auch im Einrichtungs-Assistenten

### v0.199 (02.11.2026)
- **Meisterschaft ohne Neustart**: Nach dem Rennen lädt das Tool das nächste Rennen automatisch – sind Spieler online, live an den Server (alle bleiben in der Lobby), sonst per Neustart. Im Chat: nächste Strecke, Tabellenspitze und der eigene Ballast. Ändert sich der Erfolgsballast, startet der Server nach einer Ansage 30 s später neu (der Server liest den Ballast nur beim Start – getestet)
- **Menü aufgeräumt**: neue Seite **»Community«** (unter »Strafen«) mit »Willkommen & Chat«, später Discord und Website; **VIP-Liste, reservierte Plätze und Admin-Befehle** auf der Seite **Fahrer** (Reiter »VIP & Admins«); **Meisterschaft ohne Neustart, Ansagen und Zufallswetter** unter **Meisterschaften → Automatik**; in den Einstellungen bleibt »BoP & Klassen-Limit«. Jeder umgezogene Reiter hat eigene Speicher-Knöpfe
- **Idioten-Regel** (statt Rüpel-Schutz, standardmäßig aus): zählt Crashs im Rennen als Punkte nach der **Aufprall-Stärke**, die der Server meldet – harter Einschlag 1, Kontakt ½, leichter Rempler 0; mit KI ½, derselbe Gegner nochmal ½, Startphase (20 s) ½ außer bei harten Einschlägen, **Abdrängen** (das andere Auto knallt kurz danach in die Bande) +½, Massenkarambolage (4+ Autos in 5 s) höchstens 1 – außer für den Auslöser, der 3 oder mehr Autos trifft. Punkte verfallen nach einstellbarer Zeit (Standard 5 Min.). Verwarnung ab 2, letzte Verwarnung ab 4, Kick ab 6 Punkten mit der Meldung **»BUSTED IDIOT«** (in beiden Sprachen); Wiederholungstäter bekommen eine Sperre; VIPs und Admins ausgenommen
- **Fahrer-Status**: normal → auffällig (1× gekickt, Verwarnungen kommen früher) → BUSTED IDIOT (mehrmals gekickt); beim Beitritt bekommen markierte Fahrer einen Hinweis, optional öffentliche Warnung; **zweite Chance** nach einstellbar vielen sauberen Rennen (Standard 5)
- **Testmodus** für die Idioten-Regel: KI zählt voll, Admins zählen mit, kein echter Kick/Bann (»TEST: Du würdest jetzt gekickt«), jeder Crash mit Punkten im Chat-Fenster – plus Rohdaten der Crash- und Abkürzungs-Ereignisse zum Prüfen
- **Strafregister und Achievements pro Steam-ID**: Verwarnungen, Kicks, Banns, letzter Vorfall, Statistik (Rennen, Siege, Podien, Poles, schnellste Runden, Runden); Achievements (Meilensteine, Erster Sieg, Seriensieger, Podiumsjäger, Polesetter, Zeitenjäger, Eisenmann, Fair-Play) bleiben für immer – vorhandene Ergebnisse werden beim ersten Start nachgetragen. Rechtsklick in der Fahrerliste: Strafregister anzeigen, Status hoch-/zurückstufen, Strafregister zurücksetzen
- **Rennsperre** für Wiederholungstäter (neuer Standard statt Stunden): erste Sperre 3 Rennen, danach gleich viel dazu (3 → 6 → 9) oder verdoppeln (3 → 6 → 12), höchstens 12 Rennen (alles einstellbar), optional »dauerhaft ab der X. Sperre«. Das Tool zählt nach jedem Rennen runter und kickt gesperrte Fahrer beim Beitritt (»⛔ noch 2 Rennen gesperrt«); das Rennen mit dem Kick zählt nicht mit
- Neue Seite **»Strafen«** im linken Menü: **Übersicht** (alle auffälligen Fahrer mit Status, Verwarnungen, Kicks, wievielte Sperre, Restsperre, letzter Vorfall; Rechtsklick: Strafregister, Sperre aufheben/verlängern, Status hoch/runter, zurücksetzen), **Sperrliste** (Renn-/Zeitsperren und dauerhafte Banns – vorher auf der Fahrer-Seite), **Strafen der Rennleitung** (aufheben) und **Einstellungen** (die Idioten-Regel ist hierher umgezogen)
- **Begrüßung im Spiel-Chat wird nicht mehr abgeschnitten**: lange private Nachrichten (Begrüßung, Meisterschaftsstand, Ballast, `!rank`) werden auf mehrere kurze Zeilen verteilt, eine alle 2,5 Sekunden; eigene Texte können mit `|` selbst getrennt werden, neuer Platzhalter `{races}`
- **Ergebnistabelle schmaler**: kurze Überschriften (Rd., Zeit, Abst., Beste, Pkt., %) mit vollem Namen als Tooltip; die CSV-Datei behält die vollen Namen
- Spalte **»Verwarnungen«** in der Fahrerliste und in der Meisterschaftstabelle (z. B. »⚠ 2 · 1× Kick« oder »⛔ noch 2 Rennen«), gelb bei auffälligen, rot bei gesperrten Fahrern bzw. BUSTED IDIOTs – in der Tabelle nur, wenn jemand Einträge hat
- Hauptfenster startet breiter (1600 × 900); **Monitor** steht im Menü jetzt unten bei Hilfe und Einstellungen
- Standard-Servername jetzt **»AMS2 Server Control Server«**; jede Installation bekommt eine eindeutige **Server-ID**
- **Admin-Befehle im Spiel-Chat**: `!skip`, `!skiprace`, `!restart`, `!kick Name`, `!ai an/aus`, `!admin` – nur für eingetragene Steam-IDs
- **Dauerbetrieb (Community-Modus)** pro Meisterschaft: niemand online → Rennen ohne Wertung überspringen; am Kalender-Ende von vorn (Punkte laufen weiter oder neue Saison mit Archiv); optional Wetter bei jedem Rennen neu würfeln
- **Meisterschaft Schritt 2**: Rennserie als Streckenquelle – »keine Rennserie« zeigt alle Strecken, eine Serie nur deren Rennen; einzeln holen oder alle übernehmen (ersetzen oder anhängen), Serien mischbar, ✓ für schon eingetragene Rennen
- **🎲 Zufall**: Zufalls-Saison, Wetter würfeln (Gewichtung einstellbar), zufällige Strecke und zufälliges Datum (Schnellrennen und Meisterschaft)
- Nach dem Rennen wird die nächste Strecke im Chat angesagt (auch bei Rotation)
- Server-Schalter »Anti-Rüpel-Kollisionen« heißt jetzt **»Ghosting bei Falschfahrern & Stehenden«** (mit Erklärung im Tooltip)
- **Server starten** startet das nächste Rennen der Meisterschaft, die gerade auf der Meisterschafts-Seite geöffnet ist (statt des Schnellrennens)
- **Rechtsklick** in Fahrerliste und VIP-Liste: **Steam-ID kopieren** und **Als Admin eintragen / austragen**
- **Speichern unter Einstellungen** behält eine laufende Meisterschaft (vorher wurde dabei auf das Schnellrennen umgeschaltet); nur »Rennen starten« / »Nur speichern« im Schnellrennen wechseln zum Schnellrennen
- `!skiprace` überspringt das Rennen **ohne Neustart**: das nächste Meisterschaftsrennen wird live geladen und alle bleiben auf dem Server – in der Lobby wechselt die Strecke sofort; während einer Session wird sie fürs nächste Event geladen und der Chat erklärt den Weg: Rennen starten lassen → zurück in die Box → zurück in die Lobby; übersprungene Rennen zählen nicht. Gibt es kein weiteres Rennen, kommt ein Hinweis
- `!skiprace` während einer Session: Ist das nächste Rennen schon geladen, kommt der Hinweis »Schon geladen: … kommt, sobald ihr wieder in der Lobby seid«; »übersprungen« wird zurückgesetzt, wenn das Rennen wieder geladen oder als nicht gefahren markiert wird
- `!skiprace` startet den Server nie neu – auch nicht, wenn sich der Erfolgsballast ändert (Hinweis im Chat)
- 🎲-Knöpfe orange mit schwarzem Würfel, damit er gut zu sehen ist
- **Zeitraffer-Rennen**: Schnellrennen → Ablauf mit Knöpfen 20/30/45/60/90/120 min (oder frei, z. B. 40) und »Gefühlte Dauer« 6/12/24 h – das Tool wählt die passende Zeitraffer-Stufe (1x–60x) für Tageszeit und Wetter und zeigt, was im Spiel vergeht (inkl. Hinweis »durch die Nacht«). In der Meisterschaft pro Rennen wählbar; Langstrecken aus echten Kalendern (ab 6 h) werden automatisch zu 60 Minuten mit passendem Zeitraffer
- 🎲 Zufallswetter würfelt so viele Wetter, wie Wetter-Slots eingestellt sind; »wie Rennen« bleibt erhalten
- Rennkarten zeigen übersprungene Rennen (»⏭ übersprungen«)

### v0.1985 (01.11.2026)
- **Neues Design: Schiebeschalter** statt Häkchen – orange = an, grau = aus, der Knopf gleitet beim Umschalten (überall im Tool und im Assistenten)
- **Moderne Rechtsklick-Menüs**: dunkel, abgerundet, orange Markierung, Symbole vor den Einträgen (Meisterschaft, Tabelle, Ergebnisse, Chat, Fahrer)
- **Dunkle Titelleiste** für alle Fenster (Windows 10/11); unter Windows 11 zusätzlich oranger Fensterrahmen
- Dunkle Scrollbalken (Versuch über den Windows-Dark-Mode – bleiben je nach Windows-Version hell)
- Tabellen: Spaltenköpfe brechen nicht mehr um (»Beste Runde« wurde abgeschnitten), Spalten sind mindestens so breit wie ihre Überschrift
- »Server starten« lädt automatisch das nächste Meisterschaftsrennen, wenn das geladene schon gefahren ist
- Standard-Datum für neue Rennen ist Hochsommer (21. Juni, Südhalbkugel 21. Dezember)

### v0.198 (01.11.2026)
- Neu: eigene Seite **✎ Vorlagen** (links in der Navigation unter Monitor) – Vorlagen als Karten mit Neu, Bearbeiten, Duplizieren, Löschen und »Im Schnellrennen fahren«
- Vorlagen werden nur noch auf dieser Seite angelegt – im Schnellrennen gibt es oben nur noch »Vorlage laden«
- **Vorlagen-Modus**: Bearbeiten im Schnellrennen-Editor mit orangem Hinweis, »Vorlage speichern« / »Abbrechen«; das Schnellrennen wird so lange beiseitegelegt und kommt unverändert zurück
- **Speicher-Knöpfe rot/grün**: rot mit »●« bei ungespeicherten Änderungen, grün wenn alles gespeichert ist (Einstellungen, Schnellrennen, Vorlagen-Modus, Meisterschafts-Editor); Abbrechen fragt bei ungespeicherten Änderungen nach
- Meisterschaft Schritt 1 aufgeräumt: Infozeilen entfernt, »Renn-Setup aus« heißt jetzt **»Startwerte laden aus«**, der Rennserie-Knopf zeigt die gewählte Serie
- **GT3-Rennserien** tragen jetzt GT3 Gen1 **und** GT3 Gen2 ein
- Server-Addon heißt jetzt **TGC_Server_Manager** (vorher tgc_manager) – das alte wird beim nächsten Serverstart automatisch entfernt, Rangliste und Ergebnisse werden übernommen
- **Mouseover-Hilfen** für Navigation und die wichtigsten Knöpfe
- **Hilfe-Fenster** im abgerundeten Design, eigener Reiter **Changelog**
- **Standard-Datum Hochsommer** statt »heute«: neue Rennen bekommen den 21. Juni (Südhalbkugel wie Bathurst/Interlagos: 21. Dezember), Folgerennen +14 Tage innerhalb des Sommers – Sonne bis in den Abend. Echte Rennserien-Kalender behalten ihre Original-Termine
- Meisterschaft: Ist das geladene Rennen schon **gefahren**, lädt **»Server starten«** automatisch das nächste Meisterschaftsrennen (mit Ballast und Tabelle)
- Meisterschaft: **Rechtsklick → »Als nächstes Rennen festlegen«** – »Nächstes Rennen starten« lädt dann genau dieses Rennen; »Vormerkung aufheben« stellt die Reihenfolge wieder her
- **KI auffüllen repariert:** Der Server gibt KI nur auf freien Plätzen (KI-Plätze = Startplätze − max. Spieler). Die Option steht jetzt bei »Startfeld« bzw. »Startfeld & KI« mit Anzeige »→ 16 Plätze für KI«; sind keine Plätze frei, bietet das Tool beim Speichern an, max. Spieler zu halbieren
- **Meldungen und Eingabefenster im Design des Tools** (dunkel, abgerundet, runde Knöpfe) statt grauer Windows-Fenster – z. B. Update-Frage mit »Jetzt aktualisieren« / »Später«
- Meisterschaft: **Rechtsklick auf einen Fahrer in der Tabelle → »Ballast fürs nächste Rennen ändern …«** (gilt nur für dieses Rennen, Markierung ✎, »Ballast automatisch berechnen« nimmt es zurück)
- Ergebnisse: Sessions wieder **nach Datum sortiert** (neueste oben), Tabelle passt sich der Fensterbreite an (kein Abschneiden mehr), »Beste Runde« statt »Schnellste Runde« als Spaltenname
- Erfolgsballast richtet sich nach dem zuletzt **gefahrenen** Rennen (zeitlich), nicht nach der Kalender-Reihenfolge – wichtig bei vorgemerkten oder übersprungenen Rennen
- Meisterschaft Schritt 1: **alle Optionen wie im Schnellrennen** (Fahrhilfen, Box & Technik, Rennablauf mit »Startfeld mit KI auffüllen«, Fairness, Erweitert)
- Rennkarten zeigen jetzt auch **Training und Quali**; »Noch keine Ergebnisse« in der Tabelle nicht mehr abgeschnitten
- Schnellrennen: der gewählte Abschnitt-Reiter (Strecke & Fahrzeuge, Ablauf …) wird orange markiert
- README: »All-in-One-Lösung« und »Keine Installation nötig«


### v0.197 (31.10.2026)
- Meisterschaft: neuer Schritt **3 Fahrer** mit **Startliste** (Nr., Name, Steam-ID, Team, Ballast, Leistung, Luftwiderstand), »Aus Ergebnissen übernehmen« und »Fahrer vom Server übernehmen«
- **Feste Namen** aus der Startliste in Tabelle und Teamwertung, **Allow-Liste** (nur Fahrer aus der Startliste dürfen beitreten, Option)
- **Teamwertung**: alle Fahrer oder die besten 2 pro Rennen, Punkte bei Teamwechsel wahlweise mitnehmen; Umschalter »Teamwertung / Fahrerwertung« in der Meisterschaft
- **Erfolgsballast** in Schritt 1: »Nach dem letzten Rennen« oder »Aufbauend mit Abbau«, kg für Platz 1–3, Abbau und Höchstgewicht einstellbar; Ballast fürs nächste Rennen steht in der Tabelle, Fahrer bekommen ihn als private Nachricht
- **Balance of Performance** für alle Rennen unter Einstellungen → Spieler & VIP (Ballast, Leistung, Luftwiderstand pro Steam-ID) – über `ballastFile`, `powerScalarFile` und `dragScalarFile` des Servers
- **Eigene Klasse pro Meisterschaftsrennen** (Schritt 2)
- **Persönliche Begrüßung** mit Punktestand der Server-Rangliste und der laufenden Meisterschaft, Text mit Platzhaltern anpassbar
- **Platzhalter `{link}`** für die Willkommensnachricht, **VIP-Ankündigung** im Spiel-Chat (abschaltbar)
- **Chat**: Steam-ID im Chatlog hinter jedem Namen (auch bei Beitreten/Verlassen), Farben im Chat-Fenster (VIP Gold mit ★, Admin Orange, Server Grau), Rechtsklick: Fahrer bannen (auch wenn er schon weg ist), Steam-ID kopieren, Steam-Profil öffnen
- **Fahrer-Seite**: Spalte »Info« mit VIP, Team und Ballast

### v0.196 (31.10.2026)
- Neuer Name: **AMS2 Server Control** (`AMS2-Server-Control.exe`, ohne Versionsnummer im Dateinamen). Der Daten-Ordner `ServerManager` wird beim ersten Start automatisch zu `ServerControl` umbenannt, alte `AMS2-Server-Manager.*.txt`-Dateien ebenso
- Neu: **Hilfe-Fenster** mit Anleitung und Funktionen & Changelog, Logo, »Auf Updates prüfen« und GitHub-Link
- Neu: **automatisches Update** über GitHub-Releases (abschaltbar)
- Meisterschaft Schritt 1: **Startfeld & KI**, **Regeln & Fahrhilfen** (inkl. Boxengasse) und **Renn-Optionen** direkt einstellbar
- Meisterschaft Schritt 2: pro Rennen **Training/Quali-Dauer** (0 = aus), **bis zu 4 Wetterwechsel** im Rennen, Training und Quali mit eigener Startzeit und eigenem Wetter, **Ablauf & Wetter für alle Rennen übernehmen**
- Meisterschaft Schritt 3: **Streichresultate** und **eigene Tabelle je Klasse** bei Multiclass
- Neue Renn-Optionen (Schnellrennen und Meisterschaft): **Zeitraffer** für Tageszeit und Wetter, **Stint-Limit** und **Runden-Limit** in der Quali, **Mindest-Rang** und **Mindest-Stärke** (Online-Ruf)
- Exporte landen standardmäßig in `ServerControl\export`
- Meisterschaft Schritt 2 neu aufgeteilt: Streckenauswahl und Kalender oben, darunter Datum, Uhrzeit & Wetter sowie die Dauer
- Carbon-Hintergrund wieder entfernt

### v0.195 (31.10.2026)
- Neu: **Chat-Sprache im Spiel** einstellbar (wie das Tool, Deutsch, English) – unabhängig von der Sprache des Tools
- Neu: **Name im Chat** – eigene Nachrichten aus dem Tool erscheinen als »Admin: Hallo« (Name frei wählbar, leer = ohne)
- Neu: **Strecke bzw. Meisterschaft am Servernamen** (z. B. »TGC Server | Spa-Francorchamps 2022«), abschaltbar unter Einstellungen → Server → Anzeige
- Neu: **Boxengassen-Tempolimit** unter Regeln & Fahrhilfen (Strecken-Standard oder 40–200 km/h, Server-Wert `PitSpeedLimit`)
- Neu: **Export/Import der Einstellungen** (`.ams2settings`, Passwort nur auf Wunsch)
- Neu: **Export/Import von Meisterschaften** (`.ams2champ`) mit Fortschritt, Ergebnissen und Strafen oder als frische Meisterschaft; vorhandene werden nie überschrieben, sondern unter anderem Namen gespeichert
- Meisterschafts-Editor Schritt 1 neu: Setup gilt sofort (kein »Übernehmen« mehr), eigener Kasten **Fahrzeuge** mit Klassen, Multiclass, max. Autos pro Klasse und festem Auto
- Neu: **Carbon-Hintergrund** in Kopfleiste, Navigation, Fußleisten und Assistenten (abschaltbar)
- Schnellrennen, Einstellungen und Meisterschafts-Editor passen sich der Fensterbreite an – kein seitliches Scrollen mehr
- Rennserien-Knopf im Schnellrennen kompakter neben den Vorlagen-Knöpfen
- Rotation (`sms_rotate`) entfernt; eine noch aktive Rotation wird beim nächsten Speichern aus der server.cfg genommen

### v0.194 (31.10.2026)
- Neu: **Rennserien** im Schnellrennen und im Meisterschafts-Editor, Auswahl im modernen Look (Karten, Kategorien GT3 / Langstrecke / Markenpokale / Klassiker)
- Eine Rennserie stellt die Klassen automatisch ein – auch Multiclass: IMSA 2026 (LMDh, LMP2, GT3), IMSA DPi 2019 (DPi, LMP2, GTE, GT3), WEC 2026 (LMDh, GT3), Le Mans Series 2005 (LMP1, LMP2, GT1, GT2), FIA GT 2005 (GT1, GT2), Porsche Supercup, Lamborghini Super Trofeo, DTM Gruppe A sowie GT World Challenge, DTM, GT Masters, IGTC und IMSA GTD (GT3)
- Neue echte Kalender: IMSA 2026, IMSA 2019, WEC 2026, Le Mans Series 2005, FIA GT 2005, Porsche Supercup 2026, Super Trofeo Europe 2026, DTM 1991 und 1992
- Neu: Streckenfilter »Nur zur Klasse passende Strecken« (Schnellrennen) bzw. »Passend zur Klasse« (Meisterschaft): Art der Strecke und Epoche der Autos werden berücksichtigt
- WEC 2026 nutzt LMDh statt der AMS2-Klasse »Hypercars« (das sind Straßen-Supersportwagen)
- Fix: VIR wird in den Kalendern als volle Strecke (Full) statt Patriot eingetragen, Suzuka-Ersatz ist jetzt Kansai GP

### v0.193 (31.10.2026)
- Fix: Einrichtungs- und Start-Assistent öffnen sich nur noch beim allerersten Start automatisch – auch wenn sie abgebrochen werden. Danach gibt es sie über Einstellungen → Allgemein bzw. Experten. (Ausnahme: Wird gar kein Server gefunden, fragt der Einrichtungs-Assistent weiterhin nach.)
- Die alte Willkommensmeldung nach einem abgebrochenen Start-Assistenten entfällt
- Merker-Datei `AMS2-Server-Manager.state.txt` neben dem Tool

### v0.192 (31.10.2026)
- Neu: Englische Übersetzung der kompletten Oberfläche, aller Meldungen und beider Assistenten
- Sprachwahl Deutsch/English unter Einstellungen → Allgemein und beim ersten Start im Einrichtungs-Assistenten (Windows-Sprache vorausgewählt)
- Chat-Nachrichten im Spiel (Addon) in der gewählten Sprache
- Englische README (`README_AMS2-Server-Manager_v0.193_EN.md`)

### v0.191 (30.10.2026)
- Neu: Start-Assistent für Einsteiger im modernen Look (8 Schritte, Karten-Auswahl, Erklärungen, sinnvolle Vorauswahl)
- Einrichtungs-Assistent: SteamCMD liegt neben dem Server-Ordner, Standardziel ist `<Tool-Ordner>\Server`
- Einrichtungs-Assistent: automatische Wiederholung bei „Missing configuration“, Server in Unterordnern des Tools werden gefunden, Fenster passt sich der Bildschirmhöhe an (kein Scrollen), Info-Hinweise blau, DS-Lite-Hinweis gelb und ganz unten, Abbrechen mit klarer Meldung
- Fix: Absturz in Schritt 3 (Netzwerk) des Einrichtungs-Assistenten
- Fix: Monitor zeigt CPU und RAM des Servers richtig an

### v0.19 (30.10.2026)
- Neu: Einrichtungs-Assistent im modernen Look (Schritt-Anzeige, Auswahlkarten, runde Knöpfe, Fortschrittsbalken)
- Server-Suche in allen Steam-Bibliotheken; auch bei einem Fund wird gefragt: benutzen, neu per SteamCMD installieren oder Ordner wählen
- Neuinstallation per SteamCMD (anonym, App 1338040) mit Fortschritt; Daten können in die neue Installation übernommen werden
- SteamCMD liegt neben dem Server-Ordner (`steamcmd`); Standard-Zielordner ist `<Tool-Ordner>\Server`
- Automatische Wiederholung (bis zu 3-mal) bei „Missing configuration“ und Verbindungsproblemen, App-Daten werden vorher geladen
- Netzwerk-Check: lokale IPv4, Ports (zum Kopieren), IPv4-Hinweis, feste IP, DS-Lite/CGNAT-Prüfung per Fritzbox-UPnP, Bind-IP, Firewall
- Neu unter Experten: »Server aktualisieren« per SteamCMD
- Ein gespeicherter Server-Ordner (path.txt) hat jetzt Vorrang vor dem Ordner neben dem Tool
- Fix: Monitor zeigt CPU und RAM des Servers wieder richtig an (Variable wurde überschrieben)

### v0.18 (30.10.2026)
- Schnellrennen im modernen Karten-Look wie die Meisterschaft: Strecken und Autos als Karten mit orangem Rahmen für die Auswahl
- Neue Rennkarte oben als Zusammenfassung (Strecke, Fahrzeuge, Sessions, Datum, Uhrzeit, Wetter, Wertung), aktualisiert sich sofort
- »Autos in der Auswahl« als aufgeräumte Liste mit Klassen-Überschriften statt Textfeld

### v0.172 (30.10.2026)
- Fix: Beim Start erschien ein Fenster mit „True“, sobald ein VIP eingetragen war
- Fix: Startfehler „<#“ (doppelte Kodierungs-Kennung am Dateianfang) behoben

### v0.171 (30.10.2026)
- Fix: Der Admin-Chat zeigt jetzt Spieler-Nachrichten, Server-Antworten (z. B. auf `!rank`), Willkommensnachrichten sowie Beitreten/Verlassen an. Vorher kam nichts an, weil das Tool die Ereignisse des Servers falsch einsortiert hat
- Fix: Beim Beitreten wird der richtige Spielername angezeigt
- Session-Wechsel (Training, Qualifying, Rennen) erscheinen im Chat

### v0.17 (30.10.2026)
- Neu: Rennleitung. Rechtsklick auf einen Fahrer im Ergebnis → Strafe vergeben: Punktabzug, Zeitstrafe oder Disqualifikation, mit Pflicht-Begründung und optionaler Chat-Meldung
- Bestrafte Fahrer rot mit ⚑ und Tooltip, in der Meisterschaftstabelle z. B. „18 (−5)“
- Strafenliste gesamt (Ergebnisse) und pro Meisterschaft, Strafen lassen sich aufheben
- Strafen zählen in Meisterschaft, Statistik, Saison und (nach dem nächsten Speichern) bei `!rank`/`!top`
- Kontextmenü im Meisterschaftskalender: „Ergebnis anzeigen“ für gefahrene Rennen

### v0.164 (30.10.2026)
- Der Servername steht jetzt groß oben links und in der Titelleiste (auch in Taskleiste und Alt+Tab); er passt sich nach dem Speichern sofort an
- Toolname und Version stehen klein links unten unter »Einstellungen«

### v0.163 (30.10.2026)
- Meisterschaften: Renndauer pro Rennen wahlweise in Runden, Minuten oder »wie im Setup«
- Neuer Knopf »Dauer für alle Rennen übernehmen«
- Schritt 2 (Strecken) kompakter, passt jetzt ohne Scrollen auf kleinere Bildschirme
- Das Reifen-Icon erscheint auch oben links in der Titelleiste
- Ältere Meisterschaften werden automatisch übernommen (Langstrecken bleiben in Minuten)

### v0.162 (28.10.2026)
- Fehler beim Speichern einer Meisterschaft behoben (»System.Object[] … Int64«)
- Eigene Punkte einer Meisterschaft werden jetzt richtig übernommen (vorher fielen sie auf die Standardwerte zurück)
- Das Zeichen »&« wird jetzt auch in Gruppen-Überschriften angezeigt

### v0.161 (28.10.2026)
- Upload und Download: neue Option »unbegrenzt«, als Standard eingeschaltet
- Neuer Meisterschafts-Kalender »Langstrecken-Klassiker« (2 h bis 24 h, Rennen nach Zeit)
- Renndauer pro Rennen bis 1440 Minuten; Langstrecken werden im Kalender in Stunden angezeigt

### v0.16 (28.10.2026)
- Neu: **Meisterschaften** mit Kartenübersicht, Editor in vier Schritten und eigener Tabelle (Gold, Silber, Bronze)
- Rennkalender per **Drag & Drop**: Strecken hineinziehen, Reihenfolge ändern, herausziehen; pro Rennen Datum, Startzeit, Wetter und Renndauer
- **Kalender echter Rennserien** 2022–2026 (GT World Challenge Europe, DTM, ADAC GT Masters, IMSA GTD, Intercontinental GT Challenge) mit Ersatzstrecken für Kurse, die AMS2 nicht hat
- Eigene Punkte pro Meisterschaft
- Großer Knopf **»Nächstes Rennen starten«** (auch in der Übersicht); gefahrene Rennen werden automatisch abgehakt
- Rechtsklick auf ein Rennen: jetzt starten, wiederholen, als gefahren markieren
- Ergebnisse zeigen, zu welcher Meisterschaft ein Rennen gehört; `!info` nennt die Meisterschaft
- Streckennamen wie »Nurb_GP_2020« werden lesbar angezeigt (»Nürburgring GP 2020«)

### v0.151 (27.10.2026)
- Der Server legt die Strecke jetzt immer fest; das Häkchen »Keine feste Strecke« ist entfernt. Ohne gewählte Strecke lässt sich kein Rennen starten
- Anzeige »Host wählt die Strecke« korrigiert: Solange niemand auf dem Server ist, zeigt das Tool die eingestellte Strecke
- Übersicht bei Multiclass repariert (Klassen, Session und Spieler wurden nicht angezeigt)
- Das Zeichen »&« wird auf Knöpfen und Überschriften wieder angezeigt
- Symbole in der Navigation funktionieren jetzt auf jedem Windows (vorher teils leere Kästchen)

### v0.15 (27.10.2026)
- Neue Punktevergabe unter Einstellungen → Wertung & Punkte: Platz 1 bis 20 mit je einem Kästchen, Standard 25 bis 1
- Extrapunkte für Pole-Position (Qualifying) und schnellste Runde (Rennen), jeweils abschaltbar
- Platzierung geht vor: Extrapunkte überholen nie den Vordermann
- Neu: »Neue Saison starten« setzt die Rangliste auf null, Statistik standardmäßig für die aktuelle Saison
- Schnellrennen: neuer Abschnitt »Wertung« mit »Wertung aktivieren« (aus = Spaßrennen ohne Punkte)
- Ergebnisse zeigen die Spalte »Extra« (Pole, schnellste Runde); KI ist standardmäßig ausgeblendet
- `!info` im Chat nennt die Wertung, `!rank` zählt die Extrapunkte mit
- Rotation aus dem Schnellrennen entfernt, sie steht jetzt unter Einstellungen → Experten; eine alte Rotation wird einmalig ausgeschaltet

### v0.14 (27.10.2026)
- Neue Seite **Schnellrennen** in der Navigation: das komplette Renn-Setup übersichtlich untereinander, Vorlagen oben, Sprungknöpfe zu den Abschnitten und unten der große Knopf **Rennen starten**
- Neuer Menüpunkt **Meisterschaften** (Inhalt folgt in einer der nächsten Versionen)
- Einstellungen aufgeräumt: senkrechte Liste mit sieben Seiten (Server, Netzwerk, Willkommen & Chat, Spieler & VIP, Wertung & Punkte, Leistung & Energie, Experten), alles einspaltig und luftiger
- Presets heißen jetzt Vorlagen; die Rotation steht im Schnellrennen
- »Live übernehmen« steht jetzt im Schnellrennen, »Listen laden« unter Experten
- Rennen starten fragt nach, wenn Spieler online sind

### v0.13 (26.10.2026)
- Fehler beim Start behoben (»NULL kann nicht in System.Drawing.Color konvertiert werden«)
- Neues Layout in Schwarz-Orange mit besserem Kontrast und etwas größerer Schrift
- Navigation links: großer Knopf Server starten/stoppen, Neustart, Seiten Übersicht, Fahrer, Chat, Ergebnisse, Monitor und Einstellungen
- Chat und Fahrerliste sind jetzt Seiten im Hauptfenster statt eigener Fenster
- Kopfleiste mit Status, Strecke, Session, Spielern und Balken für CPU, RAM, Upload und Ping
- Neu: Übersicht mit Karten und Live-Reihenfolge (KI ausgeblendet, per Häkchen einblendbar)
- Neu: Monitor mit Rundinstrumenten (CPU, RAM, Upload, Download, Pakete/s, Ping), Verlaufskurve und Höchstwerten
- Neu: Wetter und Startzeit für Training, Quali und Rennen einzeln, mit »wie Rennen« und »Echtes Wetter«. Startzeit als Uhrzeit (z. B. 15:00 Uhr). QualifyDateHour aus den Experten-Attributen wird übernommen
- Neu: Einstellungen → Erweitert mit Tick-Rate, Priorität für Server und Tool, Energiesparen verhindern, Energiesparplan Höchstleistung, Laptop-Deckel-Prüfung und Leitungskapazität
- Neu: Knopf »Diagnose speichern« für die Fehlersuche (z. B. wenn der Chat nicht ankommt)
- Max. Spieler wird automatisch auf die Größe des Grids begrenzt
- Flags-Zahl nach Einstellungen → Erweitert verschoben
- KI-Fahrer in Tabellen besser lesbar
- Vorsicht beim Stoppen und Neustarten: Rückfrage, wenn Spieler online sind

### v0.121 (25.10.2026)
- Schadensstärke (Niedrig/Mittel/Hoch/Maximal) steht jetzt im Tab »Fahrhilfen & Regeln« direkt unter »Schaden« statt bei den Renn-Optionen

### v0.12 (25.10.2026)
- Neu: Admin-Chat-Fenster (mitlesen, an alle oder privat schreiben, Verlauf als Textdatei)
- Neu: Fahrerliste mit Rechtsklick-Menü: anschreiben, kicken, bannen (1 h / 24 h / dauerhaft), VIP. Chat-Hinweis 5 Sekunden vorher
- Neu: Sperrliste für dauerhafte Banns in der server.cfg, mit „Entbannen“
- Neu: Knopf „Nächste Session“
- Neu: Renn-Optionen: Pflicht-Boxenstopps, Reifenwechsel-Pflicht, Tank-Verbot, Boxenstopp-Steuerung, fliegender Start, Einführungsrunde, Startaufstellung, Extra-Runde, Full Course Yellow, geplante FCY, Streckenzustand, private Quali, Schadensstärke, Strafen für Boxenlinie/Durchfahrt, erlaubte Abkürzungen
- Neu: Server-Addon „tgc_manager“ mit MOTD, Chat-Befehlen (!rank, !top, !best, !record, !info, !next, !help), Ergebnis-Aufzeichnung, Rangliste, reservierten Plätzen und Klassen-Limit
- Neu: Tab „Ergebnisse“ (Training, Quali, Rennen; Gesamt oder pro Klasse; 75-%-Regel; CSV-Export) mit dauerhaftem Archiv
- Neu: Tab „Statistik“ mit Top-Fahrern, Punkten, Rundenrekorden und Fahrerprofil
- Neu: Tab „Chat & Addon“ für MOTD, Chat-Befehle, Wertung, VIP-Liste und Klassen-Limit
- DriveThroughPenalty und AllowedCutsBeforePenalty werden aus den Experten-Attributen in die neuen Renn-Optionen übernommen

### v0.11 (25.10.2026)
- Strecken, Autos und Klassen werden immer mit Namen angezeigt statt mit IDs, auch ohne laufenden Server (230 Strecken, 280 Autos, 109 Klassen aus der `DedicatedServerCmd.exe`)
- Schaden, Reifenverschleiß, Sprit, Strafen, Kameras und Wetter sind sofort auswählbar, mit deutschen Namen
- Streckeninfos (Land, Länge, max. Grid, DLC) und Auto-DLC kommen jetzt direkt vom Server
- Flags auf Stand der Server-Version: ALLOW_VEHICLE_RESET (2097152) statt GHOST_GRIEFERS, neu DISABLE_TRACKSIDE_OBJECT_COLLISIONS (8192)
- Unbekannte IDs werden als „Unbekannte Strecke / Auto / Klasse“ markiert

### v0.10 (25.10.2026)
- Erste Version
- Start, Stopp, Neustart, Statusanzeige mit Spielerliste, Live-Log
- Alle Server-Einstellungen inklusive Bind-IP und Ports
- Strecken- und Autoauswahl mit Daten aus dem AMS2-Wiki (259 Autos, 210 Layouts), Filter und Suche
- Fahrzeug-Modi: freie Wahl, eine Klasse, Multiclass bis 4 Klassen, festes Auto
- Flags als Häkchen mit automatischer Berechnung, auch negative Werte (COOLDOWNLAP)
- Presets und Rotation (`sms_rotate`)
- Übernahme der vorhandenen `server.cfg` beim ersten Start, automatische Backups
