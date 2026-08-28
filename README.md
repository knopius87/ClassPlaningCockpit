# Unterrichts-Cockpit NRW

Offlinefähiges Lernarchitektur- und Reihenplanungs-Cockpit für das Gymnasium NRW mit den Fächern **Deutsch**, **Spanisch neu einsetzend** und **Musik**.

Die App arbeitet nach einer Backward-Design-Logik: von KLP, Bewertungssituation und Ziel über Produkt/Evidenz und Lernarchitektur bis zum chronologischen Stundenraster.

## Enthaltene Dateien

- `index.html` – die komplette App
- `manifest.webmanifest` – Metadaten für die Installation auf dem Startbildschirm
- `service-worker.js` – Offline-Cache für die über GitHub Pages geöffnete App
- `icons/icon-192.png` – PWA-Icon
- `icons/icon-512.png` – großes/maskierbares PWA-Icon
- `icons/apple-touch-icon.png` – Icon für iPhone/iPad
- `.nojekyll` – verhindert unnötige Jekyll-Verarbeitung bei GitHub Pages

## Auf GitHub hochladen

1. Auf GitHub ein neues Repository anlegen, z. B. `unterrichts-cockpit-nrw`.
2. **Den Inhalt dieses Ordners** in die oberste Ebene des Repositorys hochladen. `index.html` muss also direkt im Repository liegen, nicht in einem zusätzlichen Unterordner.
3. Committen.
4. Im Repository **Settings → Pages** öffnen.
5. Unter **Build and deployment** als Quelle **Deploy from a branch** wählen.
6. Branch `main` und Ordner `/ (root)` auswählen und speichern.
7. Nach kurzer Zeit zeigt GitHub dort die öffentliche Pages-Adresse an.

GitHub Pages liefert die Seite über HTTPS aus. Dadurch können Manifest und Service Worker die App als installierbare Web-App bereitstellen.

## Auf dem Smartphone zum Startbildschirm hinzufügen

### iPhone / iPad

1. Die GitHub-Pages-Adresse in **Safari** öffnen.
2. Auf **Teilen** tippen.
3. **Zum Home-Bildschirm** wählen.
4. Namen bestätigen und **Hinzufügen**.

Die App startet anschließend über das eigene Icon nahezu wie eine normale App.

### Android

1. Die GitHub-Pages-Adresse in Chrome öffnen.
2. Das Browsermenü öffnen.
3. **App installieren** oder **Zum Startbildschirm hinzufügen** wählen.
4. Bestätigen.

## Offline-Nutzung

- Die ursprüngliche Grundfunktion der App benötigt weiterhin keinen Server.
- Nach dem ersten erfolgreichen Aufruf über GitHub Pages speichert der Service Worker die App-Oberfläche und Icons lokal im Browsercache.
- Danach kann die installierte App auch ohne Netzverbindung starten.
- Beim direkten Öffnen von `index.html` per Doppelklick funktioniert das Unterrichts-Cockpit ebenfalls; lediglich die PWA-Installation und der Service Worker stehen bei `file://` nicht zur Verfügung.

## Wo werden Planungsdaten gespeichert?

Planungsdaten werden weiterhin **lokal im Browser (`localStorage`)** gespeichert. Die PWA-Erweiterung überträgt diese Daten nicht an GitHub und enthält keine Tracker oder Analyse-Skripte.

Wichtig: Browser und Geräte haben jeweils einen eigenen lokalen Speicher. Eine Planung auf dem PC erscheint daher nicht automatisch auf dem Smartphone. Für Gerätewechsel oder Backups die vorhandene **Export-/Import-Funktion** der App verwenden.

## Updates

Wenn eine neue `index.html` veröffentlicht wird, versucht die App bei bestehender Internetverbindung die aktuelle Version zu laden. Der Service Worker dient als Offline-Fallback.

Wenn später auch `manifest.webmanifest`, Icons oder der Service Worker grundlegend verändert werden, sollte in `service-worker.js` die Konstante `CACHE_NAME` auf einen neuen Versionsnamen gesetzt werden. Dadurch werden alte App-Shell-Caches beim nächsten Update sauber entfernt.

## Datenschutz

Die App enthält keine Felder für personenbezogene Schüler*innendaten und benötigt keine Anmeldung. Planungen, Ziele und Einstellungen bleiben lokal im Browser, sofern sie nicht bewusst über die Export-Funktion als JSON-Datei gespeichert werden.

Wie bei jeder über GitHub Pages ausgelieferten Website entstehen beim Abruf technisch notwendige Verbindungsdaten beim Hosting-Anbieter. Die eigentlichen Unterrichtsplanungen werden durch diese App nicht an GitHub übertragen.

## Hinweise zur Weitergabe

Das Repository kann über Teams oder als GitHub-Link geteilt werden. Wird es öffentlich auf GitHub gestellt, ist auch der Quelltext öffentlich einsehbar. Eine Open-Source-Lizenz ist in diesem Paket bewusst **nicht** vorgegeben; falls die App später ausdrücklich zur freien Weiterverwendung oder Bearbeitung veröffentlicht werden soll, kann eine passende Lizenz ergänzt werden.
