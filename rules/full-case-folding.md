# Full Case Folding

## Definition

The input text's case should be normalized using Unicode's Full Case Folding rules.

This is distinct from mere lower-case mapping, as it encompases lossy transformations that are only exhibited when mapping the text to upper case (such as "LATIN SMALL LETTER SHARP S", which is transformed to "SS" when mapped to upper case, and consequently mapped to "ss" when transformed back to lower case).

This is also distinct from simple case folding, an alternative mapping for character sequences that uses single-character mappings rather than the multi-character transformations of Unicode's "Special Casing" rules.

## Implementation remarks

The proper way to implement Unicode case folding is to map characters using the CaseFolding.txt mappings in the Unicode standard; however, for environments that do not expose this functionality (such as JavaScript, at least as of 2016), this can be emulated by mapping the string's upper-case mapping to lower-case, until the final lower-case mapping is identical to the last iteration.

While the previously-described mechanism is *similar* to the procedure used by Unicode, it is not *guaranteed* to give the same result, as Unicode's case mappings are also informed by historical stability concerns: for instance, Unicode defines the folded case for Cherokee characters as the *upper* case, due to the lower case not existing in earlier versions of Unicode. If the alphabinary encoding rules would give different results based on this distinction, this caveat should be taken into consideration.
