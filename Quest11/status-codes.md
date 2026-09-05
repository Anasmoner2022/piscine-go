## status-codes

### Before you start
Every handler you've written so far has silently returned `200 OK` by default. Real APIs communicate success/failure through the status code itself, not just the body text — this is exactly what Project 4's validation requirements need.

### What to build
```go
func ValidateBookingHandler(w http.ResponseWriter, r *http.Request) {

}
```
Decode a `BookingRequest` (same shape as `json-decode`) from the body. Respond:
- `400 Bad Request` with body `invalid guest name` if `Guest` is empty
- `400 Bad Request` with body `invalid room number` if `Room` is `0` or negative
- `200 OK` with body `booking valid` otherwise

**Usage:**
```go
body := strings.NewReader(`{"guest": "", "room": 101}`)
req := httptest.NewRequest("POST", "/validate", body)
rec := httptest.NewRecorder()
ValidateBookingHandler(rec, req)
fmt.Println(rec.Code)
fmt.Println(rec.Body.String())
```
```console
400
invalid guest name
```

### Watch for
The status code has to be set *before* you write the body — writing the body first locks the status code to whatever the default was. Check the order of your operations if the code isn't matching what you expect.

### Stuck? Ask better
Say which of the three cases (empty guest, invalid room, valid booking) is producing the wrong status code or body — and show the order in which your code sets the status vs. writes the body.

### Notions
- [WriteHeader](https://pkg.go.dev/net/http#ResponseWriter)
