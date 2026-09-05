## dom-manipulation

### Before you start
Everything up to now has been static markup. This is the first exercise where JavaScript changes what's on the page *after* it loads — which is exactly what a prompted frontend will need to do to display data from your API.

### What to build
```js
function renderRooms(rooms) {

}
```
Given an array like `[{number: 101, type: "Single"}, {number: 102, type: "Double"}]`, and an existing empty `<ul id="room-list"></ul>` in the page, `renderRooms` should add one `<li>` per room to that list, with text like `Room 101 - Single`.

### Watch for
Calling this function twice with the same data shouldn't double the list — either clear the list first, or make sure your function is only ever called once per render. Which one you choose matters for how a real page would use this.

### Stuck? Ask better
Say what `document.getElementById('room-list').innerHTML` (or equivalent) actually contains after calling your function, versus what you expected — an empty result usually means the element wasn't found or nothing was appended.

### Notions
- [DOM manipulation basics](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)
