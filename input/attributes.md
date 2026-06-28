# Input attributes

## Type

This attribute specifies the behavior and purpose of the input element.

The `type` attribute changes:

* browser behavior
* validation rules
* keyboard layout on mobile devices
* accessibility semantics
* submitted data format
* built-in browser features

---

### Syntax

```html
<input type="text">
```

---

### Default Value

```html
<input>
```

is equivalent to:

```html
<input type="text">
```

---

### Philosophy

```text
<input> = Input engine.

type = Configuration of that engine.
```

or

```text
One element + Different behaviors =  Different input types.
```
---

### Why does it exist ?

Without `type`, the browser would need:

```html
<input type="text" >
<input type="email" >
<input type="password" >
<input type="date" >
<input type="file" >
...
```

Instead, HTML provides:

```html
<input type="...">
```

This makes the input element highly configurable.

---

### What does `type` change ?

#### Validation

```html
<input type="email">
```

adds:

```text
Built-in email validation.
```

---

#### Browser UI

```html
<input type="date">
```

may display:

```text
Calendar picker.
```

---

#### Mobile Keyboard

```html
<input type="tel">
```

may open:

```text
Phone keypad.
```

---

#### Accessibility

```html
<input type="checkbox">
```

has different semantics from:

```html
<input type="text">
```

Screen readers announce them differently.

---

#### Form Submission

```html
<input type="file">
```

submits a file.

```html
<input type="checkbox">
```

submits only when checked.

---

### Most Important Types

### Text Inputs

```text
text
email
password
search
tel
url
number
```

---

#### Selection Inputs

```text
checkbox
radio
```

---

#### File Inputs

```text
file
```

---

#### Form Control Inputs

```text
hidden
submit
button
reset
```

---

#### Specialized Inputs

```text
date
time
datetime-local
range
color
month
week
```

---

### Best Practice

Choose the most specific type possible.

Good:

```html
<input type="email">
```

Bad:

```html
<input type="text">
```

for email addresses.

The browser can only help the user if it knows what kind of data is expected.

---

### Philosophy Summary

```text
type
=
Tell the browser:

- what the user is entering
- how to help the user
- how to validate the data
- how to expose the control to accessibility tools
- how to behave
```

or simply:

```text
type
=
The personality of the input element.

<input> is the engine.
type is the configuration file.
```

## Important Attributes

### `name`

#### What is it ?

Specifies the name of the input when the form is submitted.

#### Works With

Almost all input types except image .

#### Accessibility

No direct accessibility impact.

It does not replace:

```html
<label>
```

#### Important Notes

Without:

```html
name=""
```

the input value is not submitted.

---

### `value`

#### What is it ?

Specifies the current value of the input.

#### Works With

Almost all input types.

#### Special Cases

```text
checkbox → submitted value.
radio → selected value.
file → do not rely on it.
```

#### Accessibility

No direct accessibility impact.

---

### `placeholder`

#### What is it ?

Provides a temporary hint to the user.

#### Works With

```text
text
email
password
search
tel
url
number
```

#### Accessibility

```text
placeholder ≠ label
```

Never use it instead of:

```html
<label>
```

because it disappears and may not be announced properly.

---

### `required`

#### What is it ?

Makes the input mandatory.

#### Works With

Most input types.

#### Accessibility

Excellent support.

Screen readers usually announce:

```text
Required.
```

Prefer:

```html
required
```

over:

```html
aria-required
```

---

### `disabled`

#### What is it ?

Disables the input.

#### Works With

Almost all input types.

#### Browser Behavior

* cannot receive focus
* cannot be edited
* is not submitted
* is ignored by validation

#### Accessibility

Screen readers announce:

```text
Disabled.
Unavailable.
```

Prefer:

```html
disabled
```

over:

```html
aria-disabled
```

---

### `readonly`

#### What is it ?

Makes the input read-only.

#### Works With

```text
text
email
password
search
tel
url
number
```

#### Browser Behavior

* can receive focus
* is submitted
* cannot be edited

