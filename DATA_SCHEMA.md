# Data Schema

All data is stored in `localStorage` under the key `lifeOS_v1` as a single JSON object.

## Top-level structure

```json
{
  "fin": [],
  "gym": [],
  "diet": [],
  "checkins": [],
  "career": {},
  "projects": [],
  "skills": [],
  "goals": []
}
```

---

## Finances — `fin[]`

Monthly snapshot. One entry per month.

| Field | Type | Description |
|---|---|---|
| `month` | string | `YYYY-MM` format, e.g. `"2025-04"` |
| `inc` | number | Total income (₹) |
| `exp` | number | Total expenses (₹) |
| `sav` | number | Auto-calc: `inc - exp` |
| `mf` | number | Mutual funds value (₹) |
| `st` | number | Stocks value (₹) |
| `fd` | number | FD / savings balance (₹) |
| `inv` | number | Auto-calc: `mf + st + fd` |
| `nw` | number | Auto-calc: `inv + sav` |

---

## Gym log — `gym[]`

One entry per session.

| Field | Type | Description |
|---|---|---|
| `date` | string | `YYYY-MM-DD` |
| `group` | string | Chest / Back / Legs / Shoulders / Arms / Full body |
| `ex` | string | Exercises done (free text) |
| `sets` | number | Sets completed |
| `dur` | number | Duration in minutes |
| `rating` | number | 1–5 star rating |

---

## Diet log — `diet[]`

One entry per day.

| Field | Type | Description |
|---|---|---|
| `date` | string | `YYYY-MM-DD` |
| `meals` | number | Number of meals |
| `kcal` | number | Approx. calories |
| `prot` | number | Protein in grams |
| `water` | number | Water in litres |
| `adhere` | string | On plan / Mostly on plan / Off plan |
| `cheat` | boolean | Cheat meal logged |

---

## Weekly check-in — `checkins[]`

| Field | Type | Description |
|---|---|---|
| `date` | string | `YYYY-MM-DD` (week start) |
| `weight` | number | Body weight in kg |
| `sessions` | number | Gym sessions that week |
| `energy` | string | High / Medium / Low |
| `sleep` | number | Average sleep hours |
| `notes` | string | Free-text observations |

---

## Career profile — `career{}`

Single object, updated in place.

| Field | Type | Description |
|---|---|---|
| `role` | string | Current job title |
| `company` | string | Company name |
| `exp` | number | Years of experience |
| `milestone` | string | Next career milestone |
| `target` | string | `YYYY-MM-DD` target date |

---

## Projects — `projects[]`

| Field | Type | Description |
|---|---|---|
| `name` | string | Project name |
| `status` | string | In progress / Planning / Done / On hold |
| `target` | string | `YYYY-MM-DD` deadline |

---

## Skills — `skills[]`

| Field | Type | Description |
|---|---|---|
| `name` | string | Skill name |
| `level` | string | Beginner / Intermediate / Advanced / Expert |

---

## Goals — `goals[]`

| Field | Type | Description |
|---|---|---|
| `title` | string | Goal title |
| `cat` | string | Finance / Career / Health / Personal |
| `q` | string | Q1 / Q2 / Q3 / Q4 |
| `date` | string | `YYYY-MM-DD` target date |
| `kr1` | string | Key result 1 description |
| `kr1p` | number | KR1 progress 0–100 |
| `kr2` | string | Key result 2 description |
| `kr2p` | number | KR2 progress 0–100 |
| `status` | string | Not started / In progress / At risk / Done |
| `note` | string | Reflection note |
