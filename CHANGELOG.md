# Change Log

All notable changes to the "magegamescript-colors" extension will be documented in this file.

## 2025-09-02 (v1.1.3)

- Operator bug fixes:
	- Partial matches (was matching `<` before `<=`)
	- Missing `>=` (was matching `=>`)
	- `logical` vs `assignment` stricter scoping; split category in unit tests
- Fixed TextMate version failing to match strings after `warp_state =` etc.
- Syntax colors for script "lambdas" in dialog and serial dialog options

## 2025-08-23 (v1.1.2)

- Fixed function definitions having wrong colors for body

## 2025-08-23 (v1.1.1)

- Fixed label coloring bug
- Fixed function args not being colored after the first 1-2

## 2025-08-19 (v1.1.0)

- Added functions! `fn functionName($arg, $arg)`
- Changed `copy!(scriptName)` to just `scriptName()` to more closely resemble functions
- Removed almost all ['\"] entries (single quotes are deprecated)
	- Final case is complex and I'll do it later
- Aligned tokens in unit tests to make it easier to spot anomalies

## 2025-08-16 (v1.0.0)

- "Mathlang" syntax overhaul!
- More modular syntax (more like math than a natural language)
- Properly recursive syntax
- Expressions and other non-fixed-length features
- Other QOL like the "spread" operator
- Bare identifiers for bools and ints
- Identifiers now identifier-colored
- Much simpler keyword-based coloring


## 2024-03-12 (v0.10.0)

- corrected color for certain contexts of quoted script names
- changed instances of multiple scopes to single scopes (improves compatibility)
- `$_` variables colored correctly more places, and are more consistent across themes
- `+ 000`: the `000` is now colored like a string before `->` and colored like a number otherwise
- New language phrases:
	- `alias _ = _;`
	- `remove alias _;`
	- `hide command _;`
	- `unhide command _;`
- Updated preview image

## 2023-11-13 (v0.9.1)

- removing unused and non-useful keywords:
	- `failure` (now just `fail`, rather than both variants being okay)
	- `arg` and `command` (implied by their use: `register (command) $STRING + (arg) $STRING`)
- more bug fixes involving patterns failing when snug against a `;` (instead of whitespace)
- optional words for dialog settings removed:
	- `parameters for label labelName` now just `label labelName` etc.
	- in addition, `global default`/`defaults` now just `default`

## 2023-10-28 (v0.9.0)

- new "macro" `debug!()`
	- contents are equivalent to `show serial dialog {}`
	- anticipating engine feature: if not a quoted string, contents refer to a serial dialog name
- *actually* fixed `ALL` light keyword this time (oopsie-doopsie)
- bug fixes involving patterns failing when snug against a `;` (instead of whitespace)

## 2023-10-13 (v0.8.0)

- new "macro" `include!()`
- new constructions `for` and `while`
- new keywords `return`, `break`, `continue`, `pause`, `unpause`
- new action `goto index _`, `goto label _` (standalone and `CHECK_` versions)
- new parameters for map: `on_load`, `on_command`
- removed `on_tick` (etc) variants (now these are only in the `on_tick` (etc) form)
- bug fix: light keyword `ALL` (was `ANY`) (oopsie)

## 2023-09-17 (v0.7.0)

- relative entity names (`%PLAYER%`) are now colored within serial dialog messages
- colors for `debug mode` in condition statements
- colors for `lights control`, specifier `light`, and the fixed names for the lights themselves

## 2023-06-24 (v0.6.0)

New actions, new keywords!

- removed `hackable_state` entity fields
- added entity field `relative_direction`
- added `on_look` (etc) as a synonym of `look_script` (etc)
- new condition: `if (dialog is _) {}` (`open`/`closed`) (also for `serial dialog`)
- new actions: `close dialog` and `close serial dialog`
- new ANSI tag: `<bell>`

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