#### Accessibility

Screen readers announce:

```text
Read only.
```

---

### `autocomplete`

#### What is it ?

Gives semantic meaning to the input data and enables autofill.

#### Works With

Especially:

```text
text
email
password
tel
```

#### Examples

```html
autocomplete="name"
autocomplete="email"
autocomplete="username"
autocomplete="current-password"
autocomplete="new-password"
```

#### Accessibility

Very important.

Helps:

* password managers
* autofill
* cognitive accessibility

---

### `inputmode`

#### What is it ?

Hints which keyboard should appear on mobile devices.

#### Works With

Text-like inputs.

#### Examples

```html
inputmode="numeric"
inputmode="decimal"
inputmode="tel"
inputmode="email"
```

#### Accessibility

Improves mobile accessibility and reduces typing effort.

---

### `minlength` / `maxlength`

#### What is it ?

Sets the minimum and maximum number of characters.

#### Works With

Text-like inputs.

#### Accessibility

Good practice:

```html
aria-describedby
```

to explain the constraints.

---

### `min` / `max`

#### What is it ?

Defines the minimum and maximum values.

#### Works With

```text
number
date
range
time
datetime-local
```

#### Accessibility

No direct accessibility impact.

---

### `step`

#### What is it ?

Defines the allowed increments.

#### Works With

```text
number
date
time
range
datetime-local
```

#### Accessibility

Improves keyboard and screen-reader value adjustments.

---

### `pattern`

#### What is it ?

Provides a regular expression that the value must match.

#### Works With

Text-like inputs.

#### Accessibility

Always explain the pattern using:

```html
aria-describedby
```

because screen readers do not automatically explain the regex.

---

### `checked`

#### What is it ?

Specifies the selected state.

#### Works With

```text
checkbox
radio
```

#### Accessibility

Native support already exists.

Do not use:

```html
aria-checked
```

unless you are building a custom widget.

---

### `multiple`

#### What is it ?

Allows multiple values.

#### Works With

```text
email
file
```

#### Accessibility

Good practice:

```html
aria-describedby
```

to inform the user that multiple values are allowed.

---

### `accept`

#### What is it ?

Specifies allowed file types.

#### Works With

```text
file
```

#### Accessibility

No direct accessibility impact.

Good practice:

Explain file restrictions in visible text and connect it with:

```html
aria-describedby
```

---

### `autofocus`

#### What is it ?

Automatically focuses the input when the page loads.

#### Works With

Most input types.

#### Accessibility

Use carefully.

Unexpected focus movement may confuse screen reader users.

---

### `enterkeyhint`

#### What is it ?

Changes the Enter key label on mobile keyboards.

#### Examples

```html
enterkeyhint="search"
enterkeyhint="send"
enterkeyhint="next"
```

#### Accessibility

Improves mobile user experience.

---

### `spellcheck`

#### What is it ?

Enables or disables spell checking.

#### Works With

Text-like inputs.

#### Good Use Cases

```text
spellcheck="false"
```

for:

* usernames
* passwords
* code

---

### `autocapitalize`

#### What is it ?

Controls automatic capitalization on mobile devices.

#### Works With

Text-like inputs.

#### Examples

```html
autocapitalize="words"
autocapitalize="sentences"
autocapitalize="off"
```

#### Accessibility

Improves typing experience on mobile devices.

#### important notes 

```text
readonly
=
The user can see the field and focus it,
but cannot modify it.

disabled
=
The field is temporarily unavailable.

hidden
=
The field does not participate in the UI at all.
```

```text
readonly
=
Visible
+
Submittable
+
Not editable
```

```text
disabled
=
Visible
+
Not usable
+
Not submittable
```

```text
hidden
=
Not visible
+
Submittable
+
For developers
```

```text
readonly:
"You may see and carry this information."

disabled:
"This information is temporarily out of service."

hidden:
"The user was never invited to this conversation."
```

```text
readonly → awake but stubborn.

disabled → sleeping.

hidden → not in the room.
```
