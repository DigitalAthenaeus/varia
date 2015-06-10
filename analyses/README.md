# Analyses

This directory contains *citable analyses* of the text of Athenaeus.

## File: `authors.csv`

A `.csv` list enumerating and identifying authors reused by Athenaeus.

### Properties

- **EntityUrn** - a CITE URN uniquely identifying a re-used author.
- **CtsUrn** - a CTS URN identifying a passage *in Athenaeus* where the author is mentioned. This passage serves to justify the author's inclusion in the list; when an author is reused often, the passage here should be a clear, unambiguous reference. *E.g.* "Homer says…".
- **Label** - a human-readable name for the author. *E.g.* "Plutarch of Chaeroneia"
- **OptionalCtsGroupUrn** - for extant authors (Homer, Plutarch), a group-level CTS URN identifying the author. *E.g.* `urn:cts:greekLit:tlg0012:`.

## File: `works.csv`

A `.csv` list enumerating and identifying works reused by Athenaeus.

### Properties

- **EntityUrn** - a CITE URN uniquely identifying a re-used work.
- **AuthorUrn** - a CITE URN uniquely identifying a re-used author; this must correspond to an author cataloged in `authors.csv` above.
- **CtsUrn** - a CTS URN identifying a passage *in Athenaeus* where the work is mentioned. This passage serves to justify the work's inclusion in the list; when a work is reused often, the passage here should be a clear, unambiguous reference. *E.g.* "Eupolis says, in the *Dēmoi*…".
- **Label** - a human-readable name for the work. *E.g.* "*Dēmoi*"
- **OptionalCtsWorkUrn** - for extant works, a work-level CTS URN identifying the work. *E.g.* `urn:cts:greekLit:tlg0012.tlg001:`.

A fun example will be names for specific books of the *Iliad*. Those can have more precise CTS URNs in the **OptionalCtsWorkUrn** field: `urn:cts:greekLit:tlg0012.tlg001:18` = "Hoplopoiïa".

## File: `characters.csv`

A `.csv` list enumerating and identifying sophists who take part in the banquet described by Athenaeus.

### Properties

- **EntityUrn** - a CITE URN uniquely identifying a character.
- **CtsUrn** - a CTS URN identifying a passage *in Athenaeus* where the character is mentioned. This passage serves to justify the character's inclusion in the list; when a character is reused often, the passage here should be a clear, unambiguous reference. *E.g.* "Ulpianus says…".
- **Label** - a human-readable name for the character. *E.g.* "Galenus Pergamenus"
- **OptionalCtsGroupUrn** - for extant characters, a group-level CTS URN identifying the character. *E.g.* `urn:cts:greekLit:tlg0057:`.

## File: `mentions.csv`

A `.csv` file cataloging every mention of authors, characters and works in Athenaeus, and Athenaeus' vocabulary for identifying authors, characters and works. For example, Athenaeus may mention that a work by Archestratus of Syracuse was known by four different names (i.e., Gastronomy, Life of Pleasure, Science of Dining, or Art of Cooking); this would generate five entries in this list: one mention of "Archestratus", and four mentions of the same work.

### Properties

- **EntityUrn** - a CITE URN uniquely identifying a reference in Athenaeus.
- **CiteUrn** - a CITE URN (from `authors.csv` or `works.csv` above) identifying the author or work mentioned in Athenaeus.
- **CtsUrn** - a CTS URN specifying a passage in Athenaeus that mentions the author.
- **Text** - the relevant textual content of the passage specified by the CTS URN (above).
- **Notes** - human-readable notes. May be empty.

## File: `reuses.csv`

- **EntityUrn** - a CITE URN uniquely identifying an instance of text-reuse in Athenaeus.
- **CiteUrn** - a CITE URN (from `authors.csv` or `works.csv` above) identifying the author or work mentioned in Athenaeus.
- **CtsUrn** - a CTS URN specifying a passage in Athenaeus containing text-reuse. This should be a range that *includes* language marking the passage as text-reuse (*verbum dicendi*, etc.)
- **TextContent** - a string containing the precise textual content, from Athenaeus, that is reused; this will exclude *verba dicendi*, etc.
- [may be empty; only for extant works] **Analytical Edition URN** - a CTS URN attaching the reused text (from Athenaeus) to the ordered, hierarchical citation scheme of the reused work.
- [may be empty; only for extant works] **Alignment URN** - a CTS URN specifying text in another edition of the reused work, used to assert an explicit alignment between Athenaeus' language and the language of another text. *E.g.* We see Athenaeus' use of βουλεύεσθαι at 1.18 as an allusion to βουληφόρε at *Iliad* 20.83; this is not a literal string match, nor are the two instances of the same lexical entity; we are asserting an alignment that is not discoverable by any automated process; the **alignment urn** allows us to make this alignment explicit.
- [may be empty] **Commentary**.
- **Resp**. The editor responsible for asserting the existence of, and documenting, this instance of text reuse.

**For reuses of works otherwise extant**: Where Athenaeus reuses text from extant works, which exist in other editions with citation schemes, we can produce an Analytical Edition of that work, the "Athenaeus Edition"; this edition can be cited by CTS URNs.

**For reuses of lost works**: For lost works, there is no citation scheme, nor any inherent order to the text. For these, we will produce a *collection* of text-reuse. This Collection can be cited by CITE URNs.


Contents of this repository are licensed under a Creative Commons Attribution-ShareAlike 4.0 International License http://creativecommons.org/licenses/by-sa/4.0/

