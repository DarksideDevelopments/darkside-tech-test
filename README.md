# Junior Web Developer — Technical Take-Home Task

| | |
|---|---|
| **Time allowance** | 2–3 hours (please don't spend significantly more) |
| **Submission** | Send a link to a public GitHub repository, or a ZIP file by email |
| **Tech stack** | PHP / Laravel for the backend & plain HTML/CSS/JS or Vue.js for the frontend |
| **Prerequisites** | PHP 8+, Composer, and Node/npm installed locally |

---

## Overview

You've been asked to build a small internal tool called the **Order Note Board**. It is a single-page web application that lets a warehouse team leave short notes against order numbers, for example flagging a packaging issue or a priority rush job.

This task is intentionally small in scope. We are not looking for perfection; we want to see how you approach a problem, structure your code, and communicate what you have built.

---

## What to Build

### Backend (Laravel)

Create a Laravel application with a single notes resource. The application should:

- Provide a RESTful API endpoint to create a new note (`POST /api/notes`)
- Provide an endpoint to retrieve all notes (`GET /api/notes`)
- Store notes in a database using a migration and an Eloquent model

Each note should have at minimum:

| Field | Type | Notes |
|---|---|---|
| `order_number` | string | Required. E.g. "ORD-1042" |
| `message` | text | Required. The note content. |
| `author` | string | Required. Name of the person leaving the note. |
| `created_at` | timestamp | Auto-managed by Laravel. |

### Frontend

Build a simple single-page interface (in the same Laravel project, or as a standalone page) that:

- Displays all existing notes in a list, showing the order number, author, message, and time posted
- Includes a small form to submit a new note (order number, author name, and message fields)
- Updates the list after a new note is submitted, without a full page reload

> **Plain HTML/JS** is absolutely fine. Vue.js is a bonus, not a requirement.

---

## Optional Extras

If you have time and want to show more, any of the following would impress us, but none are required:

- Basic validation on the API (return a meaningful error if fields are missing)
- A simple filter or search on the frontend (e.g. filter notes by order number)
- Any use of a Vue.js component for the note list or form
- A brief README explaining how to run the project locally

---

## What We Are Looking For

| Area | What a good submission looks like |
|---|---|
| Code structure | Logical file and folder organisation; sensible naming |
| Laravel basics | Correct use of routes, controller, migration, and model |
| API design | Clean JSON responses; appropriate HTTP status codes |
| Frontend | Functional form and list; no need for it to look polished |
| Problem solving | Evidence of thinking through the task rather than copying boilerplate |
| Communication | A README or code comments that briefly explain decisions made |

---

## Submitting Your Work

1. Push your code to a public GitHub repository, or package it into a ZIP file.
2. Include a short README with setup instructions (even just the standard Laravel steps).
3. Reply to your application email with the link or attachment.
4. If anything is incomplete, include a note explaining what you ran out of time on and how you would have approached it.

We appreciate the time you've put in. Good luck, we look forward to seeing what you build!

---

## Quick-Start Reference

If you need a reminder of the standard Laravel setup steps:

```bash
composer create-project laravel/laravel order-note-board
cd order-note-board
cp .env.example .env && php artisan key:generate
# Edit .env with your DB credentials, then:
php artisan migrate
php artisan serve
```

> **SQLite tip:** If you don't have MySQL set up locally, SQLite is the easiest option. Set `DB_CONNECTION=sqlite` in your `.env` and create a blank `database/database.sqlite` file.
