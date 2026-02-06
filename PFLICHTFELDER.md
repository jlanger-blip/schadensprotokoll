# Pflichtfelder Schadensprotokoll

**Deaktiviert am:** 2026-02-06 für Testzwecke

## HTML Input Felder (required Attribut)

| Zeile | Feld-ID | Beschreibung |
|-------|---------|--------------|
| 369 | date | Unfalldatum |
| 373 | time | Unfallzeit |
| 377 | location | Unfallort |
| 382 | employee | Mitarbeitername |
| 401 | plate | Kennzeichen |
| 405 | model | Fahrzeugmodell |
| 409 | mileage | Kilometerstand |
| 424 | faultType | Schadensart (Select) |
| 436 | police (radio) | Polizei hinzugezogen |
| 444 | faultCleared (radio) | Schuldfrage geklärt |
| 503 | driveable (radio) | Fahrzeug fahrbereit |

## Dynamische Pflichtfelder (JS)

- **faultComment** - Pflicht wenn faultCleared = "nein" (Zeile 617)
- **carLocation** - Pflicht wenn driveable = "nein" (Zeile 630)

## Foto-Pflichtfelder (photoRequirements Array, Zeile 662-668)

| ID | Titel | Pflicht |
|----|-------|---------|
| photo_front | Front | ✅ Ja |
| photo_rear | Heck | ✅ Ja |
| photo_left | Linke Seite | ✅ Ja |
| photo_right | Rechte Seite | ✅ Ja |
| photo_damage1 | Schaden Detail 1 | ✅ Ja |
| photo_damage2 | Schaden Detail 2 | ❌ Nein |
| photo_tacho | Tacho | ✅ Ja |

## JavaScript Validation (Zeile 727)

```javascript
const requiredFields = ['date', 'time', 'location', 'employee', 'plate', 'model', 'mileage', 'faultType'];
```

## Wiederherstellen

Um die Pflichtfelder wieder zu aktivieren:

1. In `index.html` suchen nach `// PFLICHTFELDER DEAKTIVIERT`
2. Die auskommentierten `required` Attribute wieder einkommentieren
3. In `validateForm()` die Validierung wieder aktivieren
4. `photoRequirements` Array: `required: true` wieder setzen
