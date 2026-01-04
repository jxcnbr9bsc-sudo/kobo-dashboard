# Kobo Dashboard

Dashboard E-ink per Kobo Aura N514 (2013) con meteo, orologio e calendario.

## Caratteristiche

- **Orologio digitale** aggiornato ogni minuto
- **Meteo Padova** con previsioni 3 giorni (API OpenMeteo)
- **Calendario famiglia** integrato con Google Calendar via Apps Script
- **Design minimalista** stile Dieter Rams (bianco/nero)
- **Compatibilità ES5** per browser WebKit 2013

## Tecnologie

- HTML5, CSS3 (Flexbox), JavaScript ES5
- Google Apps Script per integrazione calendario
- OpenMeteo API per dati meteo
- Font DM Sans da Google Fonts

## Setup

1. Configura l'URL del Google Apps Script in `index.html`:
   ```javascript
   var CALENDAR_API_URL = "IL_TUO_URL_APPS_SCRIPT";
   ```

2. Apri `index.html` nel browser del Kobo o in un browser moderno per test.

## Google Apps Script

Lo script deve avere una funzione `doGet()` che restituisce JSON:

```javascript
function doGet() {
  var events = [
    { time: "18:00", text: "Spesa settimanale" }
  ];
  
  return ContentService
    .createTextOutput(JSON.stringify(events))
    .setMimeType(ContentService.MimeType.JSON);
}
```

Pubblica come "Web app" con accesso "Chiunque, anche anonimo".

## GitHub Pages

Il dashboard è pubblicato su GitHub Pages:
https://jxcnbr9bsc-sudo.github.io/kobo-dashboard/

## Licenza

MIT

