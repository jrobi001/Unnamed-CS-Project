---
layout: post
title:  "Data Sources"
date:   2020-10-28 14:44:42 +0100
categories: blog post
---

# Data Sources

I've been looking into the data sources and APIs that may prove useful in building the pronunciation app, below I'll run through a few of them.

The app is currently planned to have two languages - English and Japanese, so the data resources may refer to one or the other.

With Japanese presenting the phonetic reading of unknown words is generally enough to learn from, however with English few people know the international phonetic alphabet (myself included) - so an audio clip will be needed.

All language learners encounter the problem of unknown phenomes - it is often the case that the speaker may not know they are mis-pronouncing words slightly - or be able to detect the differences in pronunciation between [minimal pairs](https://en.wikipedia.org/wiki/Minimal_pair#:~:text=In%20phonology%2C%20minimal%20pairs%20are,separate%20phonemes%20in%20the%20language.) in recordings

Precise pronunciation isn't really the aim of the app though - just ability to read words generally correctly and absorb the spelling to pronunciation rules of a language (by hopefully encountering unknown words and attempting to pronounce them)

Ideally the app should present words to the language learner that are either:

1. Unknown to the user (but fairly common)
2. Words who's pronunciation are frequently misinterpreted from the spelling (or Kanji)

### Sentences:

[tatoeba.com]() sentences which are free to use. The sentences often have translations (for the same sentence) in multiple language.

Splitting up sentences from novels or books in the public domain are also an option.

### Dictionaries:

Japanese dictionaries from [EDRDG](http://www.edrdg.org/) - free to use for non-commercial or commercial with acknowledgement

English dictionaries - undecided - possibly [FreeDict](https://freedict.org/downloads/)

#### Language parsers:

For breaking down the sentences and identifying words (despite conjugation)

Japanese - [MeCab](http://taku910.github.io/mecab/) or [Ve](https://github.com/Kimtaro/ve)

English - undecided - possibly the [stanford Parser](https://nlp.stanford.edu/software/lex-parser.shtml)

### Audio

There are few free sources of whole sentences with audio (understandably)

The [Forvo api](https://api.forvo.com/) allows for pronunciations of individual words to be requested - it costs $2 a month for 500 requests a day and 28.95 for 10,000 a day - it may not be the best option.

[Google's text to speech service](https://cloud.google.com/text-to-speech) may need to be relied on at times - they offer an AI enhanced text to speech service which is quite impressive, however [there is a cost associated](https://cloud.google.com/text-to-speech/pricing). Developers do get $300 cloud credit for their first 90 days though, which may be enough for the project.

Other text to speech programs or services could be investigated

There are several other possible sources of audio recordings out there such as the [oxford dictionaries API](https://developer.oxforddictionaries.com/) or project [shtooka](http://shtooka.net/)

### Other

Word frequency lists to determine the order sentences should generally be presented

Lists of English words learners find difficult to learn exist (though often dependent on the language learning from) - they could also be used to some extent to increase the chances of encountering these words

People - it may be worth sending out a survey asking people who've learnt English (or Japanese) which words they remember finding tricky to pronounce

The app could contain information on minimal pairs, unknown phenomes and information on pronunciation - vowel charts - but this isn't really necessary.