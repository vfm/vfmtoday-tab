# vfmtoday-tab

Statische HTML-Dateien für die **vfm Today** Microsoft Teams App.

Diese Dateien werden über **GitHub Pages** gehostet und dienen als Wrapper für den
[vfm Today Kalender](https://vfmtoday.vfm.de/kalender), der hinter einem
Entra Application Proxy mit Vorauthentifizierung läuft.

## Dateien

| Datei | Zweck |
|-------|-------|
| `teams-tab.html` | Teams Tab – initialisiert das Teams SDK und öffnet ein Auth-Popup |
| `auth-end.html` | Callback-Seite – schließt das Auth-Popup nach erfolgreicher Anmeldung |

## Warum dieses Repo?

Die Kalender-Seite `vfmtoday.vfm.de` läuft hinter einem **Entra Application Proxy**
mit Vorauthentifizierung. Der Login-Redirect (`login.microsoftonline.com`) blockiert
die Anzeige in iframes (`X-Frame-Options: DENY`). Diese HTML-Dateien lösen das Problem
über den Teams Popup-Authentifizierungsfluss.

## Deployment

Dieses Repo nutzt **GitHub Pages** (automatisch via GitHub Actions).

Nach jedem Push auf `main` werden die HTML-Dateien unter folgender URL verfügbar:

- `https://vfm.github.io/vfmtoday-tab/teams-tab.html`
- `https://vfm.github.io/vfmtoday-tab/auth-end.html`

## Verknüpftes Repo

Das Teams App Manifest und der Build befinden sich im privaten Repo:
[vfm/msteams-app-vfmtoday](https://github.com/vfm/msteams-app-vfmtoday) (privat)
