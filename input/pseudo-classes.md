# Input Pseudo Classes

## placeholder-shown

### what is it ?

This is a pseudo class that applies a style when the input's placeholder is shown.
<!-- This is a pseudo class that specify a style if the placeholder input is shown . -->

### Examble

```css
    input:placeholder-shown {
        border-color: gray;
    }
```

## valid and invalid pseudo classes

### what is it ?

These pseudo classes are used to style form controls based on their validation state.
<!-- This is a css pseudo class it is exist to specify a specific style for input tag . -->

If the input field is in a valid state this style will put valid state style in it by valid pseudo class .

If it is in invalid state the invalid pseudo class style will put in it .

### Example

```css
    input:invalid{
        border-color: red;
    }

    input:valid{
        border-color: green;
    }
```

### Important Notes

Using `:invalid` directly is not recommended because it may create a poor user experience.
<!-- `invalid` is not recommended as there is a UX problem it do if used normally , -->

Imagine that you have a required input as a text when the user enter the form page

```html
<input type="text" required>
```

The browser considers this input invalid as it is required and empty
<!-- this pseudo class will consider the state of this input is invalid as it is required and empty -->

so the invalid styles will be applied.
<!-- this is a bad UX as the user do not interact with the page so we use another pseudo class -->

this is a bad UX
Therefore, we usually use another pseudo class:

```text
:user-invalid
```

or use another way by a complex interacted class :

```css
    input:not(:placeholder-shown):invalid{
        border-color: red;
    }
```

This selector means:
"Apply this style to every invalid input except the one whose placeholder is currently shown."
<!-- This selector means "put this style in every invalid input except that its placeholder is shown" -->

Placeholder shown = the user has not interacted with the input yet.
<!-- placeholder shown = user is not interacted with input yet -->

## user-valid & user-invalid

These are modern versions of valid and invalid pseudo classes .

These pseudo classes apply their styles when the user interact with the form .

But those pseudo classes is a modern and have problems with older browsers may not support them .

### Examble

```css
    input:user-invalid{
        border-color: red;
    }
```

#### Best Practise

The best practise with this case is to use its two ways to support both modern and older browsers. .

```css
    input:user-invalid,
    input:not(:placeholder-shown):invalid{
        border-color: red;
    }

    input:user-valid,
    input:not(:placeholder-shown):valid{
        border-color: green;
    }
```
<!-- 
I prefer using :is(..) selector with this for best practise but using previous
way is not wrong. -->
I personally prefer using the :is() selector here for better readability,
although the previous approach is also correct.
