## json-response

### Before you start
Compare this to `hello-handler` — same shape of function, but now the body isn't a plain string, it's structured data. What has to change on both ends (what you write, and what header you set) for a client to know it's receiving JSON?

### What to build
```go
type Room struct {
	Number int    `json:"number"`
	Type   string `json:"type"`
	Price  int    `json:"price"`
}

func RoomHandler(w http.ResponseWriter, r *http.Request) {

}
```
Respond with a single `Room` (any values you like) encoded as JSON, with the correct `Content-Type` header set.

**Usage:**
```go
req := httptest.NewRequest("GET", "/room", nil)
rec := httptest.NewRecorder()
RoomHandler(rec, req)
fmt.Println(rec.Header().Get("Content-Type"))
fmt.Println(rec.Body.String())
```
```console
application/json
{"number":101,"type":"Single","price":50}
```

### Watch for
The struct tags (`` `json:"number"` ``) control the field names in the output — without them, Go uses the Go field names as-is (capitalized). Check your output against the expected format carefully.

### Stuck? Ask better
Show what your actual JSON output looks like next to the expected shape above, and say specifically which part differs — field names, missing header, or malformed JSON are three different bugs.

### Notions
- [encoding/json](https://pkg.go.dev/encoding/json)
