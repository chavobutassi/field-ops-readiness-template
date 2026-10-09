# Data dictionary

All dates are text. Use `YYYY-MM-DD`, and `YYYY-MM-DD HH:MM` for event timestamps. Yes/no columns accept `yes` or `no`. Do not rename sheets or headings (capital letters do not matter). Ids must be unique inside their table.

## clients (one row per site or customer)

| Column | Required | What to write | Example |
|---|---|---|---|
| id | yes | Short unique code | S-0001 |
| name | yes | Site or customer name | Dunmore Office Park |
| type | yes | Kind of site. Use your own list and keep it consistent | Office / municipal |
| zone | yes | Service area, borough or district | Manhattan |
| plan | yes | Service plan | Daily service |
| installed_year | yes | Year the client started | 2019 |
| equipment_count | yes | Crew or equipment normally assigned | 13 |
| last_service_date | yes | Last major service, `YYYY-MM-DD` | 2026-04-26 |
| status | yes | `OK`, `Open violation`, `Supplies low` or `Deep clean due` | OK |
| supplies_audit_date | no | Last supplies check | 2026-03-07 |
| snow_duty | no | Does the site need snow and ice work? `yes` or `no` | yes |

Other organizations can replace the status list and the two optional columns with their own (for example battery age for alarm systems). Keep the same column positions.

## events (incidents, calls and findings)

| Column | Required | What to write | Example |
|---|---|---|---|
| id | yes | Unique code | E-00001 |
| timestamp | yes | `YYYY-MM-DD HH:MM` | 2025-11-01 08:08 |
| client_id | yes | Must exist in `clients` | S-0002 |
| type | yes | Kind of event | Snow / ice response |
| subtype | yes | More detail, free text | Sidewalk ice |
| first_response_min | yes | Minutes until someone responded | 14 |
| dispatched | yes | Was a crew sent? `yes` or `no` | yes |
| resolved | yes | Is it solved? `yes` or `no` | yes |

## technicians (supervisors and crew leads)

| Column | Required | What to write | Example |
|---|---|---|---|
| id | yes | Unique code | T-01 |
| name | yes | Full name | Elena Marquez |
| role | yes | Job title | Operations manager |
| zones | yes | Areas covered. Separate several with `;` | Manhattan;Brooklyn |
| shift | yes | `Day` or `On call` | Day |
| status | yes | `On job`, `Available`, `On call` or `Off shift` | On job |

## credentials (certificates and training)

| Column | Required | What to write | Example |
|---|---|---|---|
| technician_id | yes | Must exist in `technicians` | T-01 |
| name | yes | Certificate name | OSHA 10-hour |
| expires_on | yes | `YYYY-MM-DD` | 2027-08-04 |

One row per certificate. A person can have several rows.

## work_orders (open jobs)

| Column | Required | What to write | Example |
|---|---|---|---|
| id | yes | Unique code | WO-1001 |
| client_id | yes | Must exist in `clients` | S-0001 |
| type | yes | Kind of job | Deep sanitation |
| priority | yes | `Urgent`, `High` or `Normal` | High |
| due_date | yes | `YYYY-MM-DD` | 2026-10-15 |
| technician_id | no | Leave empty if nobody is assigned | T-04 |
| status | yes | `Unassigned`, `Scheduled` or `In progress` | Scheduled |
| tasks | no | The checklist, separated with `;` | Strip old wax;Apply 3 coats;Photograph the result |

## Common mistakes

- An `events`, `credentials` or `work_orders` row that points to an id that does not exist in `clients` or `technicians`.
- Dates typed as `10/03/2026` instead of `2026-10-03`.
- A status that is not in the list (for example `Sick`).
- Duplicate ids.
