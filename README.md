# Field Operations Readiness Template

An open, spreadsheet-based standard for small and mid-sized organizations that run field crews and keep essential facilities working: building cleaning and maintenance, private security, alarm monitoring, water and utility contractors, and similar services.

It answers one question each week: **are we ready, and where should we look first?**

You do not need special software. Five flat tables, exported from a spreadsheet or from the software you already use, are enough to calculate coverage, certification status, response time, backlog and workload for every site and service area.

## What is in this repository

| Folder | Contents |
|---|---|
| `templates/` | A blank Excel workbook with five sheets and drop-down lists, plus blank CSV files |
| `sample_data/` | A complete set of **simulated** data (Excel and CSV) to practice with |
| `docs/data_dictionary.md` | Every column: what to write, allowed values, examples |
| `docs/readiness_index.md` | How the weekly readiness score is calculated |
| `docs/weekly_routine.md` | A 30-minute weekly routine that a new supervisor can follow |
| `docs/pilot_protocol_90_days.md` | A 90-day pilot with a baseline, weekly measures and targets |

## The five tables

1. **clients**: the sites or customers you serve.
2. **events**: incidents, calls and findings, with response times.
3. **technicians**: supervisors or crew leads, their areas and shifts.
4. **credentials**: certificates and training, with expiry dates.
5. **work_orders**: open jobs, priority, due date and assignee, with an optional checklist.

## Quick start

1. Copy `templates/field_ops_blank_template.xlsx`.
2. Delete the example rows and paste in your own data, one sheet per table. Fill `clients` and `technicians` first: the other three tables refer to their ids.
3. Check your file against `docs/data_dictionary.md`.
4. Follow `docs/weekly_routine.md` every week.

Dates are text in the form `YYYY-MM-DD` (events use `YYYY-MM-DD HH:MM`). Do not rename sheets or column headings.

## Weekly readiness index

A score from 0 to 100 per service area, made of coverage (30%), credentials (20%), response speed (15%), equipment or site condition (20%) and backlog (15%). The formula is in `docs/readiness_index.md`. The weights are a starting point. Change them to fit your operation.

## Design principles

- **Open formats.** CSV and plain Excel. No lock-in.
- **Replicable.** A small operator can adopt it in an afternoon.
- **Privacy first.** Use only the data you need. Do not put personal identifiers or sensitive records in the tables.
- **Measure, then decide.** Every number can be checked against your own records.

## Status

Version 0.1. The sample data is simulated, and no real organization's data is included. Suggestions and corrections are welcome as issues or pull requests.

## Author

Claudio Julián Butassi, Data Analytics.
GitHub: [chavobutassi](https://github.com/chavobutassi). Portfolio: [cjbutassi-datar.vercel.app](https://cjbutassi-datar.vercel.app).

## License

MIT. See `LICENSE`.
