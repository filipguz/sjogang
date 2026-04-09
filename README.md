# Sjøgang

**Sjøgang** er en lokal surf intelligence-app for Agder.

Appen samler og tolker vær- og havdata for å gi én enkel ting:

**En tydelig vurdering av surfeforholdene på lokale spots.**

---

## Hva er Sjøgang?

Sjøgang er ikke en vanlig værapp.

Det er en **lokal surf intelligence-plattform** som:
- samler data fra flere vær- og hav-API-er
- normaliserer dataene til én modell
- kobler data til konkrete surf spots
- gir en enkel vurdering av forholdene

Målet er å gjøre det enklere å svare på:

**Er det verdt å surfe i dag?**

---

## Første fokusområde

Sjøgang bygges først for:

- Agder
- Lista
- Vanse
- utvalgte lokale surf spots

Produktet er lokalt først, og kan utvides senere.

---

## Hvordan det fungerer

Sjøgang fungerer som en aggregator + tolk:

1. Henter data fra eksterne kilder:
   - bølger / swell
   - vind
   - periode
   - tidevann

2. Normaliserer data til én intern modell

3. Knytter data til surf spots

4. Beregner en enkel vurdering:
   - dårlig
   - ok
   - bra
   - veldig bra

5. Presenterer dette i en enkel og tydelig UI

---

## Hvorfor dette er nyttig

Eksisterende vær- og surf-tjenester:
- viser ofte rådata
- er globale og lite lokale
- krever erfaring for å tolke

Sjøgang skal:
- være lokalt relevant
- være enkel å forstå
- gi direkte verdi uten tolkning

---

## Tech stack

### Frontend
- React
- TypeScript
- Vite
- React Router
- TanStack Query (eller enkel fetch i starten)

### Backend
- Java
- Spring Boot
- Spring Web
- Spring Security
- Spring Data JPA
- PostgreSQL

---

## Arkitektur

Backend fungerer som en **data-aggregator og intelligence-lag**.

### Lagdeling

#### 1. Providers
Integrasjoner mot eksterne API-er:
- værdata
- bølger
- tidevann

Eksempler:
- MetProvider
- OpenMeteoProvider
- StormglassProvider

#### 2. Normalisering
Oversetter rådata til en intern modell:

- `SpotConditions`
- `ForecastSnapshot`
- `TideSnapshot`

#### 3. Persistence / cache
- lagrer data lokalt
- reduserer API-kall
- muliggjør historikk

#### 4. Domenelogikk
- kobler data til spots
- evaluerer forhold
- beregner score

#### 5. API
Eksponerer data til frontend:
- `/api/spots`
- `/api/spots/{slug}`
- `/api/spots/{slug}/conditions`

---

## Intern datamodell (eksempel)

```text
SpotConditions
- spotSlug
- timestamp
- waveHeightMeters
- swellDirection
- wavePeriodSeconds
- windSpeed
- windDirection
- tideLevel
- score
- summary
