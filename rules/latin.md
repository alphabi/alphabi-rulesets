# Latin Alphabinarization

This is the core alphabinary encoding rule that governs all rulesets deriving from the original, simplest definition, that only pertained to English text written in ASCII.

## Definition

The following characters are transformed to a "zero" bit (0):

A, a, B, b, C, c, D, d, E, e, F, f, G, g, H, h, I, i, J, j, K, k, L, l, M, m

The following characters are transformed to a "one" bit (1):

N, n, O, o, P, p, Q, q, R, r, S, s, T, t, U, u, V, v, W, w, X, x, Y, y, Z, z

## Implementation remarks

In the ASCII set (and by consequence, Unicode), all alphabetical characters have code points in alphabetical order: this allows for the state of a character falling within the range of these characters to be decided based on its code point's position relative to the midpoint of the range, rather than having to hard-code every letter.

However, in doing so, care must be taken to *only* apply this rule to characters within this range: code points before "A", or after "z" (or between the upper- and lower-case ranges) are not addressed by this rule, and care must be taken that they are not inadvertently processed as part of such a simplification.

## Undefined externalities

The transformation of any characters other than the 52 specified above (including any accented variations) are undefined by this rule.

Such extended characters may be coerced to a form containing these characters so that they *may* be covered by this rule, eg. by following a decompositional normalization like NFD: however, this rule, on its own, does not dictate any such normalization.
