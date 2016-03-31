# Prism Style Guide

This is a style guide for the Prism project. Its goal is to write clearer and more maintanable code throughout the production process.

## Javascript
---

### Classes
Class names are written in camelCase and begin with an uppercase.

_Example_: `ClassName`

_Complete example_:
```
export default class ClassName extends OtherClass {
    constructor(parameters) {

    }
}
```

### Variables
Variable names should be written in camelCase and begin with a lowercase. Declaring a variable should be done by using `let`and not the `var`keyword. When declaring multiple variables, they should be seperated with a coma.

_Example_:
```
let variableName      = value,
    otherVariableName = value
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
```
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
