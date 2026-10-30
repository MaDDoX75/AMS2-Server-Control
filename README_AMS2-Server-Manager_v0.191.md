# AMS2 Server Manager v0.191

GUI für den **Automobilista 2 Dedicated Server**: Server einstellen, Strecke und Autos wählen, Regeln und Fahrhilfen setzen, Presets und Rotation verwalten, Start, Stopp und Neustart per Knopfdruck. Dazu kommen Admin-Chat, Fahrerliste mit Kick und Bann, Ergebnisse nach jeder Session, eine Statistik mit Rangliste, Chat-Befehle wie `!rank` und eine Willkommensnachricht.

## Installation

1. `AMS2-Server-Manager_v0.191.exe` irgendwo hinlegen, am einfachsten in den Ordner des Dedicated Servers (neben `DedicatedServerCmd.exe`).
2. Die EXE starten.
3. Beim ersten Start öffnet sich der **Einrichtungs-Assistent** (siehe unten). Ist schon ein eingerichteter Server da, startet das Tool direkt.

## Einrichtungs-Assistent

Öffnet sich beim ersten Start automatisch und jederzeit über *Einstellungen → Experten → Einrichtungs-Assistent*.

1. **Server**: Das Tool sucht in allen Steam-Bibliotheken und neben dem Tool nach dem Dedicated Server und zeigt alle Funde als Karten. Du wählst immer selbst:
   - eine **gefundene Installation benutzen**,
   - **neu per SteamCMD installieren** (kostenlos, ohne Steam-Login, App 1338040). Vorgeschlagen wird der Unterordner `Server` im Ordner des Tools, oder
   - einen **Ordner selbst wählen**.
   
   Wechselst du auf eine andere Installation, kannst du **deine Daten übernehmen**: Einstellungen, Vorlagen, Meisterschaften, Ergebnisse, Strafen und VIP-Liste. Die alte Installation bleibt unverändert.
2. **Installation**: SteamCMD wird bei Bedarf geladen und installiert den Server, mit Fortschrittsbalken und Log. Beim allerersten Start aktualisiert sich SteamCMD selbst. Meldet Steam dabei „Missing configuration“ oder gibt es Verbindungsprobleme, versucht das Tool es automatisch bis zu 3-mal. Danach werden die Daten kopiert.
3. **Netzwerk**: eine Checkliste mit
   - der lokalen IPv4 des PCs und dem Tipp, ihm im Router immer dieselbe Adresse zuzuweisen,
   - den freizugebenden Ports (Knopf **Ports kopieren**),
   - der Prüfung auf **DS-Lite/CGNAT**: Das Tool fragt die Fritzbox per UPnP nach ihrer öffentlichen IPv4 und vergleicht sie mit der Adresse, die der Server im Log meldet,
   - Bind-IP und Windows-Firewall.
4. **Fertig**: Zusammenfassung. Bei einem Wechsel des Server-Ordners startet das Tool neu.

