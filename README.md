<p align="center"><img src="images/logo.png" width="160" alt="AMS2 Server Control"></p>

<h1 align="center">AMS2 Server Control</h1>

<p align="center"><b>Deutsch</b> · <a href="README_EN.md">English</a></p>

<p align="center"><a href="https://github.com/MaDDoX75/AMS2-Server-Control/releases/latest"><b>⬇ Download (neueste Version)</b></a> · <a href="CHANGELOG.md">Changelog</a></p>

GUI für den **Automobilista 2 Dedicated Server**: Server einstellen, Strecke und Autos wählen, Regeln und Fahrhilfen setzen, Vorlagen und Meisterschaften verwalten, Start, Stopp und Neustart per Knopfdruck. Dazu kommen Admin-Chat, Fahrerliste mit Kick und Bann, Ergebnisse nach jeder Session, eine Statistik mit Rangliste, Chat-Befehle wie `!rank` und eine Willkommensnachricht.

## Installation

1. `AMS2-Server-Control.exe` irgendwo hinlegen, am einfachsten in den Ordner des Dedicated Servers (neben `DedicatedServerCmd.exe`).
2. Die EXE starten.
3. Beim ersten Start öffnet sich der **Einrichtungs-Assistent** (siehe unten). Ist schon ein eingerichteter Server da, startet das Tool direkt.

## Sprache / Language

Das Tool gibt es auf **Deutsch** und **Englisch**. Beim ersten Start ist die Windows-Sprache vorausgewählt. Im Einrichtungs-Assistenten kannst du oben rechts umschalten, später unter *Einstellungen → Allgemein → Sprache / Language* (danach startet das Tool neu). Die Chat-Nachrichten im Spiel (Willkommen, `!rank`, `!info`, Rennleitung …) folgen der gewählten Sprache. Die Auswahl steht in `AMS2-Server-Control.lang.txt` neben dem Tool.

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

