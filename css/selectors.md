# CSS Selectors Cheatsheet
(Thank you [MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)!)

## Basic Selectors

Type: ex `div`

Class: ex `.classname`

ID: ex `#idname`

Attribute: examples 
* `[attr]` matching on `attr`
* `[attr=value]` matching on `attr` whose value is `value`
* `[attr^=value]` matching on `attr` whose value starts with `value`
* `[attr$=value]` matching on `attr` whose value ends with `value`
* `[attr*=value]` matching on `attr` whose value contains `value`

## Combinators

Adjacent sibling: `A + B` 
* `p + span` matches all `<span>` elements that directly follow a `<p>`

General sibling: `A ~ B`
* `p ~ span` matches all `<span>` elements that follow a `<p>`

Child: `A > B`
* `p > span` matches all `<span>` elements that are nested directly inside a `<p>`

Descendant: `A B`
* `p span` matches all `<span>` elements that are inside a `<p>`

## Pseudo-classes
[Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes): specifiy special states of a selected element
* `p:hover` matches any `<p>` element that is being hovered over

## Pseudo-elements
[Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements): specify a specific part of a selected element
* `p::first-line` matches the first line of every `<p>`
