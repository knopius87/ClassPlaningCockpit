# Unterrichts-Cockpit NRW · V7

Offlinefähiges Planungswerkzeug für Deutsch, Spanisch **neu einsetzend** und Musik am Gymnasium NRW.

## Neu in V7

- Dark Mode als Standard
- kompakte Reihen-Schnellplanung: Stundenziel, Material, Haupterarbeitung/Methode und optional Produkt
- Reihencheck bereits ohne ausführliche Stundenplanung
- deutlich erweiterte kreative, szenische, produktive und problemlösende Methodenbibliothek
- Detailplanung nur noch optional pro Stunde
- responsive Bildschirm-Ausgabe ohne breite Abschlusstabellen
- eigene Druck-/PDF-Fassung
- Live-Unterricht mit Stunden- und Phasentimer, Gelb-/Rot-Warnung, Überspringen, +/- 2 Minuten und direktem Sprung zur Bearbeitung
- lokale Speicherung sowie JSON-Export/Import

## GitHub Pages

1. Repository auf GitHub erstellen.
2. **Den Inhalt dieses Ordners** in das Hauptverzeichnis des Repositorys hochladen.
3. `Settings` → `Pages`.
4. Unter `Build and deployment`: **Deploy from a branch**.
5. Branch `main`, Ordner `/(root)` wählen und speichern.
6. Nach kurzer Wartezeit die von GitHub angezeigte Pages-Adresse öffnen.

## Als App auf dem Smartphone

### iPhone / iPad
Die GitHub-Pages-Adresse in Safari öffnen → Teilen → **Zum Home-Bildschirm**.

### Android
Die GitHub-Pages-Adresse in Chrome öffnen → Browsermenü → **App installieren** bzw. **Zum Startbildschirm hinzufügen**.

Nach dem ersten erfolgreichen Online-Aufruf wird die App über den Service Worker auch offline zwischengespeichert.

## Daten

Planungsdaten werden standardmäßig nur im lokalen Browser (`localStorage`) gespeichert. Es werden keine Schüler*innendaten benötigt und die App enthält keine Tracker oder Analyse-Dienste. Für Backup oder Gerätewechsel gibt es JSON-Export und -Import.

## Hinweis zum Dark Mode

Der Dark Mode kann besonders auf OLED-/AMOLED-Displays den Energieverbrauch des Bildschirms reduzieren. Auf LCD-Displays ist der Effekt deutlich geringer.
