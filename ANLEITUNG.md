# MathWarrior – Upload zu GitHub

## Dateien in diesem Paket

```
MathWarrior/
├── index.html                      <- Das komplette Spiel (neueste Version mit allen Fixes)
├── manifest.json                   <- PWA-Manifest
├── image.png                       <- App-Icon (jetzt ein echtes PNG, vorher war es ein JPEG mit falscher Endung)
└── .github/
    └── workflows/
        └── android.yml             <- GitHub-Actions-Workflow für den APK-Build
```

## So kopierst du die Dateien zu GitHub (am PC)

1. Repository auf GitHub öffnen.
2. `index.html`, `manifest.json` und `image.png` per Drag & Drop ins Repository ziehen
   ("Add file" → "Upload files") und die alten Versionen damit überschreiben.
3. Die Datei `android.yml` muss im Repository unter `.github/workflows/android.yml` liegen.
   Wenn sie dort schon existiert und unverändert ist, musst du sie nicht neu hochladen.
   Achtung: Der Ordner `.github` ist auf dem PC eventuell versteckt
   (in Windows: Explorer → Ansicht → "Ausgeblendete Elemente" aktivieren).
4. Commit mit einer kurzen Beschreibung speichern, z. B. "Fixes: Glücksrad, Schild-Aufgabe, UFO".
5. Der Push auf den `main`-Branch startet automatisch den APK-Build.
   Unter "Actions" → neuester Lauf → "Artifacts" kannst du die fertige
   `MathWarrior-APK` herunterladen.

## Neu in dieser Version (basiert auf deiner aktuellen Version mit Melodie-System!)

- Glücksrad-Gewinne (Items UND Münzen) überleben jetzt Game Over und "Neues Spiel"
  und sind im nächsten Spiel dabei, bis sie tatsächlich benutzt wurden.
  Shop-Items und normale Münzen werden weiterhin wie gehabt zurückgesetzt.
- Nach einem Schildbruch wird die erneut gestellte Aufgabe wieder korrekt angezeigt
  (der Freeze-Fix aus deiner Version bleibt dabei erhalten).
- Weltall-Level: Alle Charaktere fliegen jetzt dasselbe UFO, der gewählte Charakter
  ist als kleines Bild in der Kuppel zu sehen. Der Weltall-Boss ist jetzt 👾 statt 🛸,
  damit sich Spieler-UFO und Boss nicht gleichen.
- Info-Texte (DE/EN) an die neue Glücksrad-Regel angepasst.
- Der Workflow (android.yml) erzeugt automatisch das App-Icon und einen Splashscreen
  aus image.png. WICHTIG: Die neue android.yml muss im Repository unter
  .github/workflows/android.yml liegen, sonst kommt das Icon nicht in die APK!
