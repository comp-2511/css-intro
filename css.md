# CSS
CSS is all about adding styles and layout to a webpage.

---

## Rules
CSS uses rules to add styles to a document. A set of rules is called a stylesheet.

Rule examples:
```css
h1 {color: blue;}
body {background: red;}
```

---

### Rule Structure
Each rule has two main parts:
1. Selector
1. Declaration Block

The selector tells the browser which HTML elements to select for apply the rule.

The declaration block contains one or more declarations. Declarations are separated by `;`.

Each declaration is a pair of a CSS property and a value.

---

## Whitespace
CSS is **almost** insensitive to whitespace. All the following are OK:

```css
p{color:red;}

p {
    color:red;
}

p   {color  :   red;}
```

---

## Comments
CSS allows for comments. They're very similar to comments in languages like C++ or Go:

```css
/* This is a CSS comment */

/* This is a multiline
CSS comment. */
```

---

## Connecting CSS to HTML (method 1)
Using the `<link>` tag that goes inside the `<head>` tag.

```html
<link rel="stylesheet" href="mystyle.css" />
```

This is referred to as External CSS as the stylesheet is defined in a file external to the HTML document importing it.

You can link multiple CSS files to an HTML document.

---

## Connecting CSS to HTML (method 2)
Using the `<style>` tag which goes inside the `<head>` tag.

```html
<head>
    <style>
        body {background-color:#f1f1f1;}
        p {text-align: center;}
    </style>
</head>
```

This is referred to as Internal or Embedded CSS.

---

## Connecting CSS to HTML (method 3)
Using the `style` attribute inside an element:

```html
<p style="text-align:center">This is a test</p>
```

This is referred to as Inline CSS.

---

## Conflicts; who wins?
In case of conflicts, the closest rule wins. In other words, 

1. Inline wins over
1. Internal (or embedded); which in turn wins over
1. External

---

## Selectors
As mentioned earlier, each CSS Rule contains a selector and a declaration block. The selector shows which part of the HTML document needs to be selected.

---

### Type Selector
Also knows as an element selector, is basically an HTML element.

```css
html {color: black;}
h1 {color: gray;}
h2 {color: silver;}
```

---

#### Grouping
Sometimes you want to apply the same styles to multiple selectors. You can use grouping for that.

The followings have the same effect:

```css
h1 { color: red; }
h2 { color: red; }
```

or:

```css
h1, h2 { color: red; }
```

---

### Class & ID Selectors
In addition to type selectors, CSS has class selectors and ID selectors, which let you assign styles based on HTML attributes but independent of element type.

---

#### Class Selector
The class selector works by directly referencing a value that will be found in the class attribute of an element. This reference is always preceded by a period (`.`), which marks it as a class selector.

```css
p.success {color: green;}
```

Class values are case-sensitive in HTML.

---

#### Multiple Classes
You can select elements that have multiple classes.

```css
p.success.notification {
    color: green;
    border: 1px solid silver;
}
```

---

### ID Selector
The ID selector is similar to the class selector, except that an HTML document should not have more than one elements with the same id.

```css
p#main-para {
    font-weight: bold;
}
```

ID values are case-sensitive in HTML.

---

### Attribute Selector
Attribute selector is based on HTML attributes connected to HTML elements. There are four general types of attribute selector.

1. Simple Attribute
1. Exact Attribute Value
1. Partial-match Attribute Value
1. Leading-value Attribute

---

#### Simple Attribute Selector
If you want to select elements that have a certain attribute, regardless of that attribute's value, you can use a simple attribute selector.

```css
h1[class] {color: silver;}
img[alt] {outline: 3px solid forestgreen;}
a[href][title] {font-weight: bold;}
```

---

#### Exact Attribute Value Selector
You can further narrow the selection process to encompass only those elements whose attributes are a certain value.

```css
a[href="https://mru.ca"] {color: blue;}
p[class="urgent warning"] {font-weight: bold;}
```

---

#### Partial-match Attribute Value Selector
You may want to select elements based on portions of their attribute values, rather than the full value. CSS offers a number of options for this situation.

- Matching one word in a space-separated list: `p[class~="warning"]` 

- Matching a substring within an attribute value: `a[href*="mru.ca"] {font-weight: bold;}`

- Matching a substring at the beginning of an attribute value: `a[href^="https:"] {font-weight: bold;}`

- Matching a substring at the end of an attribute value: `a[href$=".pdf"] {font-weight: bold;}`

---

#### The Case-Insensitivity Identifier
Including an i before the closing bracket of an attribute selector will allow that selector to match attribute values case-insensitively, regardless of document language rules. 

```css
a[href$='.PDF' i]
```

---

### Descendant Selector
When you want to select some elements based on their shared ancestor.

```css
h1 em {color: gray;}
ul ol ul em {color: gray;}
```

---

### Children Selector
When you want to select element based on their direct parent.

```css
h1 > strong {color: red;}
```

---

### Adjacent-sibling Selector
When you want to select an element based on the sibling that appears immediately before them.

```css
h1 + p {color: red;}
```

Select any `<p>` element that immediately follows an `<h1>` element that shares a parent with the `<p>` element.

---

### Sibling Selector
When you want to select elements based on the sibling that appears before them (not necessarilly RIGHT before them).

```css
h2 ~ ol {font-style: italic;}
```

They don't have to be adjacent.