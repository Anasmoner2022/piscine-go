## css-box-model

### Before you start
This is the exercise that makes "the AI's CSS looks off" something you can actually diagnose instead of just feeling. Padding, border, and margin each do a different job — mixing them up is one of the most common issues in generated CSS.

### What to build
Given this HTML:
```html
<div class="room-card">Room 101</div>
```
Write CSS so that `.room-card`:
- has `20px` of space *inside* the border, between the border and the text
- has a `2px solid` border
- has `10px` of space *outside* the border, separating it from neighboring elements

### Watch for
All three of those map to specific, different CSS properties. If you set the wrong one, the element might look visually close to correct but fail an exact check.

### Stuck? Ask better
Say which of the three spacing requirements (inside, border, outside) doesn't match, and paste your `.room-card` rule.

### Notions
- [CSS box model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model)
