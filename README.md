# Grant Deadline Tracker

A small command-line tool (Node.js, no dependencies) that reads a CSV file of grant
opportunities and shows them sorted by deadline.

## Why I built it
Nonprofits and small teams often track grant deadlines in a spreadsheet and miss them.
This tool turns that spreadsheet into a clear list of what is due soon.

## Run it
You need Node.js 18 or newer.

```bash
node src/index.js                          # all grants, soonest first
node src/index.js --within 60              # only deadlines in the next 60 days
node src/index.js --status open            # only grants with status "open"
node src/index.js --within 60 --status open
node src/index.js --file my-grants.csv     # use your own CSV file
node src/index.js --help
```

## CSV format
```
name,funder,deadline,amount_usd,status
Example Digital Rights Grant,Example Foundation A,2026-11-30,15000,open
```
Dates must be written as `YYYY-MM-DD`. The names in `data/sample-grants.csv` are made-up examples.
Rows with an invalid date are not hidden. The tool lists them as skipped.

## Test it
```bash
node --test
```

## What I would improve next
- Rewrite it in TypeScript.
- Handle commas inside quoted CSV fields.
- Add an option to export the upcoming list as a Markdown table.
- Send a reminder email a week before a deadline.

## A note on AI
I built this starter with help from an AI coding assistant, then read every line, ran the
tests and checked the output. I am using it to rebuild my coding habit.
