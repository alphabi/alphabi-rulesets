# Normalization Via Compatible Decomposition

This rule provides a means by which extended characters may be evaluated as
characters they resemble.

As it translates similar-looking but semantically-distinct characters, it is not necessarily appropriate for use in concert with other rules which evaluate canonically-different characters: in such cases, NFD "canonical decomposition" may be the more appropriate form of consolidation.

## Definition

Before evaluating the input string, it is normalized according to [Unicode Compatibility Decomposition][TR15].

[TR15]: http://www.unicode.org/reports/tr15/

## Implementation remarks

As of ECMAScript 2015 (ES6), a string may be normalized in this form by calling the String method `.normalize("NFKD")`. See [MDN][] for more information, including browser support.

[MDN]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/normalize

## Undefined externalities

The transformation of the compatibly-decomposed result into bits is entirely undefined by this rule.
