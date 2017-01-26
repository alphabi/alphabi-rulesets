# Naive Alphabinary Encoding

This was the Alphabinary ruleset used by the first test scripts to generate alphabinary-to-letter dictionaries.

It is very simple to implement (requiring code to only have a knowledge of 52 code points), making it suitable for ASCII-only text.

However, for any text containing any letter characters outside of the ASCII set (such as an accented "é"), it is unsuitable, as it discards such characters entirely. (It also doesn't exhibit proper case-folding, which would cause some extended characters to transform into Latin characters.)

For handling such characters in a way that more closely resembles how a user familiar with only the Latin alphabet may interpret them (ie. ignoring the accents and interpreting them as the *unaccented* Latin letter they resemble), see [Superficial Alphabinary Encoding](superficial-alphabi.md).

## Procedure

Convert the text to lower case [(per the "lower-case-mapping" rule procedure)](../rules/lower-case-mapping.md).

Convert all letters from "a" to "m" to zero and all letters from "n" to "z" to 1 [(per the "latin" rule procedure)](../rules/latin.md).

Ignore all other code points [(per the "discard-rest" rule procedure)](../rules/discard-rest.md).
