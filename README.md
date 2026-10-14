# Expense Tracker MCP Server

A local MCP server for recording expenses in SQLite and summarizing spending by date and category.

## Features

- Add expense entries with a date, amount, category, optional subcategory, and note.
- List expenses within a date range.
- Summarize spending by category, optionally filtered to one category.
- Read the available categories and subcategories from `categories.json`.

## Requirements

- Python 3.12 or later
- [uv](https://docs.astral.sh/uv/)

## Setup

From the project directory, install dependencies:

```powershell
uv sync
```

## Run

```powershell
uv run python main.py
```

The server creates `expenses.db` and its `expenses` table if they do not already exist.

## MCP tools

| Tool | Purpose |
| --- | --- |
| `add_expense` | Add an expense. Requires `date`, `amount`, and `category`; `subcategory` and `note` are optional. |
| `list_expenses` | List expenses between `start_date` and `end_date`, inclusive. |
| `summarize` | Sum expenses by category over an inclusive date range; optionally filter by `category`. |

Use dates in `YYYY-MM-DD` format.

## MCP resource

- `expense://categories` — returns the contents of `categories.json`.

Edit `categories.json` to change the available categories and subcategories.

## Data and privacy

Expenses are stored locally in `expenses.db`. Keep this file private if it contains personal financial information.