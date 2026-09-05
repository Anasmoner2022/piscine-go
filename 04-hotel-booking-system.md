## Project — Remote Hotel Booking System

**Team size:** 4
**Type:** Web application — Go REST API backend (hand-built) + frontend (AI-prompted, not hand-authored)

---

### Before you start (as a team)

Restate the goal out loud, all four of you: *what does a customer do, in order, from opening the app to holding a confirmed booking?* Then: *what does each step need from the server, and what does the server send back?* Write down your API's shape — endpoints, request fields, response fields — before either the backend or the frontend prompting starts. That shape is your integration contract, and this project has two consumers of it (each other's backend code, and the AI you'll prompt) so it needs to be unambiguous on paper, not just understood verbally.

### Objective

A hotel reservation system reachable over HTTP. The backend (Go) is a REST API — you write every line of it yourselves. The frontend is a real, working web UI — but instead of hand-coding it, **you build it by prompting an AI**, applying everything you've been practicing since Quest 1 without calling it that. This is where it gets a name.

### Backend — build this yourselves (Go REST API)

Core resources:
- **Rooms** — number, type, price/night, availability
- **Bookings** — guest info, room, check-in/out dates, total price, booking ID, status

Core endpoints (exact routing/naming is your team's call):
- List/view rooms, filter by availability
- Create a booking (validates dates, availability, guest info; returns a booking ID and price)
- Look up a booking by ID
- Cancel a booking (frees the room)

### Backend levels

**Level 1 — Rooms API.** Room data, types, prices, availability, endpoints to list/view them. No bookings yet.

**Level 2 — Bookings API.** Create a booking (guest info, room, dates → total price, booking ID), look it up by ID.

**Level 3 — Booking management.** Cancel a booking, update room availability accordingly, handle "booking not found," "already cancelled," "room unavailable."

**Level 4 — Persistence.** Save rooms and bookings to disk (JSON) so a server restart doesn't lose data.

**Level 5 (stretch) — Admin & extras.** Admin endpoints for managing rooms, discounts, search by guest/date. Only after 1–4 are solid.

### Backend validation to handle
Invalid room ID, unavailable room, check-out before check-in, invalid/missing booking ID, cancelling an already-cancelled booking, empty guest name — each as a real API error response, not a silent failure or a crash.

### Backend team division

| Role | Owns |
|---|---|
| **Room Management** | Room data, types, prices, availability, room endpoints |
| **Guest & Booking Management** | Booking creation, IDs, lookup, cancellation endpoints |
| **Pricing & Validation** | Nights × price calculation, date validation, availability checks, error responses |
| **Persistence & Server** | JSON storage, server wiring, routing, tying the other three together |

Same rule as every project so far: agree on paper what the JSON request/response shape is for each endpoint *before* two people start building against it independently.

---

### Frontend — build this by prompting, not by hand

Here's the twist: **you don't hand-write the frontend.** You write a prompt (or a sequence of prompts) that gets an AI to build it for you, then you run it against your real API and iterate until it actually works. The frontend can be plain HTML/CSS/JS or a simple framework — your team's call, but keep it something a prompt can realistically produce in one or two rounds.

**Each of you prompts for the piece that talks to the endpoint you built.** You know that endpoint's shape better than anyone else on the team — that's the point.

- Room Management owner → prompts for the room browsing/listing screen
- Guest & Booking Management owner → prompts for the booking form and booking-lookup screen
- Pricing & Validation owner → prompts for how prices and validation errors are displayed
- Persistence & Server owner → prompts for a simple admin/status view

### How to write the prompt

Use this shape — it's the same structure you've been using in every "Stuck? Ask better" block all piscine, just pointed forward instead of at a bug:

1. **Context** — what the app is, what this specific screen needs to do, and the *exact* request/response JSON your endpoint uses (paste a real example, not a description of one).
2. **Constraints** — tech allowed (plain HTML/CSS/JS, or whatever you agreed on), what NOT to include (no backend logic in the frontend — it only calls your API).
3. **Task** — the specific screen/feature, described concretely, not "make it nice."
4. **Expected behavior** — what should happen on success, and what should happen on each error case you built on the backend.

**Worked example**, for the Room Management owner's screen:

> Build a single HTML page with vanilla JS that lists hotel rooms from a REST API.
>
> The API returns JSON from `GET /rooms` shaped like:
> ```json
> [{"number": 101, "type": "Single", "price": 50, "available": true}]
> ```
>
> Requirements:
> - Fetch and display all rooms in a table: number, type, price/night, availability
> - Unavailable rooms should be visually distinct (e.g. greyed out), not hidden
> - No backend logic — this page only calls the API above and renders the result
> - Handle the case where the fetch fails (show an error message, don't leave a blank page)

### Iterate — don't accept the first output

The first thing the AI generates almost never matches your real API exactly, or misses one of your error cases. That's expected — the actual skill here is round two: look at what it built, compare it against what you asked for, and tell it *specifically* what's wrong (not "fix it" — say which field is missing, which case isn't handled, what the actual vs. expected behavior is). That's the same "Ask better" discipline you've used on every exercise this piscine, now aimed at an AI instead of a mentor.

### Watch for
- If your prompt doesn't include your *actual* JSON shape, the AI will invent a plausible-looking one that doesn't match your real API — and the bug you'll spend an hour on later is really a prompt-context gap from now.
- A frontend that "looks done" but was never actually run against your live backend isn't done. Every screen needs to be demoed hitting the real API, not a mocked one.
- Resist the urge to have one person prompt for the whole frontend "because it's faster." The pairing (you built the endpoint → you prompt for its UI) is what makes this exercise teach anything.

### Mentor checkpoint questions
- Walk through your endpoint's full request/response shape from memory.
- What did the AI's first attempt at your screen get wrong, and how did you tell it what to fix?
- Show the actual prompt you used — what context did you include, and what would you add if you did it again?
- What happens on your screen when the API returns an error — did you tell the AI to handle that, or did you discover it was missing?
- Could you modify your backend endpoint live, without AI or a copied solution?
