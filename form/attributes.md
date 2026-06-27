# Form attributes

## action

### What is it?

The destination of the form data after submitting the form.

### Why does it exist?

The browser needs to know **where** the collected data should be sent.

Without `action`, the browser has no destination for the request.

---

### Values

#### URL

```html
<form action="/login">
```

Send the data to:

```text
https://example.com/login
```

---

#### Relative Path

```html
<form action="./save-user">
```

Send the data to a file or route relative to the current page.

---

#### Empty Value

```html
<form action="">
```

Submit the form to the current page URL.

---

#### Omitted

```html
<form>
```

The browser behaves exactly as if:

```html
<form action="">
```

---

### Example

```html
<form action="/search" method="GET">
  <input type="search" name="q">
  <button>Search</button>
</form>
```

After submitting:

```text
https://example.com/search?q=weather
```

---

### Notes

* `action` accepts a URL, not JavaScript.
* It cannot call a function.
* The value can be overridden by the `formaction` attribute on a submit button.
* This allows one form to submit to different URLs depending on which button is clicked.
* The `action` attribute is ignored when `method="dialog"` is used because no HTTP request is made.\
* Modern JavaScript applications often intercept the submit event using:

```js
e.preventDefault()
```

and handle the data manually.

## method

### What is it?

Defines **how** the browser sends the form data.

---

### Why does it exist?

Knowing the destination is not enough.

The browser also needs to know:

* Should the data be appended to the URL?
* Should the data be hidden inside the request body?

`method` answers this question.

---

### Values

#### GET

```html
<form method="GET">
```

The browser appends the form data to the URL.

Example:

```text
/search?q=London
```

##### Characteristics

* Visible in the URL.
* Can be bookmarked.
* Can be shared.
* Used for reading or searching data.

##### Common Use Cases

* Search forms
* Filtering
* Pagination

---

#### POST

```html
<form method="POST">
```

The browser places the data inside the request body.

##### Characteristics

* Data does not appear in the URL.
* Cannot be bookmarked.
* Better for large data.
* Commonly used when changing server state.

##### Common Use Cases

* Login forms
* Registration forms
* Upload forms
* Creating data

---

### Example

```html
<form action="/login" method="POST">
  <input type="email" name="email">
  <input type="password" name="password">
  <button>Login</button>
</form>
```

The browser sends:

```text
POST /login
```

with the form data inside the request body.

---

### Important Note

`POST` does not automatically mean:

```text
secure
```

The request should still use:

```text
HTTPS
```

to encrypt the transmitted data.

<!-- ## Name

This attribute gives the form a name that can be used to reference it from JavaScript.

If you want to take a specific form you have to give it a unique name .
But if you want more than one form you can give all of them the same name and you will take a collection of form tags .

How to taka a form by js :-
```js
// forms object
document.forms.uniqueFormName // this is the best way and more safe .

// directly from document
document.uniqueFormName

// from window object
window.uniqueFormName

// these will return a specific form tag if you specialized this name for only one form tag
// But if you gived this name for more than one tag 
// This ways will return a NodeList of a collection of form tags
``` -->

## name

This attribute gives a name to the form element.

The name can be used to reference the form from JavaScript.

### Example

```html
<form name="loginForm"></form>
```

```js
document.forms.loginForm;
document.forms["loginForm"];
```

## enctype

This attribute specifies how the browser should package (encode) the form data before sending it.

### Values

* `application/x-www-form-urlencoded`
  * Default.
  * Best for normal text data.

* `multipart/form-data`
  * Used when the form contains file inputs.
  * Sends the data in multiple parts instead of one encoded string.

* `text/plain`
  * Sends the data as plain text.
  * Mostly useful for debugging.

### Important Notes

* `enctype` only matters when `method="post"` is used.
* The value can be overridden by `formenctype` on submit buttons.

### Philosophy

```text
Data
+
Transport requirements
=
Encoding strategy
```

## novalidate

This Boolean attribute tells the browser not to run its built-in form validation before submitting.

### Important Notes

* Without this attribute, the browser validates the form automatically.
* Useful when you want to build your own validation system with JavaScript.
* Can be overridden by `formnovalidate` on submit buttons.

### Philosophy

```text
Browser validation = Default behavior.

novalidate
=
Disable validation globally.
formnovalidate
=
Disable validation for one submission only.
Default validation
+
Local override
=
Flexible submission behavior
Publish
→ Validate.

Save Draft
→ Skip validation.
novalidate
=
Should the browser validate the form before shipping the data?
```

## target

This attribute specifies where the browser should display the response after submitting the form.

### Values

* `_self`
  * Default.
  * Load the response in the current tab.

* `_blank`
  * Load the response in a new tab.

* `_parent`
  * Load the response in the parent browsing context.

* `_top`
  * Load the response in the top-level browsing context.

* `_unfencedTop`
  * Special value used inside fenced frames.

### Important Notes

* `target` does not change where the data is sent.
* It only changes where the response is displayed.
* Can be overridden by `formtarget` on submit buttons.

### Philosophy

```text
action = Where should I send the data ?

target = Where should I display the response?

Form
↓
Default display destination.

Button in form
↓
Local override of that destination.

Same request + Different display locations = target

target = The screen on which the response should appear.
```
