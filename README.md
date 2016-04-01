# Prism Style Guide

This is a style guide for the Prism project. Its goal is to write clearer and more maintanable code throughout the production process.

## Table of Contents

  1. [Javascript](#javascript)
    - [Classes](#classes)
    - [Variables](#variables)
    - [Constants](#constants)
    - [Semi-colons](#semi-colons)
    - [Functions](#functions)
    - [Files](#files)
    - [Folders](#folders)
    - [Vue.js specifics](#vuejs-specifics)
  2. [Templates](#templates)
  3. [CSS / SCSS](#css--scss)
    - [Formatting](#formatting)
    - [Variables](#Variables-1)
    - [Nesting](#nesting)
    - [Rules - order](#rules---order)

## Javascript

### Classes
Class names are written in camelCase and begin with an uppercase.

_Example_: `ClassName`

_Complete example_:
```js
export default class ClassName extends OtherClass {
    constructor(parameters) {

    }
}
```

### Variables
Variable names should be written in camelCase and begin with a lowercase. Declaring a variable should be done by using `let`and not the `var`keyword.

_Example_:
```js
let variableName      = value
let otherVariableName = value
```


### Constants
They will be defined right after the `import` section of the code and before declaring any variables. They will be written in snake_case and entirly in uppercase.

_Example_: `const CONST_NAME = value`

### semi-colons
We will not use semi-colons in Javascript.

Check out this article: [Semicolons aren't required](https://github.com/yyx990803/semi#but-semicolons-are-required)

### Functions
They will be named in camelCase starting with a lowercase. All parameters should be on the same line as well as the opening bracket. The `function` keyword will not be used.

_Example_:
``` js
functionName(parameter1, parameter2, parameter3) {
    //function's core
}
```

### Files
Files must be named in kebab-case with only lowercase caracters.

_Example_: `my-file-name`

### Folders
The same rule applies for folders

_Example_: `my-folder-name`

### Vue.js specifics
Custom components, sections, transitions, directives... should be organised as such
```
.
├── _vuejs-component
|   ├── vuejs-component.js
|   ├── vuejs-component.html
|   └── vuejs-component.scss
```
_Examples_:

**Note:** The folder and the file that are containing a class should have the same name than the class but with their respective rules.

## Templates

## CSS / SCSS

### Formatting

* Use tabs (4 spaces) for indentation.
* Never mix spaces and tabs for indentation.
* Prefer dashes over camelCasing in class names.
* Do not use ID selectors.
* When using multiple selectors in a rule declaration, give each selector its own line.
* Put a space before the opening brace { in rule declarations.
* In properties, put a space after, but not before, the : character.
* Put closing braces } of rule declarations on a new line.
* Put blank lines between rule declarations.

_Example_ :
``` scss
.selector {
  border-radius: 50%;
  border: 2px solid white;
}

.one,
.selector,
.per-line {
  // ...
}
```

### Variables

Prefer dash-cased variable names (e.g. `$my-variable`) over camelCased or snake_cased variable names. It is acceptable to prefix variable names that are intended to be used only within the same file with an underscore (e.g. `$_my-variable`).

### Nesting

Do not nest selectors more than three levels deep!

```scss
.page-container {
  .content {
    .profile {
      // STOP!
    }
  }
}
```
When selectors become this long, you're likely writing CSS that is:

* Strongly coupled to the HTML (fragile) —OR—
* Overly specific (powerful) —OR—
* Not reusable

### Rules - order

1. Property declarations

    List all standard property declarations, anything that isn't an  `@include` or a nested selector.
    The properties should be grouped by type, example :
    ```scss
    .selector {
        /* Positioning */
        position: absolute;
        z-index: 10;
        top: 50%;
        right: 50%;
        transform: translate(-50%, -50%);

        /* Display & Box Model */
        display: inline-block;
        overflow: hidden;
        box-sizing: border-box;
        width: 100px;
        height: 100px;
        padding: 10px;
        border: 10px solid #333;
        margin: 10px;

        /* Text */
        font-family: sans-serif;
        font-size: 1rem;
        line-height: 1.5;
        text-align: right;
        color: #fff;

        /* Color */
        background: #000;
        fill: #123;

        /* Other */
        cursor: pointer;

        /* Animations */
        transition: all 2s ease;
        animation: my-keyframes 2s ease forwards;
      }
    ```

2. `@include` declarations

    Grouping `@includes` at the end makes it easier to read the entire selector.

3.  Nested selectors

    Nested selectors, if necessary, go last, and nothing goes after them. Add whitespace between your rule declarations and nested selectors, as well as between adjacent nested selectors. Apply the same guidelines as above to your nested selectors.
