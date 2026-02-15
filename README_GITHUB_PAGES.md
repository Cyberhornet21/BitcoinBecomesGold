# BTC Correlation Analyzer - GitHub Pages Ready! 🚀

## ✅ FUNKTIONIERT AUF GITHUB PAGES!

Diese Version nutzt **kostenlose CORS-Proxies** und funktioniert perfekt auf GitHub Pages!

## 🎯 Was wurde behoben:

### Problem: Yahoo Finance blockiert CORS
Yahoo Finance erlaubt keine direkten API-Aufrufe aus dem Browser (CORS-Sicherheit).

### Lösung: CORS-Proxies
Die App nutzt jetzt **3 kostenlose CORS-Proxies**:
1. **corsproxy.io** - Hauptproxy (kostenlos, kein API Key)
2. **allorigins.win** - Backup 1
3. **codetabs.com** - Backup 2

Die App versucht alle nacheinander bis einer funktioniert!

## 🚀 Deployment auf GitHub Pages

### Schritt 1: Repository erstellen
```bash
git init
git add index.html
git commit -m "BTC Correlation Analyzer"
git branch -M main
git remote add origin https://github.com/DEIN-USERNAME/DEIN-REPO.git
git push -u origin main
```

### Schritt 2: GitHub Pages aktivieren
1. Gehe zu deinem Repository auf GitHub
2. Klicke auf **Settings**
3. Scrolle zu **Pages** (linke Sidebar)
4. Bei **Source** wähle: **main branch**
5. Klicke **Save**

### Schritt 3: Warten (5-10 Minuten)
GitHub Pages braucht ein paar Minuten zum Deployen.
Deine URL wird sein: `https://DEIN-USERNAME.github.io/DEIN-REPO/`

### Schritt 4: Testen!
Öffne die URL und die App sollte funktionieren! 🎉

## 🔧 Wie es funktioniert

```javascript
// Ohne Proxy (blockiert):
fetch('https://query1.finance.yahoo.com/v8/finance/chart/IGV')
❌ CORS Error

// Mit Proxy (funktioniert):
fetch('https://corsproxy.io/?url=https://query1.finance.yahoo.com/...')
✅ Daten geladen!
```

Der Proxy leitet die Anfrage weiter und fügt die nötigen CORS-Header hinzu.

## 📊 Datenquellen

- **Bitcoin**: CoinGecko API (direkt, kein Proxy nötig)
- **Gold**: CoinGecko API (direkt, kein Proxy nötig)  
- **Software ETF (IGV)**: Yahoo Finance via CORS-Proxy

## ✅ Tab-Wechsel funktioniert

- **BTC GOLD Tab**: Bitcoin ↔ Gold Korrelation & Preise
- **BTC SOFTWARE Tab**: Bitcoin ↔ IGV Software ETF Korrelation & Preise
- Daten werden beim Start geladen und gespeichert
- Beim Wechseln werden die richtigen Daten angezeigt

## 🐛 Troubleshooting

### "CORS PROXY FEHLER"
**Ursachen:**
- Die Proxies sind überlastet (passiert manchmal)
- GitHub Pages ist noch am Deployen
- Temporäres Netzwerkproblem

**Lösungen:**
1. **Warte 1-2 Minuten** und lade neu (F5)
2. **Prüfe Browser Console** (F12) für Details
3. **GitHub Pages braucht Zeit**: Nach dem ersten Deploy kann es 5-10 Minuten dauern

### Charts zeigen keine Daten
- Warte bis "ANALYSIS COMPLETE" im System Log erscheint
- Öffne die Browser Console (F12) und schau nach Fehlern
- Lade die Seite neu (Ctrl+F5 oder Cmd+Shift+R)

### Lokales Testen
Wenn du lokal testen willst (vor GitHub Pages):
```bash
# Python
python -m http.server 8000

# Node.js
npx http-server

# Dann: http://localhost:8000
```

**WICHTIG**: Öffne NICHT als `file://` - das funktioniert nicht!

## 🎯 Alternative: Netlify

Falls GitHub Pages Probleme macht, nutze Netlify:
1. Gehe zu: https://app.netlify.com/drop
2. Ziehe `index.html` rein
3. Fertig! (funktioniert sofort)

## 💡 Warum CORS-Proxies?

CORS (Cross-Origin Resource Sharing) ist eine Browser-Sicherheitsfunktion:
- Browser blockieren Anfragen an andere Domains aus Sicherheitsgründen
- Yahoo Finance hat absichtlich kein CORS aktiviert
- CORS-Proxies umgehen das, indem sie die Anfrage serverseitig machen

Die Proxies sind:
- ✅ Kostenlos
- ✅ Kein API Key nötig
- ✅ Öffentlich verfügbar
- ✅ Weitverbreitet

## 📝 Git Commands Cheat Sheet

```bash
# Änderungen committen
git add index.html
git commit -m "Update: CORS proxy implementation"
git push

# Status prüfen
git status

# Letzte Commits anzeigen
git log --oneline -5
```

## 🎊 Zusammenfassung

✅ Funktioniert auf GitHub Pages  
✅ Keine API Keys nötig  
✅ 100% kostenlos  
✅ Echte Marktdaten  
✅ 3 Proxy-Fallbacks  
✅ Tab-Wechsel korrekt  
✅ Keine Simulation

**Deploy auf GitHub Pages und genieße!** 🚀

## ⚠️ Wichtiger Hinweis

CORS-Proxies können manchmal überlastet sein. Falls alle 3 Proxies nicht funktionieren:
- Warte ein paar Minuten
- Lade die Seite neu
- Die Proxies erholen sich schnell

Das ist normal bei kostenlosen Services, aber meistens funktioniert mindestens einer der drei!
