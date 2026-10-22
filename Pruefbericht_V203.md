# FiSi Lernhilfe V203 – Konsistenz aller vier Skins

Ergebnis: Hunter, Bruchtal, Mondhain und Nachtkrone in Haupt- und geöffneten Unteransichten auf unbeabsichtigte Designabweichungen geprüft und korrigiert. Jeder Skin behält seine eigene Farbwelt. Normale Schaltflächen, aktive Register, Primäraktionen, Formulare, Codeflächen und Statusanzeigen verwenden nun einheitliche Rollen je Skin. Die Ticketsystem-Kachel besitzt keine Sonderhervorhebung gegenüber den übrigen Schnellzugriffen.

## Konkrete Korrekturen

- Mondhain: lesbare Kartenrückseiten, Filter und Zähler; keine dunklen Fremdflächen in Übungen, Prüfung, Terminal oder Ticketprotokoll.
- Bruchtal: lesbarer Text auf Gold, goldene Filterränder und Rücklinks statt Blau/Violett.
- Hunter: lesbare Primäraktionen und aktive Register; offene Übungslösungen und Vokabelliste bei 375 px ohne Seitenüberlauf. Breite Tabellen bleiben lokal horizontal zugänglich.
- Nachtkrone: erkennbare aktive Unter- und Konto-Register; lesbare Übungsaktionen; beseitigter mobiler Seitenüberlauf durch unsichtbare alte Emoji-Texte.
- Alle Skins: gleiche Schnellzugriffskacheln; Grün/Rot/Warnfarben bleiben semantisch verschieden. Richtige und falsche Quizantworten haben jeweils eigene Flächen und Ränder. Terminalfehler, Tipps und Lösungen bleiben unterscheidbar.

## Grundlage und Erhalt

Ausgangsdatei ist V202, keine ältere Version. Neue gekapselte Präsentations-IIFE V203 vor dem V69-Register, mit Marker und Registereintrag; vier Versionsstellen aktualisiert. Exakte Ersetzungen auf Eindeutigkeit geprüft. Bestehender Quelltext nach Ausklammerung neuer Ebene, Registerzeile und vier Versionswerte vollständig identisch (Zeilenenden normalisiert). Lerninhalte, Datenformate, Ereignishandler, Accounts, Cloud- und Battlelogik wurden nicht verändert. Die zwei bereits vorhandenen Scriptblöcke bleiben erhalten, kein weiterer ergänzt.

## Ausgeführte Prüfungen

- Beide Scriptblöcke mit node --check erfolgreich geprüft.
- fisi_pruef.js --voll: Startprüfung 104/104, 25 Ansichten geöffnet, keine Beanstandung.
- Golden-Master gegen stand_V202.json: **keine Abweichung**. stand_V203.json gesichert.
- Zusätzlich vollständige Inhaltsdaten mit dem unveränderten V198-Inhaltsbestand verglichen: identisch, keine unbehandelten Laufzeitfehler.
- Allgemeine Browsermatrix: 1.200 Kombinationen aus 25 Ansichten × vier Skins × normal/hoher Kontrast × sechs Größen (375×900, 1280×900, 1440×900, 1874×900, 1920×1080, 2560×1440). Keine leeren Ansichten, keine unbehandelten JavaScript-Fehler, kein horizontaler Seitenüberlauf.
- Erweiterte Unteransichtenmatrix: 576 Kombinationen, alle Zustandsaktionen ausgeführt, keine leeren Ansichten oder JavaScript-Fehler. 18 Zustände pro Skin: Lernfelddetail, Quizfrage/falsche Antwort/Ergebnis, Karte vorne/hinten, offene Aufgaben-/Rechenlösungen, Glossar, FAQ, Einführung, Ticketbefund/Ursache/Maßnahme/Auswertung, laufende Prüfung, Offline-Battle-Lobby und Konto/Daten. Jeweils normal/hoch bei 375,1440,1920,2560 px. Zwei gefundene Hunter-Überläufe bei offener Übungslösung wurden danach korrigiert und separat erneut geprüft.
- Zusätzliche 192 Kombinationen: Lernpfaddetail, tatsächlicher Glossardetailklick, Vokabelliste und Konto-Register Anmeldung/Registrieren/Passwort vergessen, vier Skins × normal/hoch × vier Größen. Keine Zustandsfehler, leeren Ansichten oder JavaScript-Fehler. Zwei gefundene Hunter-Überläufe in der Vokabelliste wurden danach korrigiert und separat erneut geprüft.
- Finaler Wiederholungstest beider korrigierten Familien: 64 Kombinationen über alle vier Skins, normal/hoch und vier Größen; keine Zustandsfehler, keine JavaScript-Fehler, keine leeren Ansichten und kein horizontaler Seitenüberlauf.
- Acht gezielte Skin-/Kontrastprüfungen: richtige/falsche Antworten haben unterschiedliche Flächen und Ränder; alle sechs Schnellkacheln besitzen identische berechnete Flächen, Ränder, Schatten und Textfarben.
- Zusatzaudit Terminal und Zuordnung: vier Skins × zwei Zustände. Terminalaufgabe, absichtlich ungültige Eingabe, Tipp und Lösung; Zuordnungsaufgabe und eingeblendete Lösung. Keine Überläufe bei 1440 px.
- Screenshots der geänderten Haupt- und Unteransichten erstellt und gesichtet. Unabhängige Designstichprobe durch separaten Agenten: PASS nach Statusfarbenkorrektur; zusätzlich mobile Nachtkrone in acht Zuständen ohne Seitenüberlauf. Ein anderer Modellanbieter war nicht verfügbar.

## Prüfgrenzen

Die Prüfung erfasst sämtliche 25 vorhandenen Ansichten und die genannten geöffneten Unteransichtstypen. Sie spielt nicht jede einzelne Lernkarte, Quizfrage, Filterkombination, Fehlermeldung und jeden möglichen Dialogzustand durch. Semantische Statusfarben werden absichtlich nicht an neutrale Flächen angeglichen. Kontrastvorauswahl und Sichtprüfung sind keine vollständige WCAG-Zertifizierung.

Getestet wurde Chrome auf diesem Rechner, offline über file:// mit blockierten externen Anfragen. Keine produktiven Konten angelegt, keine Anmeldung, Cloud-Synchronisation oder echter Online-Battle mit mehreren Nutzern ausgeführt. Keine Veröffentlichung auf GitHub Pages, keine anderen Browser, echten Mobilgeräte oder Screenreader geprüft. Alex sollte für die produktive Onlinefreigabe Anmeldung/Kontowechsel, Cloud-Synchronisation und Battle mit zwei Nutzern sowie die bevorzugten Geräte prüfen.

Der historische stand_V175.json fehlt weiterhin; der ausgeführte Golden-Master-Vergleich verwendet den neuesten vorhandenen Ausgangsstand V202. Bestehende Strukturabweichungen (zwei Scriptblöcke, doppelte ID zu-klapp in zwei Übungsmodulen) wurden bei diesem Präsentationsauftrag nicht umgebaut.

## Datei

FiSi_Lernhilfe_V203.html ist die vollständige App. SHA-256: ecb725e4263a3a01992fa82dcbce805f2f24d4dc1f20cdfa182cbf2dd4a92fde

