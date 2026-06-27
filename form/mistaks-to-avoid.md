# Form Mistakes To Avoid

## 1. Using GET for sensitive data

```html
<form method="get">
```

Do not use GET for:

* passwords
* tokens
* private information

because the data becomes part of the URL.

---

## 2. Forgetting the `name` attribute

```html
<input type="email">
```

Without `name`, the field data is not submitted.

---

## 3. Using `multipart/form-data` without file inputs

```html
<form enctype="multipart/form-data">
```

This encoding should only be used when files need to be uploaded.

---

## 4. Forgetting `multipart/form-data` with file inputs

```html
<input type="file">
```

Without:

```html
enctype="multipart/form-data"
```

the file will not be uploaded correctly.

---

## 5. Disabling validation without having another validation system

```html
<form novalidate>
```

Only use `novalidate` when you provide your own validation.

---

## 6. Depending only on client-side validation

HTML validation improves UX but is not security.

All data must be validated again on the server.

---

## 7. Relying on `window.formName`

```js
window.loginForm
```

This is legacy behavior.

Prefer:

```js
document.forms.loginForm
```

or:

```js
document.querySelector()
```

---

## 8. Creating multiple forms when one form with overrides is enough

Bad:

```text
Duplicate forms.
```

Better:

```text
One form
+
formaction
formmethod
formenctype
formtarget
formnovalidate
```

---

## 9. Using `_blank` without understanding its security implications

Opening a new tab can create security issues if `window.opener` is available.

---

## 10. Thinking that HTML validation is security

```text
Validation
≠
Security
```

HTML validation exists mainly for:

* user experience
* convenience

**Never trust user input.**
