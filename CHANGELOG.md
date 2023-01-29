# Change Log

All notable changes to the "magegamescript-colors" extension will be documented in this file.

## 2023-01-28 (v0.5.2)

Bugs fixed:

- incorrect term for an entity's assigned path (is `%PATH%` but should be `%ENTITY_PATH%`)
- `slot` in `save slot` not colored
- variable values (`$asdf$`) not colored in serial dialogs
- `mutate varName + $number` uses string color for `$number` (crosstalk with `register verb + arg`)
- `show dialog $string` and `show dialog {}` (and equiv. `serial dialog`) using differing colors in specific themes
- many string specifiers using the wrong colors in specific themes (due to nested scope selectors)

## 2022-11-24 (v0.5.1)

- Syntax for registering and unregistering serial commands
- Better `wait` and `block` behavior

## 2022-11-12 (v0.5.0)

NEW! Serial dialog syntax:

- `serial dialog {}`
- `settings for serial dialog {}`
- `set serial connect message {}`
- `show serial dialog {}`
- `serial dialog` contents:
	- serial dialog options (`_` and `#`)
	- style tags inside messages and multiple choice option labels (e.g. `<bold>`)
- Anticipated MGE features:
	- `concat serial dialog {}`
	- `set serial control`

Other polish:

- `load` now `keyword.control` when before `map` (but nothing else)
- Backslashes can now be escaped in dialog messages
- Misc bug fixes
- Action keywords are now `storage.type` instead of `keyword.other`, which improves contrast in many themes

## 2022-10-06 (v0.4.2)

- Added package icon (drawn by @CorfidBizna).
- Color decisions changed or polished:
	- `parameters` and `settings` now colored like general action keywords
	- Assignment and logical operator keywords now entirely distinct
	- Action keywords now `keyword.other` instead of `constant.language` (more accurate scope)
- Fixes
	- Found some number suffixes I missed (`pix` and `s`)
	- Comments can now occur in dialogs after the identifier and before the messages

## 2022-10-05 (v0.4.1)

- Fixed package and publisher name.

## 2022-10-05 (v0.4.0)

- Support for the `const!` macro
	- Except for things like script names and dialog messages, action variables can now be substituted by `$` + bareword (a natlang const)
- Dialog identifiers are now *all* a separate color (and now entirely uniform in color), regardless of type: bareword identifier, `entity`, and `name`
	- (Only the chars in `%PLAYER%` and `%SELF%` are not this color)
- Moderate refactoring (partly to enable the above)
- Various small fixes (e.g. `animationFrame` -> `animation_frame`)

## 2022-09-29 (v0.3.2)

- Misc improvements
	- The token `{` can now smoosh up against the previous word (e.g. `dialog dialogName{`)
	- Dialog options `>` and `:` now marked with `keyword.control` to indicate that they result in a script jump
	- `load` now marked with `keyword.control` to indicate that it results in (effectively) a script jump
	- `then` will now be colored even if isolated on the next line
	- `dialog` in dialog nodes now marked as `constant.language` instead of `keyword.control`

## 2022-09-27 (v0.3.1)

- Misc updates
	- Words like `primaryID` now back to their original JSON form (`primary_id`)
	- Keywords like `turn`/`copy`/`set` (apart from `if`/`else`/`goto`) are now `constant.language` instead of `keyword.control` (the same color as the other language constants like `true` and `north`)

## 2022-09-27 (v0.3.0)

- MGS Natlang "zigzag" preprocessor support:
	- Added `if` / `else if` / `else` condition coloring
	- Improved syntax consistency
	- Punctuation handling for `(` / `)`

## 2022-09-24 (v0.2.3)

- QOL for auto text behavior, including:
	- auto indent after `{`
	- comment or decomment now uses inline comment syntax
	- finding matching brackets when one is selected

## 2022-09-06 (v0.2.2)

- Quote-wrapped script declarations without `script` prefix are now correctly colored
- More consistency for dialog parameters, particularly "relative names" (e.g. `%Helga%`)
- `%` and `$` can now be escaped in dialog messages
- Dialog options labels now behave the same as dialog messages

## 2022-09-02 (v0.2.1)

- Brought into line with more relaxed MGS syntax

## 2022-08-22 (v0.2.0)

- Update to MGS language v2

## 2022-07-23 (v0.1.2)

- Script name strings now yellow; bug fixes

## 2022-07-22

- Better comment handling (0.1.1)
- Initial release (0.1.0)