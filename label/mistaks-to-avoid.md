# Label Mistakes To Avoid

## 1. Using placeholder instead of label

### Wrong

```html
<input
  type="email"
  placeholder="Email"
>
```

### Correct

```html
<label for="email">
  Email
</label>

<input
  id="email"
  type="email"
>
```

### Why ?

```text
placeholder ≠ label
```

---

## 2. Forgetting to associate the label

### Wrong

```html
<label>Email</label>
<input id="email">
```

### Correct

```html
<label for="email">
  Email
</label>

<input id="email">
```

---

## 3. Mismatching `for` and `id`

### Wrong

```html
<label for="email">
  Email
</label>

<input id="username">
```

### Why ?

The association is broken.

---

## 4. Using duplicated ids

### Wrong

```html
<input id="email">
<input id="email">
```

### Why ?

`id` must be unique.

Labels may point to the wrong control.

---

## 5. Removing labels for design reasons

### Wrong

```html
<input type="search">
```

### Better

```html
<label for="search">
  Search
</label>

<input
  id="search"
  type="search"
>
```

---

## 6. Hiding the label with `display:none`

### Wrong

```css
label {
  display: none;
}
```

### Why ?

Screen readers may lose the accessible name.

Use a visually-hidden utility class instead.

---

## 7. Using ARIA instead of native labels

### Wrong

```html
<input
  aria-label="Email"
>
```

when a visible label can be used.

### Better

```html
<label for="email">
  Email
</label>

<input id="email">
```

### Why ?

Native HTML should be preferred whenever possible.

---

# Golden Rules

```text
placeholder ≠ label

for must match id

id must be unique

Every control should have a label.

Native labels are better than ARIA labels.
```

---

# Philosophy

```text
input
=
What the user edits.

label
=
What the user understands.
```
