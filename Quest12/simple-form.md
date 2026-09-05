## simple-form

### What to build
Create `booking-form.html` with a `<form>` containing:
- a text input named `guest`
- a number input named `room`
- a date input named `checkin`
- a date input named `checkout`
- a submit button

The `name` attributes matter more than anything else here — that's what a server (or a grader) reads to know which field is which.

### Watch for
An `<input>` without a `name` attribute won't be submitted as part of the form data at all — it'll render fine and still fail grading. Double-check every input has one.

### Stuck? Ask better
Show your `<form>` block and say which field the grader says is missing — check that field's `name` attribute character-for-character against the spec above.

### Notions
- [HTML forms](https://developer.mozilla.org/en-US/docs/Learn/Forms)
