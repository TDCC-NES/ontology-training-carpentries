---
title: "Reuse ontologies"
teaching: 15
exercises: 0
---

:::::::::::::::::::::::::::::::::::::: questions

- Why and when should you map an ontology to external ontologies and vocabularies?
- How do you find suitable ontologies and vocabularies, and suitable terms within them?
- What should you check before reusing a term, extending an ontology or building a new one?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: caution

### Under development

This chapter is being written. By the end of it, you will be able to:

- Explain why and when to map an ontology to external ontologies and vocabularies
- Find suitable ontologies and vocabularies, and suitable terms within them, using standard resources
- Compare mapping approaches and choose one that fits, including [SHACL-AF rules](https://www.w3.org/TR/shacl-af/#rules) for deriving RDF triples with terms from another ontology

::::::::::::::::::::::::::::::::::::::::::::::::

Reusing existing ontologies and vocabularies, and connecting your ontology to them.

## Reuse, extend or build

Before creating a new ontology, check which ontologies your research community uses and which terms the datasets you want to use already refer to. In RDF data, the class and property IRIs can identify those terms. You can reuse suitable terms, extend an existing ontology with missing concepts, or create new terms where existing models do not express the meaning you need. These choices can be combined ([Noy & McGuinness, 2001](../learners/reference.md#noy2001ontology)).

When assessing an existing ontology, check:

- Whether its definitions, relationships and logical statements fit your intended meaning and level of detail.
- Whether relevant research communities or collaborating projects use it.
- Whether documentation, a licence and information about maintenance and versions are available.

Read the definitions and logical statements behind a promising term: matching labels alone do not establish a match in meaning ([Lóscio et al., 2017](../learners/reference.md#w3c2017dwbp); [Hyland et al., 2014](../learners/reference.md#w3c2014linkeddata)).

## Import an ontology {#owl-imports}

An `owl:imports` statement brings another ontology's axioms into reasoning, including those of its imports. Using its term IRIs alone does not import their defining axioms. An import can refer to a particular version using its version IRI. See [ontology imports](https://www.w3.org/TR/owl2-syntax/#Imports).

<!-- TODO: Develop ontology imports here, with a short Protégé walkthrough using bicycle-example-data.ttl to import bicycle-ontology.ttl. Explain why definitions and instance data are separate, how to add and resolve the import using the local catalog, and how to inspect imported terms and reasoning results. -->

::::::::::::::::::::::::::::::::::::: keypoints

- Check whether existing ontologies or vocabularies can be reused or extended before building new terms; these approaches can be combined.
- Assess a candidate ontology's fit, community use, documentation, licence and maintenance before reusing its terms.
- Matching labels alone do not establish a match in meaning: read the candidate term's definitions and logical statements.
- `owl:imports` brings another ontology's axioms into reasoning; using its term IRIs in your data does not import those axioms by itself.
- This chapter is still being written; later versions will cover finding suitable terms and comparing mapping approaches in more depth.

::::::::::::::::::::::::::::::::::::::::::::::::
