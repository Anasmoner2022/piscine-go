## handle-fetch-error

### Before you start
This is the exercise that directly rehearses a "Watch for" from Project 4: a frontend that only handles the success case isn't done. Real APIs fail — bad requests, server errors, network drops — and a page that goes blank or breaks when that happens is a real bug, not an edge case.

### What to build
```js
function loadRoomsSafely() {

}
```
Same as `loadRooms`, but: if the fetch fails (network error) or the response isn't ok (e.g. a 500 status), display the text `Failed to load rooms` inside an element with id `error-message`, instead of rendering a room list.

**Usage** (grader tests both a success and a failure case):
```js
// failure case
global.fetch = () => Promise.reject(new Error("network error"));
loadRoomsSafely().then(() => {
  console.log(document.getElementById('error-message').textContent);
});
```
```console
Failed to load rooms
```

### Watch for
There are two different kinds of failure here: the network call itself rejecting (`fetch` throws), and the network call succeeding but returning an error status (`response.ok` is `false`). Does your solution handle both, or just one?

### Stuck? Ask better
Say which failure mode you tested (rejected fetch, or a bad status code) and whether the error message appeared, didn't appear, or the room list rendered incorrectly instead — describe your own iteration: what you tried first, what that revealed, what you changed.

### Notions
- [fetch error handling](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API#checking_that_the_fetch_was_successful)
