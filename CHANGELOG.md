# Change Log

All notable changes to the "magegamescript-colors" extension will be documented in this file.

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

## 2022-07-23s (v0.1.2)

- Script name strings now yellow; bug fixes

## 2022-07-22

- Better comment handling (0.1.1)
- Initial release (0.1.0)