---
title: 'Reference'
---

## Glossary

This glossary collects terms used throughout the training, with the definitions given where each term is introduced.

Ontology
: A formal, explicit specification of a shared conceptualisation. See [Introduction to ontologies](../episodes/introduction-to-ontologies.md).

Conceptualisation
: A model of the things and relationships relevant to a domain, or area of interest.

RDF (Resource Description Framework)
: A W3C standard data model that expresses descriptions and links as statements (triples) about resources. See [Linked Data Foundations](../episodes/linked-data-foundations.md).

Triple
: A single RDF statement with a subject (what is described), a predicate (the property or relationship), and an object (what it relates to, or a value).

IRI (Internationalized Resource Identifier)
: A name used in RDF to identify a resource consistently across datasets.

Linked Data
: An approach to publishing structured data on the Web, using Web identifiers, HTTP(S) lookups, RDF descriptions and links to other identifiers, so that related information can be found by following links.

Knowledge graph
: A representation of things and their relationships in a graph data model; this course covers knowledge graphs that use RDF and follow Linked Data principles.

Class
: In OWL, a kind of thing, such as Bicycle or Frame.

Individual
: In OWL, a particular thing; an instance of a class, such as B001 as an instance of Bicycle.

Object property
: A property that represents a relationship between individuals, such as "has component".

Datatype property
: A property that links an individual to a data value, such as "has material".

Literal
: A data value in the object position of an RDF triple, with a datatype that tells applications how to interpret its written value.

OWL (Web Ontology Language)
: A W3C standard, built on RDF, for representing ontologies on the Web so that applications can exchange and reason over them. See [Logical modelling in OWL](../episodes/logical-modelling-in-owl.md).

Reasoner
: Software that uses OWL reasoning to check consistency and class satisfiability and to infer additional statements from an ontology and its data, such as HermiT.

Open-world assumption (OWA)
: The assumption, made by OWL, that a statement can be true even when it has not been recorded or inferred; absence of a statement does not mean it is false.

Axiom
: A statement that an ontology asserts to hold, such as a subclass statement or a class equivalence.

Restriction
: A class expression that describes individuals through a property, such as `hasComponent some Frame`.

Entailment
: A statement that follows logically in every model of an ontology and its data.

Consistency
: A property of an ontology meaning that at least one model exists in which all its axioms hold together.

Class satisfiability
: The property that a class can have a member in some model, even in a consistent ontology.

SPARQL
: A query language for RDF data, used to match patterns of statements and retrieve the information they contain. See [Linked Data Foundations](../episodes/linked-data-foundations.md).

SHACL (Shapes Constraint Language)
: A W3C standard for validating RDF graphs against chosen requirements, expressed as shapes.

Triple store
: A database for storing and querying RDF, often exposing a SPARQL endpoint.

Competency question
: A question that an ontology, together with relevant data, should help answer; used to scope and check the coverage of a model. See [Design your own ontology](../episodes/design-your-own-ontology.md).

IRI strategy
: A consistent pattern for creating ontology, term and individual identifiers, including a maintainable Web domain and HTTPS.

## W3C standards and guides

The training uses RDF 1.1, OWL 2 and SPARQL 1.1. Start with the primers; consult the specifications for definitions and details.

### Primers and guides

