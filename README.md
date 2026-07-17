# MathWarrior 🥷⚔️👹

Kopfrechnen-Abenteuer für Klasse 1–4: Löse Mathe-Aufgaben, besiege Monster und rette Zahlenland!

## 📁 Dateistruktur im Repository

So müssen die Dateien bei GitHub liegen (die Ordner `.github/workflows` bitte genau so anlegen):

```
MathWarrior/
├── .github/
│   └── workflows/
│       ├── android.yml        <- baut die APK automatisch
│       └── pages.yml          <- veröffentlicht das Spiel als Webseite (PWA)
├── index.html                 <- das komplette Spiel
├── manifest.json              <- PWA-Konfiguration (Name, Icons, Farben)
├── sw.js                      <- Service Worker (Offline-Modus + Installierbarkeit)
├── image.png                  <- Original-Logo (1036x1036)
├── icon-192.png               <- App-Icon 192x192
├── icon-512.png               <- App-Icon 512x512
├── icon-512-maskable.png      <- App-Icon für runde Android-Icons
├── apple-touch-icon.png       <- Icon für iPhone/iPad-Homescreen
└── README.md
```

## 🚀 Einrichtung (einmalig)

1. Alle Dateien wie oben gezeigt ins Repository hochladen (Branch `main`).
2. **GitHub Pages aktivieren:** Repository → *Settings* → *Pages* → bei *Source* die Option **"GitHub Actions"** auswählen.
3. Fertig! Bei jedem Push auf `main` laufen beide Workflows automatisch (Tab *Actions*).

## 📱 Variante A: APK installieren

1. Tab **Actions** → Workflow **"Build Android APK"** → letzten grünen Lauf öffnen.
2. Unten bei **Artifacts** die Datei **MathWarrior-APK** herunterladen und entpacken.
3. `app-debug.apk` aufs Handy übertragen und installieren ("Unbekannte Quellen" erlauben).

## 🌐 Variante B: Per Link über Chrome installieren (PWA)

1. Nach dem ersten erfolgreichen "Deploy to GitHub Pages"-Lauf ist das Spiel erreichbar unter:
   `https://DEIN-GITHUB-NAME.github.io/REPOSITORY-NAME/`
2. Diesen Link auf dem Handy in **Chrome** öffnen.
3. Chrome-Menü (⋮) → **"App installieren"** bzw. **"Zum Startbildschirm hinzufügen"**.
4. MathWarrior erscheint wie eine echte App mit eigenem Icon und läuft danach auch offline.

> 💡 Nach jeder Spiel-Änderung in der `sw.js` die Zeile `CACHE_NAME = 'mathwarrior-v1'`
> hochzählen (v2, v3, …), damit installierte PWAs die neue Version laden.

## 🏪 Vorbereitung Play Store (später)

Das Projekt ist bereits vorbereitet:
- Eindeutige App-ID: `com.simon.mathwarrior`
- Launcher-Icons werden im Workflow automatisch aus `image.png` generiert
- Vollständiges PWA-Manifest (Name, Beschreibung, Kategorien, maskable Icon)
- Versionsnummer zentral in `android.yml` (Zeile mit `"version": "1.0.0"`)

Für die Veröffentlichung fehlen dann noch (klären wir, wenn es soweit ist):
1. Ein **Signatur-Schlüssel** (Keystore) + signierter **Release-Build** (AAB statt Debug-APK)
2. Ein **Google Play Console**-Konto (einmalig 25 $)
3. Store-Einträge: Screenshots, Beschreibung, Datenschutzerklärung, Altersfreigabe

## 🎮 Spielprinzip

Mathe-Aufgaben schnell lösen = Angriff. Timer abgelaufen oder falsche Antwort = das Monster
schlägt zu. 12 Welten pro Klassenstufe, Bosse, Shop, Glücksrad und Highscores.
Jedes neue Spiel startet komplett frisch (Münzen, Items und Outfits werden zurückgesetzt),
damit das Kopfrechnen-Training fordernd bleibt.

---
App-Entwickler: **Simon Mählmann**
