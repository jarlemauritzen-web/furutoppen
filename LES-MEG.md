# Furutoppen – app for iPhone og iPad

Hjulet for lys, stemning, varme, musikk og screens som egen app på hjemskjermen. Den snakker direkte med Homey via Homeys API, uten Homey-appen og uten Claude.

## 1. Lag en API-nøkkel i Homey (2 min)

1. Gå til my.homey.app på en PC eller Mac og logg inn.
2. Gå til **Innstillinger → API-nøkler → Ny API-nøkkel**. Kall den «Furutoppen-app».
3. Kryss av for: **Enheter** (se og styre), **Soner** (se), **Logic / variabler** (se og endre), **Stemninger** (se og sette) og **Apper** (bruke). Det siste trengs bare hvis appen må gå via reserveveien, se under.
4. Kopier nøkkelen. Den vises bare én gang. Send den til deg selv på en trygg måte, for eksempel med AirDrop eller i Notater, så du kan lime den inn på telefonen. Ikke lim den inn i en chat.

## 2. Legg appen på GitHub Pages (5 min, én gang)

1. Gå til github.com → **New repository**. Kall det `furutoppen`, velg **Public** og trykk **Create repository**.
2. Trykk **uploading an existing file** og dra inn alle filene i denne mappen: `index.html`, `manifest.webmanifest`, `sw.js` og de tre `icon-*.png`. Trykk **Commit changes**.
3. Gå til **Settings → Pages**. Under *Branch* velger du `main` og `/ (root)`, og trykker **Save**.
4. Etter et minutt eller to får du adressen, `https://<brukernavn>.github.io/furutoppen/`.

Repoet er offentlig, men det inneholder ingen hemmeligheter. API-nøkkelen ligger bare på telefonen.

## 3. Installer på iPhone og iPad

1. Åpne adressen i **Safari**.
2. Lim inn API-nøkkelen og trykk **Koble til**. Homey-adressen er fylt ut på forhånd.
3. Trykk **Del → Legg til på Hjem-skjerm**.

Appen åpnes nå i fullskjerm med eget ikon. Gjør det samme på iPad. Hver enhet trenger nøkkelen én gang.

## Hvis tilkoblingen feiler

- **«API-nøkkelen ble avvist»:** Sjekk at nøkkelen er limt inn helt, og at den har tilgangene over.
- **«nettverk eller CORS»:** Homey slipper ikke gjennom kall fra en side på en annen adresse. Appen prøver da automatisk reserveveien via Furutoppen-appen på Homey (versjon 1.3.0 eller nyere). Installer den nye pakken med `npx homey app install`, og sørg for at nøkkelen har tilgangen **Apper**. Si fra om det fortsatt feiler.

## Senere endringer

Jeg lager en ny `index.html`, og du laster den opp i repoet med samme navn. Appen henter den nye versjonen neste gang den åpnes med nett.

Tilkoblingen endrer du i menyen øverst til høyre på forsiden → **Homey-tilkobling**.
