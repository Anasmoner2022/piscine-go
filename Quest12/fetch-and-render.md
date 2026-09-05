## fetch-and-render

### Before you start
This combines `dom-manipulation` with actually asking a server for data. In grading (and in this exercise), `fetch` is replaced with a fake version that returns canned JSON — no real network call happens, but your code doesn't know the difference, which is the whole point.

### What to build
```js
function loadRooms() {

}
```
Call `fetch('/rooms')`, parse the JSON response, and pass the result into `renderRooms` (from the previous exercise) to display it.

**Usage** (fake `fetch` provided by the grader):
```js
global.fetch = () => Promise.resolve({
  json: () => Promise.resolve([{number: 101, type: "Single"}])
});
loadRooms().then(() => {
  console.log(document.getElementById('room-list').innerHTML);
});
```

### Watch for
`fetch` is asynchronous — your function needs to wait for both the fetch *and* the `.json()` parsing to finish before rendering. If `renderRooms` runs with `undefined`, that's usually a missed `await` or an unreturned promise.

### Stuck? Ask better
Show your function and say whether it fails immediately (fetch itself), after fetch but before rendering (the `.json()` step), or renders with wrong/empty data (the render step) — those are three different places to look.

### Notions
- [fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)
- [async/await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)
