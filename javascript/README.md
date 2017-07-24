# Javascript styleguide

## Quickstart

You can include these rulesets in your local setup by including this repository
as a submodule.

```
$ cd MY_PROJECT/
$ git submodule add https://github.com/10eTechnology/styleguide.git styleguide
```

Then add the following to your `.eslintrc.json` file:

```
{
  "extends": "./styleguide/javascript/.eslintrc.json"
}
```

Make sure you have the following `npm` modules installed:
  * "eslint": "^4.3.0"
  * "eslint-config-airbnb": "^15.1.0",
  * "eslint-plugin-import": "^2.7.0"
  * "eslint-plugin-jsx-a11y": "^5.1.1"
  * "eslint-plugin-react": "^7.1.0"

## Extends

This rule set extends the popular [Airbnb eslint config](https://github.com/airbnb/javascript)
with some specific rules that fit our coding style.

## Plugins

This configuration includes plugins useful for developing with ES6 and React.

Plugins included are:
* [react](https://github.com/yannickcr/eslint-plugin-react)
* [jsx-a11y](https://github.com/evcohen/eslint-plugin-jsx-a11y) - required by the airbnb config
* [import](https://github.com/benmosher/eslint-plugin-import)

## Our coding style

This rule set modifies the above rule sets as follows:

### [react/jsx-filename-extension](https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/jsx-filename-extension.md)

File names may end with either '.js' or '.jsx'

### [complexity](http://eslint.org/docs/rules/complexity)

Throws an error for blocks of code with a [cyclomatic complexity](https://en.wikipedia.org/wiki/Cyclomatic_complexity) higher than 20.

### [key-spacing](http://eslint.org/docs/rules/key-spacing)

Key values should line up.

**Bad**
```javascript
{
  firstName: 'Andrew',
  lastName: 'Smith',
  age: 22
}

{
  firstName : 'Andrew',
  lastName  : 'Smith',
  age       : 22
}
```

**Good**
```
{
  firstName: 'Andrew',
  lastName:  'Smith',
  age:       22
}
```

### [no-multi-spaces](http://eslint.org/docs/rules/no-multi-spaces)

Multiple spaces are disallowed, except in a group of variable declarations.

**Bad**
```javascript
const a = 1   + 2;
const b  =  1 * 2;
```

**Good**
```javascript
const count     = 10;
const sum       = 1 + 2;
const firstName = "Andrew";
```

### [newline-after-var](http://eslint.org/docs/rules/newline-after-var)

A single empty line is required after variable declarations.

**Bad**
```javascript
const a = 1 + 2;
sum(a, 3);
```

**Good**
```javascript
const a = 1 + 2;
const b = 3;

sum(a, b);
```

### [newline-before-return](http://eslint.org/docs/rules/newline-before-return)

A newline is required before the return statement.

**Bad**
```javascript
function addFive(a) {
  if (!a) {
    return -1;
  }
  return a + 5;
}
```

**Good**
```javascript
function addFive(a) {
  if (!a) {

    return -1;
  }

  return a + 5;
}

function addFive(a) {
  return a + 5;
}
```

### [no-empty-function](http://eslint.org/docs/rules/no-empty-function)

Empty functions are not allowed.

**Bad**
```javascript
function doNothing() {
}

function doNothing() {}

list.map(() => {});  // returns undefined
```

**Good**
```javascript
function doNothing() {
  // do nothing
}

list.map(() => ({})); // returns an empty object
```

### [max-depth](http://eslint.org/docs/rules/max-depth)

Disallows nesting blocks more than four deep.

### [max-len](http://eslint.org/docs/rules/max-len)

Disallows lines longer than 80 characters.

### [max-statements-per-line](http://eslint.org/docs/rules/max-statements-per-line)

Only one statement is allowed per line.

**Bad**
```javascript
const a = 1; const b = 2;
```

**Good**
```javascript
const a = 1;
const b = 2;
```

### [newline-per-chained-call](http://eslint.org/docs/rules/newline-per-chained-call)

Chained calls cannot exceed a depth of two.

**Bad**
```javascript
this.that().other().those();
```

**Good**
```javascript
this.that().other();
this
  .that()
  .other()
  .those();
```

### [indent](http://eslint.org/docs/rules/indent)

We conform to the eslint defaults with the exception of "MemberExpression", which
must be indented one level.

**Bad**
```javascript
this
.that()
.other()
  .those();
```

**Good**
```javascript
this
  .that()
  .other()
  .those();
```
