# Research methods

The notebooks in this folder aim to illustrate a few different NLP methods, mostly using [spacy](https://spacy.io/). Spacy is a Python library for Natural Language Processing, with a focus on "doing real work". This distinguishes spacy from the more academically-focused toolkits such as [NLTK](https://www.nltk.org/). 

## Summary before you dive in

### Using NLP libraries

NLP libraries exist to make mechanical processing of text easier,
often by splitting things into smaller tasks and assisting each of them.

There are many such libraries, and each has its own way of doing things.
We give some introduction, and a number of examples in the one we use for these notebooks, spacy.

See
- [methods_nlp__intro_and_nlp_libraries](methods_nlp__intro_and_nlp_libraries.ipynb)
- [methods_nlp__spacy_basics](methods_nlp__spacy_basics.ipynb)


### Terms and phrases

If you have the question "how you detect interesting terms / phrases?",
the answer would include
"it depend on what you mean with interesting",
and "it depends on how thorough you want it to be".

We could spend a lot of text on clarification like 
- do we mean words that combine for known reasons and with predictable structure, or words that we notice are unusually cozy without suggesting structure yet
- do we mean cases where the meaning comes directly from the parts versus cases that are clearly not literal
- what names do we give to each? (multi-word expressions, lexicalized and institutionalized phrases, collocations, idioms)

...yet it is probably more interesting to ask questions like
- do we care about getting out a bunch of suggestions, or do we really need need complete, clean output
- "what multi-word things appear in this document at all" 
- "what multi-word things make this document interesting" (by what metric, though?)
- "what multi-word things make this document different from those in the language in general" (probably pointing out it is a legal document, which is... not so useful)
- "what multi-word things make this document different from others in a general legal context" (maybe pointing out the broad kind of document)
- "what multi-word things make this document different from others in a specific set of documents" (maybe extracting something _unusual_)
- "can we make lists of words"
- "what multi-word expressions make this document interesting" 
- match known phrases
- match phrases of a specific topic

These notebooks should be some start of contextualizing why these seemingly subtle variations can make a lot of difference.

#### Spacy pattern matcher

Spacy pattern matcher lets you find things by patterns conceptually like "NUMBER WORD NUMBER", "ADJECTVE NOUN", "uitspraak".

This may be most interesting to try to find very specific - and for the same reason will miss anything not matching exactly;
the following notebook in part eases getting started, and in part illustrates how this can be limited to match
longer matterns, because it turns out that humans are creative with their wording even within dry normative legal text.

See [methods_nlp__terms_spacy](methods_nlp__terms_spacy.ipynb)


#### Notes on tf-idf

Just counting words will quickly get disproportionate,
because in any almost language, most of the most common words are also least interesting,
being  empty function words like 'de', 'van' and 'dan'. 

Those are ignorable as stopwords, but what about words that in more specific context are just everywhere?
What about those that may be ubiquitous in one document set but not another?
Consider 'uitspraak', 'college', 'aanvraag', 'artikel'.

It's fine if you skim over this one, because it is central to anything - 
tf-idf is not a complete solution, it's more about recognizing how discounting words has 
value within other methods.

See the [methods_nlp_terms_tfidf notebook](methods_nlp_terms_tfidf.ipynb)


#### Collocations

Collocations are about finding words that are next to each other more than just chance.

Linguists may use it towards specific goals, perhaps "what verbs do we use with this noun, what adverb with this adjective?",

Collocation _analysis_ often refers to relatively basic statistics finding such unusually common combinations. 
It can be an ingredient in more specific goals or, like in the examples below, a less constrained one,
which may find anything from language-wider patterns like "in termen van", 
intentional phrases like "eigen gebruik",
parts of common phrasing in specific contexts like "indien de verhuurder",
and generally _fragments_ of phrases, "tijdstip zal", "verplichtingen uit", "heeft gedaan", and more. 

See [methods_nlp__terms_collocations](methods_nlp__terms_collocations.ipynb)


#### Topic modelling

While topic modelling is often aimed at the question 
"what sets of words or phrases seem to join and disinguish documents in a set",
if we ignore the last bit that does that splitting, 
we can inspect the words and phrases it _would_ use.

See [methods_nlp__topic_modeling](methods_nlp__terms_spacy.ipynb)



### Learning tasks

#### Named entities

See: [methods_nlp__spacy_training_ner](methods_nlp__spacy_training_ner.ipynb)

#### Categorizing text 

See: [methods_nlp__spacy_training_categorizing](methods_nlp__spacy_training_categorizing.ipynb)


### Extracting text _to_ analyse

#### PDF extraction; OCRing PDFs where necessary

See 
- [methods_technical__pdf_part1__extract_or_ocr](methods_technical__pdf_part1__extract_or_ocr.ipynb)
- [methods_technical__pdf_part2__more_extraction](methods_technical__pdf_part2__more_extraction.ipynb)