## route-params

### Before you start
So far your handlers ignore `r *http.Request` entirely. This exercise is about actually reading something out of it — specifically, a value the client put in the URL.

### What to build
```go
func RoomLookupHandler(w http.ResponseWriter, r *http.Request) {

}
```
Read a room number from the query string (`/room?number=101`) and respond with plain text confirming it, e.g. `Looking up room 101`. If `number` is missing, respond with `missing room number` instead.

**Usage:**
```go
req := httptest.NewRequest("GET", "/room?number=101", nil)
rec := httptest.NewRecorder()
RoomLookupHandler(rec, req)
fmt.Println(rec.Body.String())
```
```console
Looking up room 101
```

### Watch for
Query parameters always come back as strings, even if the value looks numeric — do you need to convert it, or is string comparison enough for what this exercise asks?

### Stuck? Ask better
Say what you tried to read the query value (which function/method), what it returned, and whether the "missing" case works correctly too — a fix that only handles the happy path isn't done.

### Notions
- [URL.Query](https://pkg.go.dev/net/url#URL.Query)
