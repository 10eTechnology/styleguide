# styleguide

Styleguides for the 10e org

## Quickstart

You can include these rulesets in your local setup by including this repository
as a submodule.

```
$ cd MY_PROJECT/
$ git submodule add https://github.com/10eTechnology/styleguide.git styleguide
```

Then add the appropriate sub-module to your linter config.  For instance, for
`eslint`, you would add the following to your `.eslintrc.json` file:

```
{
  "extends": "./styleguide/javascript/.eslintrc.json"
}
```
