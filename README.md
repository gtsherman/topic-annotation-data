TREC document topic annotations
===============================

Human annotations of randomly selected judged documents from the AP 88-89, Robust 2004, WT10g, and GOV2 TREC collections. Seven annotators were asked to read documents in their entirety and then select up to ten terms they felt best represented the main topic(s) of the document. Terms were chosen from among a set sampled from the document in question and from related documents.

# Data description

## annotations.csv

The terms selected by users to describe the main topic(s) of documents.

- **user**: A randomly created five-digit string uniquely and anonymously representing annotators
- **doc**: The TREC DOCNO uniquely identifying each document
- **index**: The short TREC collection name
  - ap: AP 88-89
  - robust: Robust 2004
  - wt10g: WT10g
  - gov2: GOV2
- **term**: A term selected by this user to describe the topic of this document. Most documents have up to ten unique term selections, though in a small number of cases eleven terms were selected (see `quality_checks.csv` below)

## inter\_annotator\_agreement\_docs.txt

The set of 15 documents that all annotators were required to annotate, allowing for measurement of inter-annotator agreement. One document DOCNO per line.

## quality\_checks.csv

The annotation interface randomly inserted directions to select a specific term in describing the document. Terms were selected with probability inverse to their maximum likelihood estimates, to attempt to ensure that unrelated terms were required. The purpose was to ensure that annotators were reading documents in their entirety before selecting descriptive terms.

Annotators were allowed to select an additional term to accommodate these required selections (for a total of eleven term selections). Due to an oversight, this allowed annotators to disregard required terms and instead select eleven descriptive terms, exceeding the ten descriptive term limit. This happened infrequently.

- **user**: The annotator designation (see `annotations.csv` for more detail)
- **doc**: The DOCNO (see `annotations.csv` for more detail)
- **term**: The term users were required to select for this document
- **selected**: A binary indicator of whether annotators selected the required term (1) or failed to select it (0)

