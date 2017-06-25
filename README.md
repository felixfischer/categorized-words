# Categorized Words

**Clean list of ~90k english words divided into seven categories. Useful for
e.g. generation of memorable, pseudo-semantical passphrases or human-friendly
identifiers.**

## About

This package is basically just a jsonified and slightly cleaned version of the
[`2of12id.txt` wordlist](wordlist/alt12dicts/2of12id.txt) (as of 3 May 2016) from
[The Unofficial Alternate 12 Dicts Package](http://wordlist.aspell.net/12dicts/)
of the [SCOWL (Spell Checker Oriented Word Lists)](http://wordlist.aspell.net/)
project.

> The 2of12id.txt file, in the alternative version of 12Dicts, is the primary
> source of part-of-speech and inflection information, however it is limited to
> common words.

*— Description from [wordlist.aspell.net](http://wordlist.aspell.net/)*

### Modifications

I have removed from the original file all entries that were somehow marked as
special, leaving in **only regular, non-hyphenated words consisting solely of
characters `a-z`** which should also not be totally obscure.

No censoring or other content-based cleaning has been applied. Please use this
source at your own discretion and expect it to contain profane words.

### Possible Uses

I made this package primarily to provide a better structured dictionary for
[XKCD-style password generators](https://www.npmjs.com/search?q=xkcd+password),
to support the generation of semantically somewhat viable word combinations that
can hopefully be remembered more easily.

These wordlists can certainly also be used for other purposes, e.g., to generate
memorable identifiers for things, like those you know from Heroku and Docker.

## Contents

|  Key  | Word class               | Size      |
|:-----:|:-------------------------|----------:|
| **N** | noun                     |     47004 |
| **V** | verb                     |     31232 |
| **A** | adjective                |     14903 |
| **I** | interjection             |       188 |
| **C** | conjunction/preposition  |       139 |
| **P** | pronoun                  |        78 |
| **S** | spoken contraction       |         9 |
|       | **Total of all classes** | **93553** |

## Usage Example

```
const words = require('categorized-words')
console.log('first noun in list:', words.N[0])
```

## Data Format

The module returns an object with keys `['A','C','I','N','P','S','V']`, each
representing a word class, and having as their value an array containing
the words in that class. The format looks like this:

```
{
  X: ['lots', 'of', 'words'],
  Y: ['even', 'more', 'of', 'them']
}
```

## Credit/License

This work is based on [SCOWL](http://wordlist.aspell.net/). It is available
under the [MIT License](https://opensource.org/licenses/MIT).
