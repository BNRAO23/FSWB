# Financial Statement Preparation Workbench

A lightweight, browser-based workbench for preparing and reviewing internal financial statement drafts in an Indian company reporting context. It brings company and board details, a mapped trial balance, draft statements, review checks, and circulation-ready text into one static application.

## Run the application

Open `index.html` in a modern desktop browser. There is no installation, build step, server, or backend database required. The application processes imported files locally in the browser.

## Workflow

1. Review the company profile, reporting period, framework, and board meeting details.
2. Load an `.xlsx`, `.xlsm`, `.csv`, or `.tsv` trial balance using **Load trial balance**. Excel workbooks are read locally; the app selects a sheet whose name contains “Trial Balance”, or the first sheet if there is no match.
3. Review or change each GL account’s statement, major head, line item, and note number in **Map accounts**. Unmapped accounts are excluded from statement totals.
4. Review the Balance Sheet, Profit and Loss statement, indicative Cash Flow statement, notes, compliance checks, and board approval draft.
5. Print or download a Word-compatible draft, CSV statement export, review email, or self-contained HTML draft pack.
6. Save a JSON working file to preserve the imported balances, mappings, and form details for later review. Use **Open working file** to resume.

`TrialBalance.xlsx` is included as a sample. The demo view is preloaded with its trial balance data; use **Reset demo** to restore it.

## Input columns

The spreadsheet should contain a header row with a GL code and account description, plus either:

- `CY Net Amount` and optionally `PY Net Amount`; or
- `CY Debit` and `CY Credit`, and optionally `PY Debit` and `PY Credit`.

Schedule III statement, major head, line item, and note number columns are used when present. If those columns are absent, accounts need to be mapped in the application.

## Outputs and review limitations

- Statement figures are calculated from the mapped balances using their debit/credit sign convention. Current-year profit or loss is included in draft other equity.
- The application flags trial balance differences, incomplete mappings, and Balance Sheet cross-check differences rather than treating them as approved.
- The Cash Flow view is indicative: a trial balance alone does not provide enough activity detail to prepare or verify a complete cash flow statement.
- Notes and board approval content are drafting aids. Confirm accounting policies, Schedule III disclosures, statutory applicability, figures, audit status, approvals, signatures, and filing requirements with the responsible professionals before circulation or filing.
- Data is not sent to a server. Working files and exported documents contain company information; store and share them appropriately.

## Project files

- `index.html` — complete static application
- `SPEC.md` — application requirements
- `TrialBalance.xlsx` — sample mapped trial balance workbook
- `fswb.png` — interface reference image

The project does not currently declare a software license.
