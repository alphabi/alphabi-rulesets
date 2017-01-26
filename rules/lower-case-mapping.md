# Lower Case Mapping

## Definition

The input text should be converted to lower case.

This is distinct from [proper case folding](full-case-folding.md), as it does not exhibit lossy transformations that are only exhibited when mapping the text to upper case (such as "LATIN SMALL LETTER SHARP S" (ß), which is transformed to "SS" when mapped to upper case, and consequently mapped to "ss" when transformed back to lower case: if the text is only lower-cased, it remains "ß").

## Implementation remarks

In JavaScript, text may be lower-cased using the `.toLowerCase()` method of strings.
