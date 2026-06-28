# Input Mistakes To Avoid

## 1. Using `placeholder` instead of `<label>`

### Wrong

```html
<input type="email" placeholder="Email">
```

### Correct

```html
<label for="email">Email</label>
<input id="email" type="email">
```

### Why ?

`placeholder` is only a temporary hint.

It disappears when the user starts typing and may not be announced correctly by assistive technologies.

---

## 2. Forgetting the `name` attribute

### Wrong

```html
<input type="email">
```

### Correct

```html
<input
  type="email"
  name="email"
>
```

### Why ?

Without `name`, the input value is not submitted.

---

## 3. Using `disabled` when you need `readonly`

### Wrong

```html
<input
  value="ahmed@gmail.com"
  disabled
>
```

### Correct

```html
<input
  value="ahmed@gmail.com"
  readonly
>
```

### Why ?

`disabled` inputs are not submitted with the form.

`readonly` inputs are submitted.

---

## 4. Using `hidden` for security

### Wrong

```html
<input
  type="hidden"
  value="isAdmin=true"
>
```

### Why ?

Hidden inputs are invisible, not secure.

The user can still inspect and modify them.

Never trust hidden values.

---

## 5. Adding ARIA that native HTML already provides

### Wrong

```html
<input
  type="checkbox"
  aria-checked="true"
>
```

### Correct

```html
<input
  type="checkbox"
  checked
>
```

### Why ?

Native HTML semantics are better than ARIA.

---

## 6. Using `aria-required` instead of `required`

### Wrong

```html
<input aria-required="true">
```

### Correct

```html
<input required>
```

### Why ?

`required` provides:

* semantics
* validation
* accessibility

---

## 7. Using `aria-disabled` instead of `disabled`

### Wrong

```html
<input aria-disabled="true">
```

### Correct

```html
<input disabled>
```

### Why ?

`aria-disabled` only announces the state.

The control is still focusable and usable unless you disable it yourself.

---

## 8. Using `type="text"` for everything

### Wrong

```html
<input type="text">
```

for email, password, search, telephone, etc.

### Correct

```html
<input type="email">
<input type="password">
<input type="search">
<input type="tel">
```

### Why ?

Correct types provide:

* better accessibility
* better validation
* better mobile keyboards
* better autofill

---

## 9. Forgetting `autocomplete`

### Wrong

```html
<input type="email">
```

### Better

```html
<input
  type="email"
  autocomplete="email"
>
```

### Why ?

Improves:

* password managers
* autofill
* cognitive accessibility

---

## 10. Not explaining input constraints

### Wrong

```html
<input
  type="password"
  minlength="8"
>
```

### Better

```html
<input
  type="password"
  minlength="8"
  aria-describedby="rules"
>

<p id="rules">
  Password must contain at least 8 characters.
</p>
```

### Why ?

Users and screen readers need to know the rules.

---

## 11. Styling `:invalid` immediately

### Wrong

```css
input:invalid {
  border-color: red;
}
```

### Why ?

The field becomes red before the user even interacts with it.

Bad UX.

### Better

```css
input:user-invalid {
  border-color: red;
}
```

or

```css
input:not(:placeholder-shown):invalid {
  border-color: red;
}
```

---

## 12. Using `autofocus` everywhere

### Why ?

Unexpected focus movement may:

* confuse screen reader users
* cause accidental keyboard input
* create poor UX

Use it only when there is a strong reason.

---

## 13. Relying on client-side validation for security

### Wrong

```text
The browser validated the form,
therefore the data is safe.
```

### Why ?

Users can:

* disable JavaScript
* edit HTML
* send requests manually

Always validate on the server.

---

## 14. Assuming `type="file"` protects uploads

### Wrong

```html
<input
  type="file"
  accept=".png"
>
```

### Why ?

`accept` is only a hint.

The server must still validate:

* file type
* file size
* file contents

---

## 15. Using `placeholder` as instructions

### Wrong

```html
<input placeholder="Password must contain 8 characters and one symbol">
```

### Better

```html
<p id="rules">
  Password must contain 8 characters and one symbol.
</p>

<input aria-describedby="rules">
```

### Why ?

Instructions should remain visible.

---

# Golden Rules

```text
label ≠ placeholder

hidden ≠ secure

disabled ≠ readonly

client validation ≠ security

ARIA does not replace native HTML.

Prefer native semantics whenever possible.
```