Der gewählte Ordner wird in `AMS2-Server-Control.path.txt` neben dem Tool gespeichert. SteamCMD liegt im Ordner `steamcmd` **neben** dem Server-Ordner. In den Server-Ordner selbst darf es nicht, das lehnt Steam ab. Beispiel bei einer Neuinstallation: Tool in `D:\AMS2\`, Server in `D:\AMS2\Server\`, SteamCMD in `D:\AMS2\steamcmd\`. SteamCMD bleibt für spätere Updates liegen.

## Start-Assistent (erste Schritte)

Erscheint beim allerersten Start von AMS2 Server Control und jederzeit über *Einstellungen → Allgemein → Start-Assistent*. Er ist für alle gedacht, die noch nie einen Server betrieben haben. Auf jeder Seite ist ein sinnvoller Wert vorausgewählt, man kann also einfach immer „Weiter“ klicken.

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

1. Links unten **Einstellungen** öffnen und **Speichern** klicken. Das Tool schreibt eine saubere `server.cfg`. Die alte Datei wird vorher in `ServerControl\backups` gesichert.
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
- **★ Rennserie wählen** (oben rechts): Rennserie aussuchen, das Tool stellt die Klassen ein (bei IMSA, WEC und Le Mans Series als **Multiclass**) und zeigt nur noch passende Strecken.
- Darunter Sprungknöpfe zu den Abschnitten.
- **Nur zur Klasse passende Strecken** (Häkchen bei der Strecke, standardmäßig an): keine Kart-, Oval-, RX- oder Truck-Strecken für Rundstrecken-Autos, Karts nur auf Kartbahnen, Ovale nur für Stock-USA/Formula-USA. Bei historischen Autos (z. B. Gruppe A) erscheinen die historischen Varianten statt der modernen, bei modernen Autos keine Layouts, die mehr als 20 Jahre älter sind.
- **Strecken und Autos als Karten**: Die gewählte Strecke bzw. das gewählte Auto hat einen orangen Rahmen und „✓ gewählt“. DLC-Inhalte sind violett markiert. *Autos in der Auswahl* zeigt pro Klasse alle Autos mit Hersteller, Baujahr und DLC.
- Die Abschnitte passen sich der Fensterbreite an (kein seitliches Scrollen). Unter **Regeln & Fahrhilfen** gibt es den Kasten **Boxengasse** mit dem Tempolimit (Strecken-Standard, 50/60/80/100 km/h oder eigener Wert 40–200 km/h).
- **Abschnitte** (untereinander, mit Mausrad scrollen): 1 Strecke, 2 Fahrzeuge, 3 Ablauf (Training, Quali, Rennen, Grid, KI, Datum), 4 Wetter & Uhrzeit, 5 Regeln & Fahrhilfen, 6 Renn-Optionen, 7 Wertung.
- **Wertung aktivieren**: an = das Rennen zählt für die Rangliste; aus = Spaßrennen, das Ergebnis wird gespeichert, aber ohne Punkte. Vorlagen merken sich das Häkchen.
- **Unten**:
  - **Rennen starten**: speichert und startet den Server neu (oder startet ihn, wenn er aus ist). Sind Spieler online, fragt das Tool vorher und bietet als Alternative »Live übernehmen« an.
  - **Nur speichern**: schreibt die `server.cfg`, ohne neu zu starten.
  - **Live übernehmen**: schickt das Setup an den laufenden Server. Es gilt ab der nächsten Session, ganz ohne Neustart.

## Meisterschaften

- **Übersicht**: Jede Meisterschaft ist eine Karte mit Klassen, Fortschritt, Führendem und dem nächsten Rennen. Klick auf eine Karte öffnet sie.
- **Neue Meisterschaft** in vier Schritten:
  1. **Grundlagen**: Name, Renn-Setup und **Fahrzeuge**. Das aktuelle Schnellrennen ist sofort als Setup eingestellt, eine andere Vorlage gilt, sobald sie gewählt ist (kein »Übernehmen« mehr). Im Kasten **Fahrzeuge** wählst du wie im Schnellrennen Freie Wahl, Eine Klasse, Multiclass (mit max. Autos pro Klasse) oder Festes Auto. **★ Rennserie** füllt die Fahrzeuge automatisch aus, filtert in Schritt 2 die Strecken (»Passend zur Klasse«) und zeigt dort nur die Kalender dieser Serie. Regeln, Fahrhilfen, Ablauf, Startfeld und KI kommen aus dem Setup.
  2. **Strecken**: Strecken links per **Drag & Drop** in den Rennkalender ziehen (oder doppelklicken), Reihenfolge per Ziehen ändern, zurück nach links ziehen oder »Entfernen« löscht. Pro Rennen: Datum (im Spiel), Startzeit, Wetter und Renndauer in **Runden**, **Minuten** oder **wie im Setup**. »Dauer für alle Rennen übernehmen« setzt Dauer und Art für den ganzen Kalender.
     **Kalender einer echten Rennserie**: GT World Challenge Europe (auch nur Sprint oder nur Endurance), DTM, ADAC GT Masters, IMSA GTD und Intercontinental GT Challenge, jeweils 2022 bis 2026 (gleiche Kalender zusammengefasst) mit den echten Terminen. Neu: IMSA WeatherTech 2026, IMSA DPi-Ära 2019, WEC 2026, Le Mans Series 2005, FIA GT 2005, Porsche Supercup 2026, Lamborghini Super Trofeo Europe 2026 und DTM 1991/1992 (Gruppe A). Langstreckenrennen laufen dabei automatisch nach Zeit. Dazu der Kalender **Langstrecken-Klassiker** (Daytona 24h, Bathurst 12h, Sebring 12h, Imola 6h, Nürburgring 24h, Le Mans 24h, Spa 24h, Watkins Glen 6h, Interlagos 6h, Monza 6h, Kyalami 9h, Petit Le Mans 10h): Diese Rennen laufen automatisch nach Zeit, die Dauer ist pro Rennen änderbar (bis 1440 Minuten). Strecken, die AMS2 nicht hat, werden durch eine ähnliche ersetzt und im Kalender markiert (z. B. »Ersatz für Norisring«). »Durch gewählte Strecke ersetzen« tauscht die Strecke eines Rennens.
  3. **Punkte**: eigene Punkte, Extrapunkte und Prozent-Regel nur für diese Meisterschaft (vorbelegt mit den Standardwerten).
  4. **Prüfen** und speichern.
- **Nächstes Rennen starten**: stellt Strecke, Datum, Uhrzeit, Wetter und alle Regeln des nächsten Rennens ein und startet den Server neu. Den Knopf gibt es auch in der Übersicht, solange eine Meisterschaft läuft. Nach dem Rennen hakt das Tool es automatisch ab.
- **Rechtsklick auf ein Rennen**: jetzt starten, wiederholen, als gefahren / nicht gefahren markieren.
- **Tabelle**: Punkte, Siege, Podien und die Punkte pro Rennen (R1, R2 …; * = mit Extrapunkten, NC = nicht gewertet). Die ersten drei in Gold, Silber und Bronze. KI-Fahrer zählen nicht.
- **Exportieren …** (in der Meisterschaft) speichert sie als `.ams2champ`-Datei: Setup, Rennserie, Kalender, Punkte-Regeln, Fortschritt sowie alle bisherigen Ergebnisse und Strafen.
- **Importieren …** (in der Liste) fragt, ob mit Fortschritt und Ergebnissen oder als frische Meisterschaft importiert wird. Eine vorhandene Meisterschaft wird nie überschrieben: Gibt es sie schon, schlägt das Tool einen anderen Namen vor (z. B. »… (2)«). Ergebnisse, die schon im Archiv liegen, werden nicht doppelt gespeichert.
- Jede Meisterschaft liegt als eigene Datei in `ServerControl\championships`.
- »Rennen starten« im Schnellrennen beendet den Meisterschaftsmodus wieder (der Server fährt dann das Schnellrennen-Setup).

## Fahrer, Teams & Ballast

- **Meisterschaft → Schritt 3 Fahrer**: Startliste mit Steam-ID, Team und Balance of Performance. Fahrer lassen sich aus den Ergebnissen oder vom laufenden Server übernehmen.
- **Teamwertung** und **feste Namen** sind Optionen in diesem Schritt, ebenso die **Allow-Liste** (nur bei Meisterschaftsrennen).
- **Erfolgsballast** (Schritt 1): *Nach dem letzten Rennen* – nur die Platzierung im vorherigen Rennen zählt; *Aufbauend mit Abbau* – Gewicht addiert sich und baut sich ohne Podium wieder ab, bis zum Höchstgewicht.
- **Einstellungen → Spieler & VIP → Balance of Performance**: Ballast, Leistung (90–110 %) und Luftwiderstand (90–110 %) pro Fahrer für alle Rennen. Gilt nach dem nächsten Server-Neustart.

## Hilfe & Updates

- Links in der Navigation **? Hilfe**: öffnet das Hilfe-Fenster mit den Reitern **Anleitung** (Schritt für Schritt), **Funktionen** (diese README) und **Changelog** (alle Änderungen). Die Texte stecken in der EXE und passen immer zur Version.
- **Auf Updates prüfen** (im Hilfe-Fenster) schaut auf GitHub (`MaDDoX75/AMS2-Server-Control`) nach einer neueren Version. Auf Wunsch lädt das Tool die neue `AMS2-Server-Control.exe`, beendet sich, tauscht die Datei aus und startet neu. Der Server läuft dabei weiter.
- Beim Start prüft das Tool das automatisch, abschaltbar unter *Einstellungen → Server → Anzeige → Beim Start nach Updates suchen*.

## Einstellungen

Links eine Liste mit sieben Seiten, oben die Knöpfe **Speichern**, **Speichern + Neustart**, **Server-Ordner öffnen**, **Exportieren …** und **Importieren …**. Der Export speichert alle Einstellungen in einer `.ams2settings`-Datei (das Passwort nur auf Wunsch), der Import übernimmt sie nach Rückfrage – der Server-Ordner bleibt dabei unverändert. Passen die Kästen nicht nebeneinander ins Fenster, stehen sie untereinander.

| Seite | Inhalt |
|---|---|
| **Server** | Name, Passwort, max. Spieler, VAC-Prüfung, Sichtbarkeit im Browser, Log-Level, Sprache; **Anzeige**: Strecke/Meisterschaft am Servernamen, Update-Prüfung beim Start |
| **Netzwerk** | Bind-IP, Ports, Internet-Leitung (Standard: unbegrenzt) |
| **Willkommen & Chat** | Willkommensnachricht (MOTD), Chat-Befehle, **Chat-Sprache im Spiel** (wie das Tool, Deutsch, English) und **Name im Chat** (z. B. »Admin: Hallo«) |
| **Spieler & VIP** | reservierte Plätze, VIP-Liste, Klassen-Limit |
| **Wertung & Punkte** | Punkte für Platz 1 bis 20, Extrapunkte, Prozent-Regel, neue Saison |
| **Leistung & Energie** | Tick-Rate, Priorität, Energiesparen, Höchstleistung, Laptop-Deckel |
| **Experten** | Flags-Zahl, weitere Session-Attribute, Listen laden, Diagnose speichern, Server aktualisieren |

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
- **Diagnose speichern** (Einstellungen → Experten oder Monitor): schreibt die echten Antworten der Server-API in eine Textdatei in `ServerControl`. Hilft bei der Fehlersuche.

## Admin-Chat

- Seite **Chat** in der Navigation links.
- Zeigt live, was die Spieler schreiben, dazu Beitritte, Abgänge und Session-Wechsel.
- Unten „An: Alle“ oder einen Spieler wählen, Text eingeben, Enter drücken.
- Der Verlauf wird pro Tag in `ServerControl\chat` gespeichert, solange das Tool läuft.

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
  | `!next` | nächstes Event (z. B. nächstes Meisterschaftsrennen) |
  | `!help` | Liste der Befehle |

- **Ergebnisse**: Nach jeder Session (Training, Quali, Rennen) speichert das Addon das Ergebnis. Das Tool archiviert es dauerhaft in `ServerControl\results`, auch wenn es beim Rennen nicht offen war (das Addon hält die letzten 200 Sessions vor).
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

Alles liegt im Unterordner `ServerControl` des Server-Ordners:

- `settings.json`: deine Einstellungen im Tool
- `presets\`: gespeicherte Presets
- `backups\`: Backups von `server.cfg` (die letzten 30)
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

`EXE bauen.bat` ausführen. Das Skript installiert bei Bedarf das Modul `ps2exe` und baut `AMS2-Server-Control.exe`. Liegt eine `icon.ico` daneben, wird sie als Icon verwendet.

## Über das Programm

**AMS2 Server Control**  
Entwickelt von MaDDoX für THC Sim Racing.  
Version 0.197 · Oktober 2026  
Webseite: https://github.com/MaDDoX75/AMS2-Server-Control

AMS2 Server Control © 2026 MaDDoX · The Game Central. Alle Rechte vorbehalten.  
The Game Central [TGC] sowie die TGC-Logos sind Eigentum von MaDDoX.  
Das THC-Sim-Racing-Logo [THC] ist Eigentum von THC Sim Racing.

## Rechtliches

**Nutzung:** Das Programm darf kostenlos privat genutzt und unverändert weitergegeben werden. Verkauf oder Veröffentlichung veränderter Versionen nur mit Zustimmung des Autors.

**Keine Gewähr:** Die Nutzung erfolgt auf eigene Gefahr. Das Programm schreibt die `server.cfg` und weitere Dateien des Dedicated Servers (vorher wird jeweils ein Backup angelegt). Für Datenverlust, Serverausfälle oder Fehler in Wertungen und Ergebnissen wird keine Haftung übernommen.

**Kein offizielles Produkt:** Dieses Programm ist ein Fan-Projekt und steht in keiner Verbindung zu Reiza Studios. „Automobilista 2“ ist eine Marke von Reiza Studios. Das Programm steuert den offiziellen AMS2 Dedicated Server über dessen Konfigurationsdateien, HTTP-API und Lua-Schnittstelle und verändert nichts am Spiel. SteamCMD und Steam sind Dienste von Valve.
