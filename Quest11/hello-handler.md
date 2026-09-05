## hello-handler

### Before you start
This is your first web-facing Go code. In one sentence: what's the difference between a normal function you call yourself, and a function the Go HTTP server calls *for you* whenever a request comes in?

### What to build
```go
func HelloHandler(w http.ResponseWriter, r *http.Request) {

}
```
Write a handler that responds with the plain text `Hello, piscine!` whenever it's called.

**Usage** (tested via `httptest`, not a live server):
```go
req := httptest.NewRequest("GET", "/hello", nil)
rec := httptest.NewRecorder()
HelloHandler(rec, req)
fmt.Println(rec.Body.String())
```
```console
Hello, piscine!
```

### Watch for
`http.ResponseWriter` isn't something you `return` from — you write directly to it, and the response is whatever ends up written by the time your function returns. What Go function writes a string to something that implements `io.Writer`?

### Stuck? Ask better
Say exactly what you tried (which function you used to write the response), what `rec.Body.String()` actually printed, and what you expected instead. If the body is empty, that's a sign nothing was written to `w` at all — different problem than wrong text being written.

### Notions
- [net/http](https://pkg.go.dev/net/http)
- [httptest](https://pkg.go.dev/net/http/httptest)
