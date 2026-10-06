# copilot-finance

## What it does

Finance Reviewer: variance analysis, invoice vs PO checks, reconciliations and commentary drafts from exported files.

Part of the **department-copilots** suite: local-only copilots where the employee provides the input, Claude analyses it on the machine, and the employee decides what to do. No CRM, NMS, email or system integrations.

## Install

```bash
claude plugin marketplace add sara-hamza/department-copilots
```

```bash
claude plugin install finance@department-copilots
```

Drop in the export (invoice, PO, budget vs actual, two lists to reconcile) or paste the numbers, and get back the variance, where it sits, what does not match and a commentary draft you can paste into the month-end pack.

| Command | Use when |
|---|---|
| `/finance:invoice-check <invoice + PO>` | Invoice has arrived: totals, variance $ and %, line differences, duplicates, rate differences, GST sanity |
| `/finance:variance <budget vs actual export>` | Month-end: variance by line and period, top drivers, explanation draft |
| `/finance:reconcile <list A + list B>` | Two lists that should agree: MATCHED / ONLY IN A / ONLY IN B / AMOUNT DIFFERENCES |
| `/finance:commentary <numbers or variance output>` | Turn the numbers into a short monthly commentary |

Requires `copilot-common` (its spreadsheet-reader profiler and document-reader do the file reading). Works well with `sticky-notes` for keeping track of invoices waiting on a query.

Reference knowledge lives in `skills/finance-reviewer/references/`. Materiality thresholds and GST treatment there are sensible defaults marked `CUSTOMISE`; tune them to the company's delegations and policies.

The reviewer flags. It does not approve, reject, post or give accounting advice beyond arithmetic and presentation.
