# Form Semantic & Accessibility

## Semantic

```text
<form>
=
A semantic region for collecting and submitting user data.
```

---

## Implicit ARIA Role

```text
form
```

A form landmark should have an accessible name:

```html
<form aria-label="Search Form">
```

or

```html
<form aria-labelledby="heading-id">
```

---

## Default Behavior

```text
Submit
↓
Validation
↓
Collect successful controls
↓
Encode data
↓
Send request
↓
Display response
```

---

## Accessibility Goals

```text
Discoverable
Understandable
Operable
Recoverable
```

---

## Philosophy

```text
<form>
=
A configurable request pipeline
for collecting and submitting user data.
```