Der gewählte Ordner wird in `AMS2-Server-Manager.path.txt` neben dem Tool gespeichert. SteamCMD liegt im Ordner `steamcmd` **neben** dem Server-Ordner. In den Server-Ordner selbst darf es nicht, das lehnt Steam ab. Beispiel bei einer Neuinstallation: Tool in `D:\AMS2\`, Server in `D:\AMS2\Server\`, SteamCMD in `D:\AMS2\steamcmd\`. SteamCMD bleibt für spätere Updates liegen.

## Start-Assistent (erste Schritte)

Erscheint beim allerersten Start des Server Managers und jederzeit über *Einstellungen → Allgemein → Start-Assistent*. Er ist für alle gedacht, die noch nie einen Server betrieben haben. Auf jeder Seite ist ein sinnvoller Wert vorausgewählt, man kann also einfach immer „Weiter“ klicken.

1. **Start**: kurze Erklärung, was das Tool kann (Schnellrennen, Meisterschaft, Einstellungen)
2. **Server**: Servername, optionales Passwort, maximale Spielerzahl, jeweils mit Erklärung
3. **Strecke**: Auswahl als Karten mit Suchfeld. Strecken mit ★ sind Einsteiger-Tipps.
4. **Autos**: freie Wahl, beliebte Klassen (z. B. GT3) oder jede andere Klasse
5. **Dauer**: *Kurz* (10/10/15 min), *Mittel* (15/15/30 min) oder *Lang* (20/20/60 min) für Training, Quali und Rennen
6. **Regeln**: *Locker* (Fahrhilfen erlaubt, kein Verschleiß), *Ausgewogen* (wie im echten Auto) oder *Simulation* (keine Fahrhilfen, voller Schaden, Defekte)
7. **Punkte**: mit oder ohne Wertung
8. **Fertig**: Zusammenfassung, dann **Speichern & Server starten** oder **Nur speichern**

Alles landet in den ganz normalen Einstellungen. Danach siehst und änderst du es im Schnellrennen und unter Einstellungen.

## Server aktualisieren

*Einstellungen → Experten → Server aktualisieren* holt die neueste Server-Version per SteamCMD. Läuft der Server, fragt das Tool vorher und stoppt ihn. Fortschritt und Ergebnis stehen direkt darunter. Während des Updates lässt sich der Server nicht starten. Nach einem AMS2-Update danach **Listen laden** klicken, damit neue Autos und Strecken auftauchen.

## Erste Schritte

1. Links unten **Einstellungen** öffnen und **Speichern** klicken. Das Tool schreibt eine saubere `server.cfg`. Die alte Datei wird vorher in `ServerManager\backups` gesichert.
2. Links **Schnellrennen** öffnen, Strecke, Autos und Regeln einstellen und **Rennen starten** klicken.

Alle Strecken, Autos, Klassen, Wetter- und Regelwerte sind mit Namen im Tool eingebaut. Sie stammen direkt aus der `DedicatedServerCmd.exe` (Server-Build vom 01.09.2026).

## Aufbau des Fensters

- **Kopfleiste oben**: groß der **Servername** (auch in der Titelleiste und Taskleiste), dazu Status des Servers, aktuelle Strecke und Session, Spieler, dazu kleine Balken für CPU, RAM, Upload und Ping. Grün = alles gut, gelb ab 70 %, rot ab 90 %.
- **Links**: der große Knopf **Server starten / Server stoppen**, darunter **Neustart**. Sind Spieler online, fragt das Tool vorher nach.
- **Navigation links**: Übersicht, Schnellrennen, Meisterschaften, Fahrer, Chat, Ergebnisse, Monitor. Ganz unten **Einstellungen**.

| Seite | Inhalt |
|---|---|
| **Übersicht** | Karten für Server, Strecke, Session und Spieler, Knopf **Nächste Session**, Warnungen und die **Live-Reihenfolge** (KI per Häkchen einblendbar) |
| **Schnellrennen** | Das komplette Renn-Setup auf einer Seite (siehe unten) mit dem Knopf **Rennen starten** |
| **Meisterschaften** | Meisterschaften anlegen und fahren, mit eigener Tabelle (siehe unten) |
| **Fahrer** | Wer gerade auf dem Server ist, mit Rechtsklick-Menü und Sperrliste (siehe unten) |
| **Chat** | Admin-Chat (siehe unten) |
| **Ergebnisse** | Reiter **Ergebnisse** (alle Sessions, Gesamt oder pro Klasse, CSV-Export) und **Statistik** (Top-Fahrer, Rundenrekorde, Fahrerprofil per Doppelklick) |
| **Monitor** | Reiter **Auslastung** (Rundinstrumente, Verlauf, Höchstwerte) und **Server-Log** |
| **Einstellungen** | alles, was den Server selbst betrifft (siehe unten) |

## Schnellrennen

- **Oben**: **Vorlage** wählen und **Laden**, das aktuelle Setup **Als Vorlage speichern** oder eine Vorlage **Löschen**. Vorlagen hießen früher Presets.
- Darunter die **Rennkarte**: Sie zeigt auf einen Blick Strecke, Fahrzeuge, Training/Quali/Rennen, Datum, Uhrzeit, Wetter und ob gewertet wird. Sie aktualisiert sich sofort, wenn du etwas änderst.
- Darunter Sprungknöpfe zu den Abschnitten.
- **Strecken und Autos als Karten**: Die gewählte Strecke bzw. das gewählte Auto hat einen orangen Rahmen und „✓ gewählt“. DLC-Inhalte sind violett markiert. *Autos in der Auswahl* zeigt pro Klasse alle Autos mit Hersteller, Baujahr und DLC.
- **Abschnitte** (untereinander, mit Mausrad scrollen): 1 Strecke, 2 Fahrzeuge, 3 Ablauf (Training, Quali, Rennen, Grid, KI, Datum), 4 Wetter & Uhrzeit, 5 Regeln & Fahrhilfen, 6 Renn-Optionen, 7 Wertung.
- **Wertung aktivieren**: an = das Rennen zählt für die Rangliste; aus = Spaßrennen, das Ergebnis wird gespeichert, aber ohne Punkte. Vorlagen merken sich das Häkchen.
- **Unten**:
  - **Rennen starten**: speichert und startet den Server neu (oder startet ihn, wenn er aus ist). Sind Spieler online, fragt das Tool vorher und bietet als Alternative »Live übernehmen« an.
  - **Nur speichern**: schreibt die `server.cfg`, ohne neu zu starten.
  - **Live übernehmen**: schickt das Setup an den laufenden Server. Es gilt ab der nächsten Session, ganz ohne Neustart.

## Meisterschaften

- **Übersicht**: Jede Meisterschaft ist eine Karte mit Klassen, Fortschritt, Führendem und dem nächsten Rennen. Klick auf eine Karte öffnet sie.
- **Neue Meisterschaft** in vier Schritten:
  1. **Grundlagen**: Name und Renn-Setup (aus einer Vorlage oder dem aktuellen Schnellrennen). Alle Rennen fahren mit diesem Setup.
  2. **Strecken**: Strecken links per **Drag & Drop** in den Rennkalender ziehen (oder doppelklicken), Reihenfolge per Ziehen ändern, zurück nach links ziehen oder »Entfernen« löscht. Pro Rennen: Datum (im Spiel), Startzeit, Wetter und Renndauer in **Runden**, **Minuten** oder **wie im Setup**. »Dauer für alle Rennen übernehmen« setzt Dauer und Art für den ganzen Kalender.
     **Kalender einer echten Rennserie**: GT World Challenge Europe (auch nur Sprint oder nur Endurance), DTM, ADAC GT Masters, IMSA GTD und Intercontinental GT Challenge, jeweils 2022 bis 2026 (gleiche Kalender zusammengefasst) mit den echten Terminen. Dazu der Kalender **Langstrecken-Klassiker** (Daytona 24h, Bathurst 12h, Sebring 12h, Imola 6h, Nürburgring 24h, Le Mans 24h, Spa 24h, Watkins Glen 6h, Interlagos 6h, Monza 6h, Kyalami 9h, Petit Le Mans 10h): Diese Rennen laufen automatisch nach Zeit, die Dauer ist pro Rennen änderbar (bis 1440 Minuten). Strecken, die AMS2 nicht hat, werden durch eine ähnliche ersetzt und im Kalender markiert (z. B. »Ersatz für Norisring«). »Durch gewählte Strecke ersetzen« tauscht die Strecke eines Rennens.
  3. **Punkte**: eigene Punkte, Extrapunkte und Prozent-Regel nur für diese Meisterschaft (vorbelegt mit den Standardwerten).
  4. **Prüfen** und speichern.
- **Nächstes Rennen starten**: stellt Strecke, Datum, Uhrzeit, Wetter und alle Regeln des nächsten Rennens ein und startet den Server neu. Den Knopf gibt es auch in der Übersicht, solange eine Meisterschaft läuft. Nach dem Rennen hakt das Tool es automatisch ab.
- **Rechtsklick auf ein Rennen**: jetzt starten, wiederholen, als gefahren / nicht gefahren markieren.
- **Tabelle**: Punkte, Siege, Podien und die Punkte pro Rennen (R1, R2 …; * = mit Extrapunkten, NC = nicht gewertet). Die ersten drei in Gold, Silber und Bronze. KI-Fahrer zählen nicht.
- Jede Meisterschaft liegt als eigene Datei in `ServerManager\championships`.
- »Rennen starten« im Schnellrennen beendet den Meisterschaftsmodus wieder (der Server fährt dann das Schnellrennen-Setup).

## Einstellungen

Links eine Liste mit sieben Seiten, oben die Knöpfe **Speichern**, **Speichern + Neustart** und **Server-Ordner öffnen**.

| Seite | Inhalt |
|---|---|
| **Server** | Name, Passwort, max. Spieler, VAC-Prüfung, Sichtbarkeit im Browser, Log-Level |
| **Netzwerk** | Bind-IP, Ports, Internet-Leitung (Standard: unbegrenzt) |
| **Willkommen & Chat** | Willkommensnachricht (MOTD) und Chat-Befehle |
| **Spieler & VIP** | reservierte Plätze, VIP-Liste, Klassen-Limit |
| **Wertung & Punkte** | Punkte für Platz 1 bis 20, Extrapunkte, Prozent-Regel, neue Saison |
| **Leistung & Energie** | Tick-Rate, Priorität, Energiesparen, Höchstleistung, Laptop-Deckel |
| **Experten** | Flags-Zahl, weitere Session-Attribute, Listen laden, Diagnose speichern, Rotation |

## Wetter & Uhrzeit

- Training, Qualifying und Rennen haben jeweils eine eigene **Startzeit** und ein eigenes **Wetter**.
- Die Startzeit geht nur in vollen Stunden (z. B. 15:00 Uhr). Halbe Stunden kennt der Server nicht.
- **Echtes Wetter**: Das Spiel nimmt das echte Wetter an der Strecke.
- **Wetter-Wechsel**: 1 bis 4 Abschnitte. Das Wetter wechselt im Lauf der Session von Feld 1 zu Feld 2 usw.
- Bei Training und Quali gibt es das Häkchen **wie Rennen**. Dann gelten dort Startzeit und Wetter des Rennens.
- Das **Datum** gilt für alle Sessions.
- **Max. Spieler** kann nicht größer als das Grid sein. Das Tool begrenzt den Wert automatisch.

## Monitor

- Rundinstrumente für **CPU** und **RAM** des PCs (darunter, was der Server selbst braucht), **Upload**, **Download**, **Pakete pro Sekunde** und **Ping** der Spieler.
- Upload und Download zählen den gesamten Verkehr des PCs, also auch andere Programme.
- Upload und Download stehen standardmäßig auf **unbegrenzt**: Die Anzeigen zeigen dann Mbit/s, die Balken richten sich nach dem bisher höchsten Wert, ohne Warnfarben. Wer seine Leitung einträgt (Häkchen aus), bekommt Prozent und Warnfarben.
- Die Verlaufskurve zeigt die letzten 5 Minuten. Darunter stehen die Höchstwerte seit dem Start des Tools, mit Knopf zum Zurücksetzen.

## Leistung & Energie (Einstellungen → Leistung & Energie)

- **Tick-Rate**: Pause im Rennen und ohne Rennen in Millisekunden (Standard 10 / 50). Kleiner = genauer, aber mehr CPU-Last. Gilt nach »Speichern + Neustart«.
- **Priorität Server**: Normal, Höher als normal (Standard) oder Hoch. **Priorität Tool**: Normal oder Niedriger als normal (Standard). Wird sofort angewendet. Echtzeit gibt es bewusst nicht.
- **Energiesparen verhindern**: Solange der Server läuft, geht der PC nicht in den Energiesparmodus. Der Bildschirm darf trotzdem ausgehen.
- **Höchstleistung**: Solange der Server läuft, schaltet das Tool auf den Energiesparplan »Höchstleistung« und danach zurück. Stürzt das Tool ab, stellt es den alten Plan beim nächsten Start wieder her. Gibt es den Plan auf dem PC nicht, passiert nichts.
- **Laptop-Deckel**: Das Tool zeigt, was beim Zuklappen passiert. Ist das »Energie sparen«, wäre der Server weg. Mit **Deckel zu: Nichts unternehmen** wird das für den Netzbetrieb geändert, mit **Zurücksetzen** kommt der alte Wert zurück. Das Tool ändert das nie von selbst.
- **Diagnose speichern** (Einstellungen → Experten oder Monitor): schreibt die echten Antworten der Server-API in eine Textdatei in `ServerManager`. Hilft bei der Fehlersuche.

## Admin-Chat

- Seite **Chat** in der Navigation links.
- Zeigt live, was die Spieler schreiben, dazu Beitritte, Abgänge und Session-Wechsel.
- Unten „An: Alle“ oder einen Spieler wählen, Text eingeben, Enter drücken.
- Der Verlauf wird pro Tag in `ServerManager\chat` gespeichert, solange das Tool läuft.

## Fahrerliste

Rechtsklick auf einen Fahrer:

- **Privat anschreiben**
- **Kicken**
- **Bannen für 1 Stunde / 24 Stunden**: gilt bis zum nächsten Server-Neustart
- **Dauerhaft bannen**: Die Steam-ID kommt zusätzlich auf die Sperrliste in der `server.cfg` und bleibt auch nach Neustarts gesperrt
- **Als VIP eintragen / austragen**

Vor jedem Kick oder Bann fragt das Tool optional nach einem Grund. Dann geht eine Nachricht in den Chat, z. B. „[Admin] XY wird in 5 Sekunden gekickt. Grund: …“. 5 Sekunden später folgt der Kick.

Unten auf der Seite steht die Sperrliste. Mit „Entbannen“ wird ein Spieler wieder aus der `server.cfg` entfernt. Das gilt ab dem nächsten Neustart.

## Server-Addon „tgc_manager“

Einige Funktionen laufen direkt im Server. Das Tool legt dafür beim Speichern das Addon `lua\tgc_manager` an und schaltet es ein. **Änderungen an diesen Einstellungen gelten erst nach einem Neustart des Servers.**

- **Willkommensnachricht (MOTD)**: mehrere Zeilen mit Platzhaltern `{name}`, `{server}`, `{track}`. Optional danach Strecke, Klasse und Renndauer. Ersetzt das Standard-Addon `sms_motd`.
- **Chat-Befehle**: Die Antwort sieht nur der Fragende, den Befehl selbst sehen alle.

  | Befehl | Antwort |
  |---|---|
  | `!rank` | eigener Platz in der Rangliste, Punkte, Siege, Podien, Rennen |
  | `!top` | Top 5 des Servers |
  | `!best` | eigene Bestzeit auf dieser Strecke in der eigenen Klasse |
  | `!record` | Streckenrekord für Strecke und Klasse |
  | `!info` | Strecke, Klassen, Renndauer, Fahrhilfen |
  | `!next` | nächstes Event (z. B. bei Rotation) |
  | `!help` | Liste der Befehle |

- **Ergebnisse**: Nach jeder Session (Training, Quali, Rennen) speichert das Addon das Ergebnis. Das Tool archiviert es dauerhaft in `ServerManager\results`, auch wenn es beim Rennen nicht offen war (das Addon hält die letzten 200 Sessions vor).
- **Rangliste**: Das Addon zählt Punkte, Siege und Podien selbst mit, damit `!rank` auch ohne Tool funktioniert. Sie beginnt bei null, sobald v0.12 läuft.
- **Reservierte Plätze**: Normale Spieler können nur „Max. Spieler – reserviert“ Plätze belegen. Wer darüber liegt, bekommt eine Nachricht und wird nach 5 Sekunden getrennt. Spieler auf der VIP-Liste kommen immer rein, solange noch ein Platz frei ist. Ist der Server komplett voll, kann auch ein VIP nicht beitreten.
- **Klassen-Limit**: Bei Multiclass hat jede Klasse ein Feld „max.“ (0 = unbegrenzt). Wer zu viel ist, bekommt in der Lobby alle 20 Sekunden eine Warnung. Optional wird er nach einer einstellbaren Zeit gekickt.

## Wertung & Punkte

- **Punkte pro Platz**: Für Platz 1 bis 20 steht neben jedem Platz ein Kästchen mit den Punkten. Standard: 25, 22, 20, 18, 16, 15, 14, 13, 12, 11, 10, 9, 8, 7, 6, 5, 4, 3, 2, 1. Ab Platz 21 gibt es keine Punkte. Hat ein Platz mehr Punkte als der davor, erscheint ein roter Hinweis.
- **Extrapunkte**: für die **Pole-Position im Qualifying** und die **schnellste Runde im Rennen**, jeweils mit Häkchen zum Einschalten (Standard: je 1 Punkt). Die Pole zählt nur, wenn danach auf derselben Strecke ein Rennen gefahren wird.
- **Platzierung geht vor**: Extrapunkte überholen nie den Vordermann. Würde jemand dadurch vorbeiziehen, bekommt er nur so viele Extrapunkte, dass er knapp dahinter bleibt. Der Sieger hat also immer die meisten Punkte.
- **Wer bekommt Punkte**: nur wer mindestens **75 %** der Runden des Siegers seiner Klasse gefahren ist (einstellbar). Bei Multiclass wird jede Klasse für sich gewertet.
- **KI-Fahrer** belegen Plätze, ihre Punkte verfallen. In den Tabellen ist die KI standardmäßig ausgeblendet.
- **Training/Quali**: Gewertet wird, wer mindestens eine gültige Runde gefahren ist. Die Reihenfolge ergibt sich aus der Bestzeit.
- **Neue Saison starten**: setzt die Rangliste (Punkte, Siege, Podien, `!rank`) auf null. Die alten Ergebnisse bleiben im Archiv. Im Server gilt das nach dem nächsten Neustart. Die Statistik zeigt standardmäßig die aktuelle Saison.
- Ergebnisse behalten die Punkte, die zum Zeitpunkt des Rennens galten. Spätere Änderungen an der Punkte-Tabelle ändern alte Rennen nicht.
- Wer nicht gewertet ist, steht grau mit „NC“ und dem gefahrenen Anteil in der Tabelle.
- Fahrer werden über die Steam-ID erkannt. Namensänderungen schaden der Statistik also nicht.

## Rennleitung (Strafen)

- **Strafe vergeben**: Unter *Ergebnisse* ein Rennen öffnen, mit Rechtsklick auf einen Fahrer → *Strafe vergeben …*. Auch über den Knopf **Strafen** oben rechts.
- **Punktabzug**: Der Platz bleibt, die Punkte werden abgezogen (Standard 5).
- **Zeitstrafe**: Die Sekunden kommen auf die Gesamtzeit. Das Ergebnis wird neu sortiert und die Punkte werden neu verteilt.
- **Disqualifikation**: keine Punkte, alle dahinter rücken einen Platz auf.
- Bei Training und Quali gibt es nur die Disqualifikation.
- Eine **Begründung** ist Pflicht. Vorlagen wie „Unfaires Verhalten“ stehen in der Liste darunter. Läuft der Server, kann die Strafe auf Wunsch im Chat bekanntgegeben werden.
- Bestrafte Fahrer stehen **rot mit ⚑** im Ergebnis. Fährst du mit der Maus darüber, siehst du Strafe und Grund. Die Meisterschaftstabelle zeigt z. B. „18 (−5)“.
- **Strafenliste**: unter *Ergebnisse* über *Strafen* (alle) und in der Meisterschaft über *Strafen* (nur diese Meisterschaft). Dort kannst du eine Strafe auch wieder **aufheben**.
- Das Originalergebnis wird nie verändert, Strafen liegen getrennt in `penalties.json`.
- Die Strafen wirken sofort auf Meisterschaftstabelle, Statistik und Saison. Für `!rank` und `!top` im Server gelten sie nach dem nächsten Speichern bzw. Neustart.
- Bei einer Zeitstrafe oder Disqualifikation wird das Rennen mit der aktuellen Punkte-Tabelle neu gewertet.
- Strafen gibt es nur für echte Fahrer, nicht für die KI.

## Damit Freunde beitreten können

- Die **Bind-IP** muss leer sein. Mit `127.0.0.1` kann nur dein eigener PC beitreten.
- Im Router diese Ports an deinen PC weiterleiten, jeweils UDP und TCP: **8766, 27015, 27016**. In der Fritzbox dabei das Häkchen **„IPv4 aktiviert“** setzen. IPv6 wird nicht gebraucht, der Server läuft nur über IPv4.
- Gib dem PC im Router immer dieselbe IPv4-Adresse, sonst zeigt die Freigabe nach einem Neustart ins Leere.
- Bei **DS-Lite** (keine eigene öffentliche IPv4) kommen Freunde von außen nicht durch. Der Einrichtungs-Assistent prüft das.
- Die Windows-Firewall muss `DedicatedServerCmd.exe` erlauben. Sie fragt beim ersten Start nach.

## Dateien des Tools

Alles liegt im Unterordner `ServerManager` des Server-Ordners:

- `settings.json`: deine Einstellungen im Tool
- `presets\`: gespeicherte Presets
- `backups\`: Backups von `server.cfg` und der Rotation (die letzten 30)
- `logs\`: Server-Logs (die letzten 30 Starts)
- `listen_cache.json`: die vom Server geladenen Listen (nur nach „Listen laden“)
- `results\`: Archiv aller Ergebnisse (wird nie automatisch gelöscht)
- `chat\`: Chatverlauf pro Tag
- `diagnose_….txt`: Dateien von »Diagnose speichern«
- `championships\`: die Meisterschaften
- `penalties.json`: die vergebenen Strafen

## Hinweise

- Die HTTP-API des Servers bleibt nur lokal erreichbar (`127.0.0.1`). Das Tool braucht sie für Status, Spielerliste und die Listen.
- Stopp beendet den Serverprozess direkt.
- Umlaute in MOTD oder Admin-Chat können im Spiel-Chat je nach Spielversion falsch angezeigt werden.
- Die Log-Ausgabe kann leicht verzögert in Blöcken kommen.
- Wurde der Server außerhalb des Tools gestartet, erkennt das Tool ihn und kann ihn stoppen, zeigt aber kein Log.

## Für Entwickler: EXE bauen

`EXE bauen.bat` ausführen. Das Skript installiert bei Bedarf das Modul `ps2exe` und baut `AMS2-Server-Manager_v<Version>.exe`. Liegt eine `icon.ico` daneben, wird sie als Icon verwendet.

## Changelog

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
