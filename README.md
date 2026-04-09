# Sjøgang

**Sjøgang** er en lokal surf conditions-app for Agder.

Appen skal gjøre det enklere å forstå surfeforhold ved å samle og presentere relevante data som:
- bølger
- swell
- vind
- periode
- tidevann
- lokale spot-vurderinger


Navnet *Sjøgang* kommer fra oseanografi, der sjøgang beskriver havoverflatens tilstand når det gjelder bølger forårsaket av vind og dønninger.

---

## Visjon

Sjøgang skal hjelpe surfere med å svare på ett enkelt spørsmål:

**Er det verdt å surfe her nå, i dag eller i morgen?**

Målet er ikke å bygge en generisk værapp, men en lokal og nyttig surfetjeneste for kaldtvannssurf og norske forhold.

---

## Første fokusområde

Første versjon er laget for:
- Agder

På sikt kan appen utvides til flere spots og regioner.

---

## Tech stack

### Frontend
- React
- TypeScript
- Vite
- React Router
- TanStack Query eller enkel fetch i starten
- Tailwind CSS eller enkel modulbasert styling

### Backend
- Java
- Spring Boot
- Spring Web
- Spring Security
- Spring Data JPA
- PostgreSQL

---

## Hvorfor denne stacken?

Sjøgang bygges med **React + Spring Boot** fordi:

- React gir en god måte å lære moderne frontend i et ekte prosjekt
- Spring Boot er allerede kjent teknologi og passer godt til API, auth og domenelogikk
- denne kombinasjonen gjør det lettere å bygge videre senere med mer interaktive dashboards, spot-sider og webcam-funksjonalitet

Dette er ikke nødvendigvis den absolutt raskeste stacken for å shippe en MVP, men det er en bevisst balanse mellom læring og produktbygging.

---

## Produktretning

Sjøgang skal ikke bare vise rå værdata.

Produktet skal etter hvert gi:
- lokale spot-sider
- surf-relevante forhold
- enkel vurdering av om spotten er bra eller dårlig
- tydelig visning av vind, bølger, periode og tidevann
- bedre lokal forståelse enn en generell værapp

---

## MVP

Første versjon skal være liten, enkel og nyttig.

### Målet for MVP
- vise lokale spots
- vise forecast-data for hver spot
- gjøre forholdene lettere å forstå
- la brukeren lagre favoritter

### MVP-funksjoner
- registrering og login
- liste over spots
- spot-detaljside
- bølgehøyde
- swell-retning
- periode
- vindstyrke og vindretning
- tidevann
- favorittspots
- enkel status eller score for forholdene



## Arkitektur

Prosjektet deles i to hovedområder:

### Plattformlag
Generiske SaaS-funksjoner:
- auth
- bruker
- konto
- abonnement
- settings

### Domenelag
Surf- og havlogikk:
- spots
- forecast
- tide
- favorites
- scoring


---

## Prosjektstruktur

```text
sjogang/
  backend/
    src/main/java/no/sjogang/
      auth/
      user/
      spot/
      forecast/
      tide/
      favorites/
      scoring/
      webcam/
    src/main/resources/

  frontend/
    src/
      app/
      components/
      features/
        spots/
        forecast/
        favorites/
      pages/
      api/
      hooks/
      types/

  docs/
