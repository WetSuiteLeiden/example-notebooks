These experiments set out with a specific goal, and sees how far we get.

Some of them are purely examples, others have led us to improve our code, or provide some data.


## [find-abbreviations](find-abbreviations)
Trying to find Abbreviations with explanations next to them,
in part as a classic example,
and in part to see which of these are useful terms to extract later (feed to NER training).

## [find-references](find-references)
Try to extract various kinds of references, from identifiers to the more naturally formatted ones.

## [find-wetnamen](find-wetnamen)
Try to find most of the name variations used to refer to each law,
in part as an example of text pattern matching,
in part as data to give to you,
in part to extract later (feed to NER training).

## [investigate-document-structures](investigate-document-structures)
Trying to inspect
In part to make XML less scary, in part in preparation for text-split (see below)

## [split-text](split-text)
Trying to extract text from varied formats (HTML, XML, PDF), 
and splitting it into fragments of text with some of the original format,
while allowing us to specialize the handling of specific sources of documents.

The goal was to make it a lot easier to extract text from varied documents.
The code behind this was merged into the wetsuite library.

## [maybe_later](maybe_later)
Experiments that may be removed later because they're not very interesting.

## [review-algoritmeregister](review-algoritmeregister)
Example of CSV parsing, and some very basic text matching.
