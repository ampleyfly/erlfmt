# Changelog

## v0.8.0 (5.10.2020)

Better rebar integration

### Enhancements

  - Better rebar integration #196 #183 #197 #200
  - Change formatting of pipes to prefixes #191 #194

### Fixes

  - Parse attributes with empty parens #189
  - Do not crash with comments before a dot #184
  - Do not crash with post comments in catch #195

## v0.7.0 (17.09.2020)

`--check` flag now provides exit code 1, if files are not formatted.

### Enhancements

  - `--check` flag #123

### Bug fixes

  - Preserve newline in list & binary comprehensions #116
  - Preserve new lines in guards and specs #115
  - Make multi-line tuples & binaries next-break-fits #117
  - Use deterministic compiler option for releasing precompiled escript #127
  - Do not crash when formatting an empty file #130
  - Relax map syntax #137
  - Support macros with parens in concat #138

## v0.6.0 (18.08.2020)

Configurable print-width and erlfmt-ignore comment

### Enhancements

  - `print-width` is now configurable as a command line parameter #99
  - `% erlfmt-ignore` comment ignores the next form and does not format it #98
  - files are now formatted in parallel #101

### Bug fixes

  - Preserve empty lines around if-like attributes #97
  - Don't break multiple clauses with comments #96
  - Make try and after always introduce a newline #107
  - Do not preserve operator newline with a next break fits expression #104
  - New format for multiline fun types #110

## v0.5.1 (05.08.2020)

### Bug fixes
  - correctly handle type unions inside of multiline containers (such as specs) #90

## v0.5.0 (05.08.2020)

### Enhancements
  - new `--insert-pragma` CLI option adds the `@format` pragma to all the formatted
    files that didn't have it before #75
  - preserve empty lines in containers #83

### Bug fixes
  - correctly handle `.script` files like `rebar.config.script` #79
  - `export_type` is formatted the same as `export` #86
  - print type unions either all on single line or each type separated by
    `|` on a separate line #84

## v0.4.2 (24.07.2020)

### Bug Fixes
  - `--require-pragma` combined with stdio for files with high-codepoint unicode

## v0.4.1 (23.07.2020)

### Bug Fixes
  - Fix dialyzer
  - `--require-pragma` for single-form and non-unicode files
  - Compiles with rebar3 3.14

## v0.4.0 (23.07.2020)

### Enhancements
  - require-pragma prints out original file instead of formatting if no pragma is found.
    This makes it easier to integrate into a CI pipeline. #57
  - Better exceptions #58
  - Group imports and exports with similar names on the same line. #65
  - Add format_string as a library call. #66

### Bug Fixes
  - Preserve empty lines between attributes #67
  - Remove space between single clause fun and parens #68

## v0.3.0 (09.07.2020)

### Enhancements
  - Allow reading from stdin with command `$ erlfmt -` #46
  - Support Erlang version 23.0

### Bug Fixes
  - Remove trailing spaces from comments #48
  - Make position of return type in specs consistent #47
  - Fix some parser failures in OTP #39
  - Concat converted from a string also forces breaks #43

## v0.2.0 (03.06.2020)

### New formatting algebra
Switched out formatting algorithm.
This is now based on Elixir's greedy algorithm, instead of a lazy algorithm.
This fixes performance issues with laying out larger tuples.

### Bug Fixes
  - Preserve empty lines between comments and expressions
  - Stop adding unnecessary empty lines between attributes
  - Stop indenting list and binary comprehensions unnecessarily
  - Fix formatting multiple files from command line
  - Ensure all parsable OTP files format cleanly

### Enhancements
  - Support formatting escripts and "consult" files like rebar.config
  - Add `--require-pragma` flag to only format files annotated with `@format`

## v0.1.0 (06.04.2020)

Initial release
