# CoSi API - Gemini CLI Nutzungsleitfaden

Diese Version des Gemini CLI wurde für die Nutzung mit dem internen **CoSi API**
Proxy angepasst.

## 1. Installation

Du hast eine Datei mit der Endung `.tgz` erhalten (z.B.
`google-gemini-cli-0.30.0...tgz`).

Führe den folgenden Befehl in deinem Terminal aus (im selben Ordner wie die
Datei), um das Tool global zu installieren:

```bash
npm install -g ./google-gemini-cli-0.30.0-nightly.20260210.a2174751d.tgz
```

_Hinweis: Nach der Installation steht dir der Befehl `gemini` zur Verfügung._

## 2. Konfiguration

Damit das Tool den internen Proxy korrekt anspricht, müssen zwei
Umgebungsvariablen gesetzt werden.

### Erforderliche Umgebungsvariablen

| Variable        | Beschreibung                                   |
| :-------------- | :--------------------------------------------- |
| `COSI_API_KEY`  | Dein persönlicher API-Key für die CoSi API.    |
| `COSI_BASE_URL` | Die vollständige URL des CoSi Proxy-Endpunkts. |

### Dauerhafte Einrichtung (Empfohlen)

Füge die folgenden Zeilen in deine Shell-Konfigurationsdatei ein (für macOS
meist `~/.zshrc`, für Linux `~/.bashrc`):

```bash
# Gemini CLI CoSi Konfiguration
export COSI_API_KEY="DEIN_INTERNER_API_KEY"
export COSI_BASE_URL="https://dein-cosi-proxy-server.de"
```

Lade die Datei danach neu: `source ~/.zshrc` (oder das entsprechende
Gegenstück).

## 3. Nutzung

Starte das Tool einfach über das Terminal:

```bash
gemini
```

### Authentifizierung im Tool

Beim ersten Start erscheint ein Auswahlmenü. Wähle hier: **`CoSi API`**

Das Tool nutzt dann automatisch den erforderlichen `x-api-key` Header für alle
Anfragen.

## 4. Tipps & Tricks

- **Proxy-URL in Settings**: Alternativ zu Umgebungsvariablen kannst du die URL
  auch dauerhaft in der Datei `~/.gemini/settings.json` festlegen:
  ```json
  {
    "general": {
      "cosiBaseUrl": "https://dein-cosi-proxy-server.de"
    }
  }
  ```

---

_Interner Leitfaden - Nur für den Dienstgebrauch._
