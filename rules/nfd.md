# Normalization Via Canonical Decomposition

This rule provides a means by which extended characters may be evaluated as
their root canonical character, with any transformations to that character split to separate combining code points.

As it retains invisible semantic distinctions embedded in the underlying code points, it is not necessarily appropriate for use in cases where such semantic details are not easily communicable (such as visual recognition): in such cases, NFKD "compatible decomposition" may be the more appropriate form of consolidation.

## Definition

Before evaluating the input string, it is normalized according to [Unicode Canonical Decomposition][TR15].

[TR15]: http://www.unicode.org/reports/tr15/

## Implementation remarks

As of ECMAScript 2015 (ES6), a string may be normalized in this form by calling the String method `.normalize("NFD")`. See [MDN][] for more information, including browser support.

[MDN]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/normalize

## Undefined externalities

The transformation of the canonically-decomposed result into bits is entirely undefined by this rule.
