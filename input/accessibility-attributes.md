### Accessibility Attributes

Most input types do not need extra ARIA because native HTML already provides their semantics.

Useful attributes:

* aria-label
* aria-labelledby
* aria-describedby
* aria-invalid
* aria-errormessage

Prefer native attributes when possible:

* required > aria-required
* disabled > aria-disabled
* checked > aria-checked

Important non-ARIA accessibility attributes:

* autocomplete
* inputmode
* enterkeyhint
* spellcheck
* autocapitalize

### Important Notes
```text
If HTML already knows how to describe itself,
don't replace it with ARIA.

Native first.
ARIA second.
```