| Reference | Use it for |
|---|---|
| [RDF 1.1 Primer](https://www.w3.org/TR/rdf11-primer/) | An introduction to RDF with examples |
| [OWL 2 Primer](https://www.w3.org/TR/owl2-primer/) | An introduction to OWL with examples |
| [OWL 2 Document Overview](https://www.w3.org/TR/owl2-overview/) | A guide to the OWL specifications |
| [OWL 2 Quick Reference](https://www.w3.org/TR/owl2-quick-reference/) | A summary of OWL constructs |
| [OWL 2 Manchester Syntax](https://www.w3.org/TR/owl2-manchester-syntax/) | Readable OWL syntax used in Protégé |
| [SKOS Primer](https://www.w3.org/TR/skos-primer/) | Concept schemes, labels and mappings |
| [SPARQL 1.1 Overview](https://www.w3.org/TR/sparql11-overview/) | A guide to queries, updates, protocols and result formats |

### Specifications

| Reference | Use it for |
|---|---|
| [RDF 1.1 Concepts and Abstract Syntax](https://www.w3.org/TR/rdf11-concepts/) | Resources, triples, graphs and datasets |
| [RDF Schema 1.1](https://www.w3.org/TR/rdf-schema/) | Classes, properties, domains and ranges |
| [RDF 1.1 Semantics](https://www.w3.org/TR/rdf11-mt/) | Interpretation and inference in RDF and RDFS |
| [OWL 2 Structural Specification and Functional-Style Syntax](https://www.w3.org/TR/owl2-syntax/) | OWL entities, expressions and axioms |
| [OWL 2 Direct Semantics](https://www.w3.org/TR/owl2-direct-semantics/); [OWL 2 RDF-Based Semantics](https://www.w3.org/TR/owl2-rdf-based-semantics/) | Formal meaning of OWL statements |
| [OWL 2 Mapping to RDF Graphs](https://www.w3.org/TR/owl2-mapping-to-rdf/) | Representing OWL as RDF |
| [OWL 2 Profiles](https://www.w3.org/TR/owl2-profiles/) | Restricted forms of OWL for different reasoning needs |
| [SKOS Reference](https://www.w3.org/TR/skos-reference/) | Concept schemes, labels, hierarchies and mappings |
| [SPARQL 1.1 Query Language](https://www.w3.org/TR/sparql11-query/) | Querying RDF data |
| [SPARQL 1.1 Update](https://www.w3.org/TR/sparql11-update/) | Adding, changing and removing RDF data |
| [Shapes Constraint Language (SHACL)](https://www.w3.org/TR/shacl/) | Checking RDF data against conditions |
| [XSD 1.1 Part 2: Datatypes](https://www.w3.org/TR/xmlschema11-2/) | Datatypes for text, numbers, dates and other values |

### File formats

| Reference | Use it for |
|---|---|
| [RDF 1.1 Turtle](https://www.w3.org/TR/turtle/) | Compact graph syntax used in the training's `.ttl` files |
| [RDF/XML](https://www.w3.org/TR/rdf-syntax-grammar/) | XML syntax for RDF graphs |
| [JSON-LD 1.1](https://www.w3.org/TR/json-ld11/) | JSON-based linked data |
| [N-Triples](https://www.w3.org/TR/n-triples/) | Line-based graph syntax |
| [TriG](https://www.w3.org/TR/trig/) | Turtle-style dataset syntax, including named graphs |
| [N-Quads](https://www.w3.org/TR/n-quads/) | Line-based dataset syntax |
| [OWL 2 XML Serialization](https://www.w3.org/TR/owl2-xml-serialization/) | OWL-specific XML syntax, distinct from RDF/XML |

### Identifiers and publication

| Reference | Use it for |
|---|---|
| [Cool URIs for the Semantic Web](https://www.w3.org/TR/cooluris/) | Choosing identifiers that can be looked up on the web |
| [Best Practice Recipes for Publishing RDF Vocabularies](https://www.w3.org/TR/swbp-vocab-pub/) | Publishing ontologies and vocabularies |
| [Data on the Web Best Practices](https://www.w3.org/TR/dwbp/) | Identifiers, documentation, licensing and versioning |

## Optional guidance on ontology development {#ontology-development-guidance}

- [Ontology Development 101](https://protege.stanford.edu/publications/ontology_development/ontology101.pdf) (2001): process guidance on scope, reuse and iterative modelling. Its examples use older tools; this course uses OWL 2.
- [OBO Academy](https://oboacademy.github.io/obook/): community training on OWL and ontology curation, with a biological and biomedical focus. Its [SubClassOf versus EquivalentTo](https://oboacademy.github.io/obook/explanation/subClassOf-vs-equivalentTo/) explanation uses diagrams to compare the two axioms.

## Related work

### Books

- [Semantic Web for the Working Ontologist](https://www.sciencedirect.com/book/monograph/9780123859655/semantic-web-for-the-working-ontologist) (Allemang and Hendler, 2nd ed., 2011): worked examples of modelling with RDF, RDFS and OWL, and querying with SPARQL.
- [An Introduction to Ontology Engineering](https://people.cs.uct.ac.za/~mkeet/OEbook/) (Keet, 2nd ed., 2025): a more technical treatment of formal foundations and ontology development methods. The author's site also provides an earlier open edition.

### Ontology development methodologies

- [METHONTOLOGY](https://cdn.aaai.org/Symposia/Spring/1997/SS-97-06/SS97-06-005.pdf) (Fernández-López et al., 1997): a lifecycle approach using evolving prototypes, with evaluation and documentation throughout development.
- [NeOn](https://doi.org/10.1007/978-3-642-24794-1_2) (Suárez-Figueroa et al., 2012): guidance for different development scenarios, particularly reusing and combining existing knowledge resources.
- [LOT (Linked Open Terms)](https://lot.linkeddata.es/) ([Poveda-Villalón et al., 2022](https://doi.org/10.1016/j.engappai.2022.104755)): an iterative workflow covering requirements, implementation, publication and maintenance, with practical guidance and workflow diagrams.

## Bibliography

Works cited in the episodes, in alphabetical order by citation key. Each entry below is linked from the episode text, for example `(Studer et al., 1998)`.

### Allemang & Hendler, 2011 {#allemang2011semantic}

Allemang, D., & Hendler, J. (2011). *Semantic Web for the Working Ontologist: Effective Modeling in RDFS and OWL* (2nd ed.). Morgan Kaufmann. <https://doi.org/10.1016/C2010-0-68657-3>

### Berners-Lee, 2004 {#bernerslee2004connectingsciences}

Berners-Lee, T. (2004). *Connecting the Sciences* [Design Issues, personal design note]. <https://www.w3.org/DesignIssues/ConnectingScience.html>

### Grüninger & Fox, 1995 {#gruninger1995methodology}

Grüninger, M., & Fox, M. S. (1995). Methodology for the Design and Evaluation of Ontologies. In *IJCAI-95 Workshop on Basic Ontological Issues in Knowledge Sharing* (pp. 6.1–6.10). Montréal, Canada. <https://eil.mie.utoronto.ca/wp-content/uploads/enterprise-modelling/papers/gruninger-ijcai95.pdf>

### Gruber, 1993 {#gruber1993ontology}

Gruber, T. R. (1993). A translation approach to portable ontology specifications. *Knowledge Acquisition*, 5(2), 199–220. <https://doi.org/10.1006/knac.1993.1008>

### Hocker et al., 2020 {#hocker2020participatory}

Hocker, J., Schindler, C., & Rittberger, M. (2020). Participatory design for ontologies: a case study of an open science ontology for qualitative coding schemas. *Aslib Journal of Information Management*, 72(4), 671–685. <https://doi.org/10.1108/AJIM-11-2019-0320>

### Isaac & Summers (eds), 2009 {#isaac2009skosprimer}

Isaac, A., & Summers, E. (Eds.). (2009). *SKOS Simple Knowledge Organization System Primer* [W3C Working Group Note]. World Wide Web Consortium. <https://www.w3.org/TR/skos-primer/>

### Neuhaus & Hastings, 2022 {#neuhaus2022consensus}

Neuhaus, F., & Hastings, J. (2022). Ontology Development is Consensus Creation, Not (Merely) Representation. *Applied Ontology*, 17(4), 495–513. <https://doi.org/10.3233/AO-220273>

### Noy & McGuinness, 2001 {#noy2001ontology}

Noy, N. F., & McGuinness, D. L. (2001). *Ontology Development 101: A Guide to Creating Your First Ontology* (KSL-01-05). Stanford University. Also published as Stanford Medical Informatics report SMI-2001-0880. <https://protege.stanford.edu/publications/ontology_development/ontology101.pdf>

### Sauermann & Cyganiak (eds), 2008 {#sauermann2008cooluris}

Sauermann, L., & Cyganiak, R. (Eds.). (2008). *Cool URIs for the Semantic Web* [W3C Interest Group Note]. World Wide Web Consortium. <https://www.w3.org/TR/cooluris/>

### Studer et al., 1998 {#studer1998knowledge}

Studer, R., Benjamins, V. R., & Fensel, D. (1998). Knowledge engineering: Principles and methods. *Data & Knowledge Engineering*, 25(1–2), 161–197. <https://doi.org/10.1016/S0169-023X(97)00056-6>

### Suárez-Figueroa et al., 2009 {#suarezfigueroa2009requirements}

Suárez-Figueroa, M. C., Gómez-Pérez, A., & Villazón-Terrazas, B. (2009). How to Write and Use the Ontology Requirements Specification Document. In R. Meersman, T. Dillon, & P. Herrero (Eds.), *On the Move to Meaningful Internet Systems: OTM 2009* (LNCS vol. 5871, pp. 966–982). Springer. <https://doi.org/10.1007/978-3-642-05151-7_16>

### Uschold & King, 1995 {#uschold1995methodology}

Uschold, M., & King, M. (1995). *Towards a Methodology for Building Ontologies* (AIAI-TR-183). Artificial Intelligence Applications Institute, University of Edinburgh. <https://www.aiai.ed.ac.uk/publications/documents/1995/95-ont-ijcai95-ont-method.pdf>

### W3C OWL Working Group, 2012 {#w3c2012owl2overview}

W3C OWL Working Group. (2012). *OWL 2 Web Ontology Language Document Overview (Second Edition)* [W3C Recommendation]. World Wide Web Consortium. <https://www.w3.org/TR/owl2-overview/>

### Hitzler et al. (eds), 2012 {#w3c2012owl2primer}

Hitzler, P., Krötzsch, M., Parsia, B., Patel-Schneider, P. F., & Rudolph, S. (Eds.). (2012). *OWL 2 Web Ontology Language Primer (Second Edition)* [W3C Recommendation]. World Wide Web Consortium. <https://www.w3.org/TR/owl2-primer/>

### Hyland et al. (eds), 2014 {#w3c2014linkeddata}

Hyland, B., Atemezing, G. A., & Villazón-Terrazas, B. (Eds.). (2014). *Best Practices for Publishing Linked Data* [W3C Working Group Note]. World Wide Web Consortium. <https://www.w3.org/TR/2014/NOTE-ld-bp-20140109/>

### Lóscio et al. (eds), 2017 {#w3c2017dwbp}

Lóscio, B. F., Burle, C., & Calegari, N. (Eds.). (2017). *Data on the Web Best Practices* [W3C Recommendation]. World Wide Web Consortium. <https://www.w3.org/TR/2017/REC-dwbp-20170131/>

### Wilkinson et al., 2016 {#wilkinson2016fair}

Wilkinson, M. D., Dumontier, M., Aalbersberg, I. J., et al. (2016). The FAIR Guiding Principles for scientific data management and stewardship. *Scientific Data*, 3, 160018. <https://doi.org/10.1038/sdata.2016.18>

