## json-decode

### Before you start
This is `json-response` in reverse — instead of encoding data to send out, you're decoding data that came in. This is exactly what "create a booking" will need in Project 4: read a JSON body, turn it into a struct you can work with.

### What to build
```go
type BookingRequest struct {
	Guest string `json:"guest"`
	Room  int    `json:"room"`
}

func BookingHandler(w http.ResponseWriter, r *http.Request) {

}
```
Read a JSON body shaped like `{"guest": "Ahmed", "room": 101}` from the request, and respond with plain text: `Booking for Ahmed, room 101`.

**Usage:**
```go
body := strings.NewReader(`{"guest": "Ahmed", "room": 101}`)
req := httptest.NewRequest("POST", "/booking", body)
rec := httptest.NewRecorder()
BookingHandler(rec, req)
fmt.Println(rec.Body.String())
```
```console
Booking for Ahmed, room 101
```

### Watch for
Decoding reads from `r.Body`, which is a stream — it can only be read once. If your decode call fails silently or your struct comes back empty, check that you're reading from the right place and that your struct's JSON tags match the incoming field names exactly.

### Stuck? Ask better
Show the exact JSON you're testing with and what your decoded struct's fields actually contain (print them before formatting the response) — that isolates whether the bug is in decoding or in how you build the response text afterward.

### Notions
- [json.NewDecoder](https://pkg.go.dev/encoding/json#NewDecoder)
