# Superficial Alphabinary Encoding

This is an Alphabinary ruleset that handles characters according to the base Latin characters they are deemed to resemble according to the rules of Unicode Compatibility and Decomposition. This most accurately resembles the way that a pure-

However, for scripts other than Latin (eg. Cyrillic characters), it's unsuitable: for example, the Latin-compatible "C" would yield the *opposite result* from what a Cyrillic "С" should be interpreted as, considering that Cyrillic languages uniformly place this character in the *lower* half of their alphabets.

## Procedure

Fold the text's case [(per the "full-case-folding" rule procedure)](../rules/full-case-folding.md).

Normalize the input by Unicode Compatibility Decomposition [(per the "nkfd" rule procedure)](../rules/nkfd.md).

Convert all letters from 'a' to 'm' to zero and all letters from 'n' to 'z' to 1 [(per the "latin" rule procedure)](../rules/latin.md).

Ignore all other code points [(per the "discard-rest" rule procedure)](../rules/discard-rest.md).
