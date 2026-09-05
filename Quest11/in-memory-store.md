## in-memory-store

### Before you start
Every handler so far has been stateless — call it twice, get the same result. This exercise introduces a handler that actually *remembers* something between calls, which is the last piece before real persistence.

### What to build
```go
var rooms = map[int]Room{}

func AddRoomHandler(w http.ResponseWriter, r *http.Request) {

}

func ListRoomsHandler(w http.ResponseWriter, r *http.Request) {

}
```
`AddRoomHandler` decodes a `Room` from the request body and stores it in `rooms`, keyed by room number. `ListRoomsHandler` responds with all currently stored rooms as a JSON array.

**Usage:**
```go
body := strings.NewReader(`{"number": 101, "type": "Single", "price": 50}`)
addReq := httptest.NewRequest("POST", "/rooms", body)
addRec := httptest.NewRecorder()
AddRoomHandler(addRec, addReq)

listReq := httptest.NewRequest("GET", "/rooms", nil)
listRec := httptest.NewRecorder()
ListRoomsHandler(listRec, listReq)
fmt.Println(listRec.Body.String())
```
```console
[{"number":101,"type":"Single","price":50}]
```

### Watch for
A package-level `map` is shared across every request — that's the whole point here, but it also means test order matters: if a previous test added a room, it's still there for the next one. Is that a problem for how you're testing this, and if so, how do you reset state between tests?

### Stuck? Ask better
Say whether `ListRoomsHandler` returns empty (nothing was stored), returns the wrong room (key/value mismatch), or panics (concurrent map access, wrong type) — those three symptoms point at different parts of the code.

### Notions
- [maps in Go](https://go.dev/blog/maps)
