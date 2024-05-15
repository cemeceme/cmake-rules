# cmake-rules
A set of please rules, that can handle some cmake related functionality.

## How to use

First, make sure to include the plugin within your please project by adding the following to your projects `plugins/BUILD` file:
```
plugin_repo(
  name = "cmake",
  revision = "master",
  plugin = "cmake-rules",
  owner = "cemeceme"
)
```
Make sure to either `preloadsubincludes` or `subinclude` the rules in the BUILD files where you need them.

## Provided rules

### cmake_configure_file
Parses a file and generates a configured file as calling cmakes configure_file would.

Takes the following arguments:
```
name         (str) : Name of this rule.
src          (str) : The source file to parse.
out          (str) : The output for the generated file.
escapeQuotes (bool): If true, escapes substituted quotes with c-stype backslashes. TODO
atOnly       (bool): If true, only replaces variables in the form of @VAR@.
variables    (dict): A dictionary of variables to substitute or enable in the source.
deps         (list): Dependent rules.
test_only    (bool): True if this rule should only be used for tests. Defaults to False.
visibility   (bool): list of rules that should have visibility to this rule. Defaults to None.
```