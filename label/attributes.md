# Label Attributes

## `for`

### What is it ?

This attribute specifies which form control this label describes.

The value of `for` must be equal to the `id` of a form control.

### Example

```html
<label for="email">Email</label>
<input id="email" type="email">
```

---

### Why do we use it ?

Without this connection:

* Screen readers may not know the name of the input.
* Clicking the label will not focus the input.
* The form becomes less accessible.

---

### Browser Behavior

Clicking the label:

```text
moves focus to its control.
```

For:

```html
<input type="checkbox">
<input type="radio">
```

Clicking the label also toggles the control.

---

### Accessibility

This is one of the most important accessibility attributes in forms.

It creates the accessible name of the control.

Example:

```html
<label for="email">Email Address</label>
<input id="email" type="email">
```

Screen readers announce:

```text
Email Address, email edit text.
```

---

### Important Notes

The value of `for` must reference an existing `id`.

```html
<label for="email">Email</label>
<input id="username">
```

This is broken.

---

## Implicit Label Association

Instead of:

```html
<label for="email">Email</label>
<input id="email">
```

You can write:

```html
<label>
  Email
  <input type="email">
</label>
```

This is called:

```text
Implicit Association
```

because the input is inside the label.

---

### Which way is better ?

Both are valid.

But explicit association:

```html
<label for="email">
<input id="email">
```

is usually preferred because:

* easier styling
* easier layout control
* easier JavaScript targeting
* works better with complex forms

---

# Accessibility Notes

Every form control should have:

```text
A visible label.
```

Avoid:

```html
<input placeholder="Email">
```

because:

```text
placeholder ≠ label
```

---

# Semantic Meaning

`<label>` does not add visual styles.

Its job is:

```text
Describe a form control
+
Provide its accessible name
+
Increase click area.
```

---

# Philosophy

```text
input
=
The control.

label
=
The control's identity.
```

Without a label, the control exists but the user may not know what it means.
