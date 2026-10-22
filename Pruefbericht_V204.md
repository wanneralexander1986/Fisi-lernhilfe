# FiSi Lernhilfe V204 – Bruchtal 2.0: Smaragdhain und Herbstlicht

Ergebnis: Bruchtal ist nach den beiden freigegebenen Designbildern neu gestaltet. Smaragdhain ist die grüne Standardvariante, Herbstlicht die herbstliche Alternative. Beide Varianten haben eine eigene Landschaft, eigene Embleme und Bildsymbole, eine eigene Farbwelt und gestaltete Unteransichten. Der bisherige Skin wurde nicht umgefärbt, sondern komplett ersetzt. Hunter, Mondhain und Nachtkrone bleiben unverändert.

## Umgesetzt nach Referenz

- **Landschaftsbühne im Kopfbereich:** „Willkommen in Bruchtal“ mit Variantennamen und dem Leitspruch „Wissen · Wachsen · Erfolgreich sein“. Die Landschaften stammen aus den Referenzbildern; die Bedienelemente wurden aus den Bildern entfernt.
- **„Design wechseln“-Schalter** mit zwei Pfeilen und Punktanzeige, oben rechts.
- **Seitenleiste als Elbenbogen** mit Baum-Emblem und „FiSi Lernhilfe – Bruchtal –“. Der aktive Eintrag erscheint als grüne bzw. rostrote Plakette.
- **Startkacheln als Pergamentkarten** mit Rahmenornamenten und Bildsymbolen: Buch, Feder, Kompass und Schwerter aus der Referenz, dazu passend gezeichnet Brief mit Siegel und Schriftrolle.
- **„Heute dran“** auf einer Landschaftsfläche, der Leitspruch als Banner, die rechte Leiste mit Pergamentkästen.
- **Alle 25 Ansichten** (Lernen, Üben, Prüfung, Battle, Tickets, Fortschritt, Einstellungen …) sind Pergamentfenster mit Landschaftsbogen und Bereichssymbol. Dazu gehören Registerleisten, Primäraktionen, Formulare, Quiz- und Statusfarben, Hinweisfenster sowie die mobile Leiste.
- **Einstellungen › Konto & Daten:** Bereich „Bruchtal-Design“ mit Bildkacheln „Bruchtal Herbstlicht“ und „Bruchtal Smaragdhain“ sowie einem Schalter „Hintergrundanimation“. Zusätzlich gibt es eine Variantenwahl unter der Designauswahl im Kopf.
- **Hintergrundanimation:** fallende Blätter, in Smaragdhain zusätzlich Lichtfunken. Sie ist abschaltbar und bei „Bewegung reduzieren“ automatisch aus.
- Variante und Animation werden gespeichert. Der hohe Kontrast hat für beide Varianten eigene Werte.

## Erhalt

Die neue gekapselte Präsentationsebene V204 steht vor dem V69-Register, mit Registereintrag. Die vier Versionsstellen sind aktualisiert. Außerhalb der neuen Ebene ist der Quelltext nachweislich zeichengleich mit V203: Abgleich mit ausgeklammerter Ebene, Registerzeile und Versionswerten. Lerninhalte, Datenformate, Ereignishandler, Konten, Cloud und Battle sind unverändert.

## Prüfungen (alle an der ausgelieferten Datei)

- `fisi_pruef.js --voll`: Syntax OK, Startprüfung 105/105, 25 Ansichten geöffnet, keine Beanstandung. Golden-Master gegen stand_V203.json ohne Abweichung; stand_V204.json ist gesichert.
- **Ansichtenmatrix:** 300 Kombinationen (25 Ansichten × 2 Varianten × 6 Größen: 375, 1280, 1440, 1874, 1920, 2560 px), dazu 200 Kombinationen im hohen Kontrast. Ergebnis: keine Fehler, keine leeren Ansichten, kein Seitenüberlauf und keine Textstelle unter WCAG-Kontrast 4,5:1 (große Schrift 3:1).
- **Unteransichten:** 420 Zustände (35 Zustände × 2 Varianten × 3 Größen × normal/hoch). Geprüft wurden:
  - Lernfelddetail, Quizfrage, beantwortete Frage und Quizergebnis
  - Karteikarte vorn und hinten
  - Übungslösung, Zuordnen, Terminal mit Fehleingabe und Rechenlösung
  - Glossardetail, Vokabeltrainer, Lernpfaddetail und Dozent
  - Ticket mit Befund, Ursache und Auswertung
  - laufende Prüfung, Prüfungsvorbereitung und Endspurt
  - Battle-Lobby
  - Registrieren und Passwort vergessen
  - FAQ, Einführung, Statistik, Erfolge, Wiederholung, Generator, Merksätze, Tricks und Grafiken
  - Prüfungsübersicht, weitere Übersicht und Suche

  Ergebnis: ohne Befund.
- **Funktionstest:** 23 von 23 bestanden. Geprüft wurden Pfeile, Variantenkacheln, Einstellungsbereich, Animationsschalter, Speicherung nach dem Neuladen, Tastaturbedienung, Wechsel zu allen anderen Skins und zurück, Kontrastknopf, Quizlauf und Startprüfung. Dabei traten keine JavaScript-Fehler auf.
- **Gegenprobe der anderen Skins:** Hunter, Mondhain und Nachtkrone wurden pixelweise mit V203 verglichen. Abweichend ist nur die Versionsangabe.
- Während der Prüfung wurden behoben: Kontrast der aktiven Schaltflächen, Signalfarben älterer Ebenen (grüner Text, Serienkarte, KI-Beispiele, Zählerplaketten), Hinweis-Einblendungen für Combo und Tagesziel, die Ornamentecken mit Abstand zum Inhalt, die kompakte Variantenwahl auf dem Handy und der „Mehr“-Knopf auf breiten Bildschirmen.

## Prüfgrenzen

Getestet wurde mit Chromium offline über file://, externe Anfragen waren blockiert. Nicht geprüft wurden echte Anmeldung, Cloud-Synchronisation, ein Online-Battle zu zweit, andere Browser und echte Mobilgeräte. Nicht jede einzelne Frage, Karte und Filterkombination wurde durchgespielt. Die Kontrastprüfung ist automatisiert und keine vollständige WCAG-Zertifizierung.

Einschränkungen gegenüber dem Referenzbild:
- **Hintergründe und Bildsymbole:** Sie stammen aus dem Referenzbild (1672 × 941 px) und sind dadurch auf großen Bildschirmen etwas weich.
- **Kopfzeile und Fortschrittsanzeige:** Avatar, „Stufe 12“ und Glocke aus dem Bild gibt es in der App nicht; dort stehen weiterhin die vorhandenen Konto- und Werkzeugknöpfe. Ebenso wurde der Fortschrittsring nicht als neue Funktion nachgebaut. Der vorhandene Ring unter „Weitere Übersicht“ trägt das Baum-Emblem.
- **Prüfwerkzeug:** In der aus Drive geladenen fisi_pruef.js (Stand 20.09.) war „📚 Lernen“ noch als abgeschafft eingetragen. Das ist seit V158 wieder ein gültiger Bereich, daher wurde der Eintrag lokal entfernt.

## Datei

FiSi_Lernhilfe_V204.html, SHA-256: 205db795de40638d803b11c4804873a96715bbf2f3cb897b188f6e9b0b5768a3
