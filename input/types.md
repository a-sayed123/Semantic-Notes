# Type Values

## Values

### `text`

#### What is it ?

The default input type.

Used to collect short free-form text from the user.

```html
<input type="text">
```

#### Browser behavior

* Single-line text field.
* Supports text selection, copy, cut, and paste.
* Pressing `Enter` may submit the form.
* Shows the normal keyboard on mobile devices.

#### Validation

No built-in validation.

You must add constraints yourself:

```html
required
minlength
maxlength
pattern
```

#### Accessibility

Implicit role:

```text
textbox
```

Should almost always have:

```html
<label>
```

#### Common Use Cases

* Name
* City
* Username
* Search term (if search semantics are not needed)

#### Important Notes

```text
<input> = <input type="text">
```

This is the default behavior.

---

### `email`

#### What is it ?

Used to collect email addresses.

```html
<input type="email">
```

#### Browser behavior

* Displays an email keyboard on mobile devices.
* Offers autofill from saved email addresses.
* Provides built-in validation.

#### Validation

The browser checks:

```text
something@something
```

The validation is intentionally simple and not perfect.

#### Attributes commonly used with it

```html
required
multiple
autocomplete="email"
```

#### Accessibility

Implicit role:

```text
textbox
```

Screen readers announce it as:

```text
Email edit text.
```

#### Common Use Cases

* Login
* Registration
* Contact forms

#### Important Notes

```text
Client-side validation:
≠
Security
```

Always validate again on the server.

---

### `password`

#### What is it ?

Used for secret text.

```html
<input type="password">
```

#### Browser behavior

* Masks characters.
* Integrates with password managers.
* Supports autofill.
* May offer password generation.

#### Validation

No special validation.

Use:

```html
required
minlength
maxlength
pattern
```

#### Accessibility

Implicit role:

```text
textbox
```

Screen readers usually announce:

```text
Password edit text.
```

#### Important Attributes

```html
autocomplete="current-password"
autocomplete="new-password"
```

#### Common Use Cases

* Login
* Sign up
* Change password

#### Important Notes

Never attempt to implement your own password masking logic.

Let the browser handle it.

---

### `search`

#### What is it ?

A specialized text field for search operations.

```html
<input type="search">
```

#### Browser behavior

Some browsers provide:

* clear button
* search styling
* search keyboard on mobile

#### Validation

No special validation.

#### Accessibility

Implicit role:

```text
searchbox
```

This is one of the reasons to prefer it over:

```html
<input type="text">
```

for search interfaces.

#### Common Use Cases

* Site search
* Product search
* Filter inputs

#### Philosophy

```text
search
=
text
+
search semantics
```

---

### `checkbox`

#### What is it ?

Represents a binary choice.

```html
<input type="checkbox">
```

#### States

```text
checked
unchecked
indeterminate
```

#### Browser behavior

* Space toggles the checkbox.
* Clicking its label toggles it.

#### Form Submission

Very important:

A checkbox submits data only when checked.

If unchecked:

```text
Nothing is submitted.
```

#### Accessibility

Implicit role:

```text
checkbox
```

Screen readers announce:

```text
Checked.
Not checked.
```

#### Important Attributes

```html
checked
required
```

#### Common Use Cases

* Accept terms
* Preferences
* Settings
* Multiple selections

#### Important Notes

The third state:

```text
indeterminate
```

can only be set via JavaScript.

---

### `radio`

#### What is it ?

Represents one choice from a group.

```html
<input type="radio">
```

#### Browser behavior

Radio buttons become a group when they share:

```html
name=""
```

Example:

```html
<input type="radio" name="theme">
<input type="radio" name="theme">
<input type="radio" name="theme">
```

Only one can be selected.

#### Keyboard Behavior

* Tab enters the group.
* Arrow keys move between choices.

#### Form Submission

Only the selected radio button is submitted.

#### Accessibility

Implicit role:

```text
radio
```

The entire group behaves like:

```text
radiogroup
```

#### Common Use Cases

* Gender
* Payment method
* Theme selection

#### Philosophy

```text
checkbox
=
many choices

radio
=
one choice
```

---

### `file`

#### What is it ?

Used to upload files.

```html
<input type="file">
```

#### Browser behavior

Opens the operating system file picker.

#### Form Submission

Usually requires:

```html
enctype="multipart/form-data"
```

#### Important Attributes

```html
accept
multiple
capture
```

#### Security

JavaScript cannot set:

```js
input.value = "C:\\secret.txt";
```

Browsers intentionally block this.

#### Accessibility

Implicit role:

```text
button
```

combined with file selection semantics.

#### Common Use Cases

* Profile picture
* Resume upload
* Attachments

#### Important Notes

The selected files are available through:

```js
input.files
```

not:

```js
input.value
```

---

### `hidden`

#### What is it ?

Invisible input.

```html
<input type="hidden">
```

#### Browser behavior

* Cannot receive focus.
* Not visible.
* Submitted with the form.

#### Common Use Cases

* IDs
* Tokens
* State information

#### Important Notes


```text
Hidden ≠ Secure
```

The user can still inspect and modify it.

Never trust hidden input values.

---

### `submit`

#### What is it ?

A button that submits the form.

```html
<input type="submit">
```

#### Browser behavior

Triggers the entire form submission pipeline:

```text
Validation
↓
Collect controls
↓
Encode
↓
Send
↓
Display response
```

#### Accessibility

Implicit role:

```text
button
```

#### Important Attributes

```html
formaction
formmethod
formenctype
formtarget
formnovalidate
```

#### Common Use Cases

* Login
* Registration
* Search
* Save

#### Important Notes

Today most developers prefer:

```html
<button type="submit">
```

because it is more flexible.

#### Philosophy

```text
submit
=
Start the form submission pipeline.
```
