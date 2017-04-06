# alphabi-rulesets

Tracking the differing known rules and variations of alphabinary-family encodings.

The original Alphabinary definition only specified how to handle characters in the modern Latin alphabet, leaving handling for whitespace and punctuation undefined (though it's implied that whitespace should be discarded).

However, this definition falls short in a number of ways:

- It doesn't state how to interpret digits in the input (including a literal "0" or "1"), whether they should be included or discarded.
- It doesn't describe how to handle even *slight* variations on these letters, such as an accented "é".
- It's ambiguous about how to handle spaces and punctuation, and the implied discarding of them wastes potential space for further information (ie. interpreting a space character as a zero bit brings the information density much closer to a one-character-to-one-bit ratio).
- It doesn't provide rules for characters in other alphabets, such as Ф (the Cyrillic "Ef").

This repository documents rulesets in further detail to address the issues above. It *also* documents how these further rulesets may be contextually *inappropriate* (such as the way that the Cyrillic "С" would be considered in the *lower* half of its alphabet, meaning that a ruleset interpreting it as a Latin-compatible "C" would yield the *opposite result* from what would be appropriate for Cyrillic text), and suggests what considerations should be taken into account.

## Call for Localizations

Rulesets for handling non-Latin scripts are, right now, woefully inadequate, and handle non-Latin characters based around *technical* criteria (such as what their *Unicode-compatible* character definition is) rather than any culturally-respectful criteria (such as how citizens of a region would interpret their alphabet).

This is, frankly, because I personally don't actually *know* any of these details, and don't want to be so presumptuous as to imply that I do (that's how we end up with messes like Han Unification). As such, I invite native readers of languages that use alphabets *other* than Latin to submit appropriate alphabinary interpretations for their culture via pull request, so that they may be represented here.
