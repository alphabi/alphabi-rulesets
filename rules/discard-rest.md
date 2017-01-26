# Discarding undefined characters

## Definition

Any code points that have not been consumed at this point should be omitted from the output.

This is expected to be the last rule in any alphabinary encoding ruleset that doesn't attempt to handle remaining characters in some other way (ie. converting them into the bits *of the code point*).

One twist on this rule is to *preserve* characters (ie. yielding anything in the output *other* than 1 or 0): however, if an implementation does so, it should state this difference, as alphabinary encoding rulesets are only meant to define a translation into *abstract bits*, not character streams.

## Implementation remarks

If the text has been converted to ones and zeroes (and any *pre-existing* ones and zeroes have already been handled appropriately, which means they need to be removed first if the ruleset only defines rules for *letters* and not digits), this can be achieved by just removing any characters other than "0" or "1" (ie `sed s/[01]//`).
