---
title: "Property characteristics and identity"
teaching: 15
exercises: 0
---

:::::::::::::::::::::::::::::::::::::: questions

- How do property axioms such as subproperty and inverse relate properties to one another?
- What do domains and ranges entail for every use of a property?
- What do functional, symmetric and transitive characteristics mean for a reasoner?
- How do `owl:sameAs` and `owl:differentFrom` express identity and difference?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

By the end of this chapter, you will be able to:

- Distinguish assertions about particular individuals from axioms that describe a property's general behaviour.
- Use subproperty, inverse, equivalence and disjointness axioms to relate properties.
- Explain the consequences of functional, symmetric and transitive property characteristics.
- Use `owl:sameAs` and `owl:differentFrom` to state identity and difference explicitly.

::::::::::::::::::::::::::::::::::::::::::::::::

<a id="owl-assertions"></a>
In the initial OWL walkthrough, we recorded statements such as "B001 is a Bicycle" and "B001 has component F001". These *assertions* describe particular individuals through class memberships, relationships and values.

Here, property axioms describe a property's behaviour across all its uses. Class restrictions describe conditions on class members. The following examples are separate modelling choices using the course prefixes; keep `bike-logical.ttl` as saved in the preceding section.

## Relationships between properties {#owl-property-axioms}

Make hasFrame a more specific relationship than hasComponent:

```turtle
def:hasFrame a owl:ObjectProperty ;
    rdfs:subPropertyOf def:hasComponent ;
    rdfs:range def:Frame .

id:B001 def:hasFrame id:F001 .
```

This entails B001 hasComponent F001. A general component link alone does not entail the more specific hasFrame link. An inverse axiom supplies the opposite direction:

```turtle
def:hasComponent owl:inverseOf def:isComponentOf .
```

From B001 hasComponent F001, infer F001 isComponentOf B001. For equivalent properties, a link using either property also holds with the other. Disjoint properties cannot both link the same subject to the same object. Subproperties, equivalence and disjointness also apply to data properties, where the object is a data value. See [property axioms](https://www.w3.org/TR/owl2-syntax/#Object_Property_Axioms).

Domains and ranges apply to every use of a property. With Frame as the range of hasFrame, every object of a hasFrame relationship is inferred to be a Frame. A class restriction such as "every hasFrame value of a Bicycle is a Frame" applies to Bicycle subjects. Several domains or ranges all apply together; the [optional union example](define-classes-logically.md#owl-union-complement) shows how to express alternatives. See [domains and ranges](https://www.w3.org/TR/owl2-primer/#Domain_and_Range_Restrictions).

## Characteristics and identity

| Characteristic | Consequence | Possible relationship |
|---|---|---|
| Functional | Each subject has at most one filler | hasAssignedStorageBay in a fixed allocation |
| Symmetric | A link entails its reverse | sharesStorageWith |
| Transitive | Two consecutive links entail a direct link | isPartOf |

Functionality allows zero fillers. If a functional object property links one subject to two names, both names must identify the same individual. Stating that they differ makes the ontology inconsistent. For a functional data property, distinct values cause inconsistency. Data properties support functionality but none of the other characteristics in this table. See [property characteristics](https://www.w3.org/TR/owl2-primer/#Property_Characteristics).

Identity and difference can also be stated explicitly: `owl:sameAs` states that two names identify the same individual, so class memberships and property assertions about either name apply to both. `owl:differentFrom` states difference. Similarity or matching labels alone justify neither. See [assertions](https://www.w3.org/TR/owl2-syntax/#Assertions).

For changing configurations or repeated measurements, represent the observation context explicitly before imposing functionality or cardinality limits.

::::::::::::::::::::::::::::::::::::: keypoints

- Assertions describe particular individuals; property axioms describe a property's behaviour across all its uses.
- Subproperty, inverse, equivalence and disjointness axioms relate properties to one another and support additional inferences.
- Domains and ranges apply to every use of a property, supporting inference about the classes of subjects and objects.
- Functional, symmetric and transitive characteristics let a reasoner infer identity, reverse relationships or chained relationships.
- `owl:sameAs` and `owl:differentFrom` state identity and difference explicitly; neither follows automatically from similar labels or distinct identifiers.
- Represent changing configurations or repeated measurements as explicit observation contexts before relying on functionality or cardinality limits.

::::::::::::::::::::::::::::::::::::::::::::::::
