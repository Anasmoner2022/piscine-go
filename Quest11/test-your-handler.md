## test-your-handler

### Before you start
Every exercise so far gave you a `Usage` block showing exactly how it'd be tested. This one doesn't — you write both the handler *and* the test that proves it works. That's the actual job in Project 4: nobody hands you a test file for your own endpoint.

### What to build
Implement an endpoint that lists rooms filtered by availability:

- `GET /rooms?available=true` → returns only rooms where `available` is `true`, as a JSON array
- `GET /rooms?available=false` → returns only unavailable rooms
- `GET /rooms` (no query param) → returns all rooms

Use the same `rooms` in-memory store idea from the previous exercise (a package-level map or slice, pre-populated with a few rooms of mixed availability before your test runs).

Then write a `httptest`-based test for it that checks all three cases above.

### Watch for
"I implemented it and it looks right" isn't the same as "I tested it." If your test only checks one of the three cases, you don't actually know the other two work — write all three before considering this done.

### Stuck? Ask better
This is the one exercise where "ask better" means describing your own iteration, not just a single failure. State: what you tried first, what your test revealed was wrong, what you changed, and what the test shows now. If you're stuck on the *test* itself rather than the handler, say which of the three cases you can't figure out how to assert on.

### Notions
- [httptest](https://pkg.go.dev/net/http/httptest)
- [testing package](https://pkg.go.dev/testing)
