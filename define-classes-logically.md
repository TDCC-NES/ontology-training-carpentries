---
title: "Define classes logically"
teaching: 20
exercises: 30
---

:::::::::::::::::::::::::::::::::::::: questions

- What are axioms, expressions and restrictions, and how does Manchester syntax express them?
- How do `SubClassOf` and `EquivalentTo` differ, and what are necessary versus necessary-and-sufficient conditions?
- How do you combine and separate classes using disjointness, intersection, union and complement?
- How do object-property restrictions such as `some`, `only` and `value` describe relationships?
- How does cardinality count distinct fillers, and how do qualified and unqualified counts differ?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

By the end of this chapter, you will be able to:

- Write class axioms using necessary (`SubClassOf`) and necessary-and-sufficient (`EquivalentTo`) conditions.
- Use object-property restrictions (`some`, `only`, `value`) and cardinality to describe relationships.
- Use disjointness, intersection, union and complement to combine and separate classes.
- Predict what a reasoner will and will not infer from a given restriction.

::::::::::::::::::::::::::::::::::::::::::::::::

We now use class expressions to state conditions for class membership. Our example defines classes that let a reasoner recognise frames with the material value `"steel"@en` and bicycles with those frames.

For the Protégé steps, open `bike-working.ttl` from the preceding chapter and use **File > Save as** to save a Turtle copy as `bike-logical.ttl`. Keep the prefixed-name display.

## Axioms, expressions and restrictions {#owl-axioms}

Our model already contains a subclass statement and B001's class membership:

```turtle
def:Bicycle rdfs:subClassOf def:Vehicle .
id:B001 a def:Bicycle .
```

These are *axioms*: statements the ontology asserts to hold. See [OWL building blocks](https://www.w3.org/TR/owl2-primer/#Modeling_Knowledge:_Basic_Notions).

We use the prefixes from the [previous Turtle example](build-your-ontology-in-owl.md#owl-turtle-example). For readable expressions, we also use *Manchester syntax*, the notation used in Protégé's class descriptions and DL Query:

```text
def:hasComponent some def:Frame
```

Read this as "has at least one component that is a Frame". `some` is a keyword; the property and class use our existing IRIs. Parentheses group expressions. The cheat sheet provides the corresponding Turtle patterns and links to the specification's construct names. See [Manchester syntax](https://www.w3.org/TR/owl2-manchester-syntax/).

An *expression* describes a class, property or range of data values. `def:Frame` is a simple class expression. The expression above is a *restriction*: it describes individuals through a property. An axiom can use that expression to describe or define a class.

## Necessary and sufficient conditions {#owl-conditions}

`and` combines conditions: an individual must satisfy each one. Data-property restrictions describe individuals through their data values. For example, `def:hasMaterial value "steel"@en` describes individuals with that material value.

Introduce `def:SteelFrame` for Frames with the material value `"steel"@en`. Following the [iterative workflow](design-your-own-ontology.md#ontology-development-workflow), we choose an axiom that expresses the agreed meaning and check its consequences on the example records.

Use `SubClassOf` to state necessary conditions. In **Entities > Classes**, keep **Asserted** mode, select `owl:Thing` and create `def:SteelFrame`. With it selected, use **+** beside **SubClass Of** and choose **Class expression editor**. Enter only the expression after `SubClassOf:` below, then confirm. See [editing class descriptions](https://protegeproject.github.io/protege/views/class-description/).

```text
Class: def:SteelFrame
    SubClassOf: def:Frame and (def:hasMaterial value "steel"@en)
```

Every SteelFrame must be a Frame and have this material value. These are *necessary conditions*: asserting that F001 is a SteelFrame lets the reasoner infer both facts, even if its material value has not been entered explicitly. Having those facts alone does not establish SteelFrame membership from this axiom.

Start HermiT, or synchronise it if already running. In **DL Query**, enter `def:SteelFrame`, select **Instances** and **Execute**: F001 should not appear.

If being a Frame with that material value is also sufficient for SteelFrame membership, use `EquivalentTo`. Remove the expression from **SubClass Of** and add it under **Equivalent To**, again using **Class expression editor**. The reasoner can then recognise matching frames:

```text
Class: def:SteelFrame
    EquivalentTo: def:Frame and (def:hasMaterial value "steel"@en)
```

This works in both directions. Every SteelFrame satisfies the expression, and every individual satisfying it is a SteelFrame. Together, the conditions are *necessary and sufficient*. The [cheat sheet](owl-2-cheat-sheet.md#owl-steelframe-turtle) shows the same definition in Turtle.

Synchronise HermiT and repeat the query: F001 should now appear.

Create `def:BicycleWithSteelFrame` under `owl:Thing`. Under **Equivalent To**, enter only the expression after `EquivalentTo:` below:

```text
Class: def:BicycleWithSteelFrame
    EquivalentTo: def:Bicycle and (def:hasComponent some def:SteelFrame)
```

A BicycleWithSteelFrame is a Bicycle with at least one SteelFrame component. F001 is a Frame with material `"steel"@en`, so the reasoner classifies it as a SteelFrame. B001 is a Bicycle with F001 as a component, so it is a BicycleWithSteelFrame.

Synchronise HermiT and query `def:BicycleWithSteelFrame` with **Instances** selected: B001 should appear. Save `bike-logical.ttl`; this working copy contains B001 and F001.

<a id="reasoning-example-files"></a>
To inspect all three inventory records, save the [reasoning definitions (owl2-reasoning.ttl)](data/owl2-reasoning.ttl), [inventory data](data/bicycle-inventory.ttl) and [catalog-v001.xml](data/catalog-v001.xml) in the same folder. Open `owl2-reasoning.ttl` through **File > Open** in a new window. It contains both class definitions above and imports the separate inventory records; the catalog resolves that import locally. Run HermiT and query `def:BicycleWithSteelFrame`: B001 should appear.

B002 has Frame component F002 with the value `"aluminium"@en`; B003 has Frame component F003 with no material recorded. Neither frame is inferred to be a SteelFrame, and neither is inferred to be outside that class. B002 and B003 likewise remain unclassified as BicycleWithSteelFrame: other material values or frames remain possible.

`some` requires a relationship to exist, even if its filler is unnamed. Asserting that B003 has some SteelFrame does not identify F003 as that frame; another frame could satisfy the condition.

This definition uses an exact text value: `"Steel"@en` and `"steel"@nl` are different values from `"steel"@en`.

## Combining and separating classes {#owl-class-expressions}

Use *disjointness* when shared membership would contradict the model. For example, Frame and Wheel describe separate kinds of component:

```turtle
def:Frame owl:disjointWith def:Wheel .
```

No individual can then be both a Frame and a Wheel. See [class axioms](https://www.w3.org/TR/owl2-syntax/#Class_Expression_Axioms).

:::::::::::::::::::::::::::::::::::::::: spoiler

### Intersection, union and complement (optional) {#owl-union-complement}

Class expressions combine conditions with `and`, `or` and `not`. For these examples, Wheel groups wheel components, CargoBicycle describes bicycles designed to carry extra loads, and Fatbike describes bicycles with unusually wide tyres.

| Manchester expression | Meaning |
|---|---|
| `def:CargoBicycle and def:Fatbike` | Individuals in both classes; an intersection |
| `def:Frame or def:Wheel` | Individuals in either class or both; an inclusive union |
| `def:Bicycle and not def:CargoBicycle` | Bicycles outside CargoBicycle; uses a complement |

Membership in a union need not establish which alternative holds. A complement expresses non-membership: absence of CargoBicycle membership alone does not establish `not CargoBicycle`.

Classes may overlap: a bicycle can be both a CargoBicycle and a Fatbike.

For the completed reasoning example above, query `def:Bicycle and not def:BicycleWithSteelFrame`: no instances should appear.

::::::::::::::::::::::::::::::::::::::::::::::::

## Describing relationships with restrictions {#owl-object-restrictions}

An object-property restriction describes individuals through their related individuals, called *fillers*.

| Manchester expression | What it says about a member |
|---|---|
| `def:hasComponent some def:Frame` | It has at least one Frame component |
| `def:hasComponent only def:Frame` | Every component it has is a Frame |
| `def:hasComponent value id:F001` | It has the particular component F001 |

`only` restricts all fillers, including any not yet recorded. It also holds for an individual with no fillers. To require at least one Frame and allow only Frames, combine both:

```text
(def:hasComponent some def:Frame) and (def:hasComponent only def:Frame)
```

Suppose B001 also has wheels and a cargo box as components. Using `hasComponent only Frame` would require them to be Frames too. A dedicated `def:hasFrame` property can express conditions about its frames alone. See [object restrictions](https://www.w3.org/TR/owl2-syntax/#Object_Property_Restrictions).

:::::::::::::::::::::::::::::::::::::::: spoiler

### Cardinality (optional) {#owl-cardinality}

*Cardinality* counts distinct fillers: the individuals related through a property. A *qualified* cardinality counts only fillers in a specified class:

| Manchester expression | Meaning |
|---|---|
| `def:hasComponent min 2 def:Wheel` | At least two distinct Wheel components |
| `def:hasComponent max 2 def:Wheel` | At most two distinct Wheel components |
| `def:hasComponent exactly 2 def:Wheel` | Both the minimum and maximum conditions |

These can describe an assembled study bicycle in its observation context. An *unqualified* restriction, such as `def:hasComponent exactly 2`, counts all components: a frame or cargo box would count towards that total too.

For example, suppose we add Wheel individuals W001 and W002 as B001's components. The reasoner can count them as two wheels when it knows they are different, for example from `id:W001 owl:differentFrom id:W002`. A minimum can also require further, unnamed wheels.

With a maximum of one Frame component for B001, the reasoner treats two Frame fillers as the same individual. Stating that they are different makes the ontology inconsistent. See [cardinality restrictions](https://www.w3.org/TR/owl2-syntax/#Object_Property_Cardinality_Restrictions).

::::::::::::::::::::::::::::::::::::::::::::::::

<a id="owl-restriction-demonstrations"></a>
For each optional demonstration below, reopen your saved `bike-logical.ttl`, containing B001 and F001, and save a separate Turtle copy. Each demonstration adds the classes, properties and individuals it needs. Start HermiT, then synchronise after each change; use **DL Query > Instances** for queries. Return to `bike-logical.ttl` afterwards.

::::::::::::::::::::::::::::::::::::::::: spoiler

### In Protégé: what only infers (optional)

Restrict B001's hasFrame links to members of Frame.

1. Create the object property `def:hasFrame`, leaving its domain and range unset. In **Individuals by class**, select B001 and use **+** beside **Types**, then **Class expression editor**, to add `def:hasFrame only def:Frame`.
2. Query `def:hasFrame some def:Frame`: B001 does not appear. `only` alone establishes no frame's existence.
3. Create `id:F004` under `owl:Thing` and add B001's object property assertion `def:hasFrame id:F004`. Query `def:Frame`: F004 now appears, although we never asserted its Frame membership. The `some` query now includes B001 too.

The restriction supplies F004's classification. It applies to this bicycle's hasFrame links; other components remain unrestricted by it.

:::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::: spoiler

### In Protégé: count distinct wheels and find a contradiction (optional)

1. Create `def:Wheel` under Component, then W001 and W002 as Wheel individuals with the `id:` prefix. Link B001 to both through `def:hasComponent`.
2. Query `def:hasComponent min 2 def:Wheel`: B001 does not appear yet. Select W001 and add W002 under **Different Individuals**. Repeat the query: B001 now appears. Two IRIs alone did not establish two distinct wheels.
3. Add `def:hasComponent max 1 def:Wheel` to B001's **Types** using **Class expression editor**. Synchronising now reports an inconsistent ontology: two known-different wheels cannot satisfy this maximum. Remove that last restriction and synchronise to restore consistency.

The two recorded wheels still do not establish `exactly 2`: additional wheels remain possible.

:::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: keypoints

- Axioms are statements the ontology asserts; expressions describe a class, property or data range, and restrictions describe individuals through a property.
- `SubClassOf` states necessary conditions; `EquivalentTo` states necessary and sufficient conditions that let a reasoner classify matching individuals automatically.
- Disjointness, intersection (`and`), union (`or`) and complement (`not`) combine and separate classes without requiring named individuals to decide between alternatives.
- `some`, `only` and `value` describe relationships through a property; `only` alone does not assert that any filler exists.
- Cardinality (`min`, `max`, `exactly`) counts distinct fillers; qualified cardinality counts only fillers of a given class, while unqualified cardinality counts all fillers.
- Missing information keeps classifications undetermined rather than false, consistent with OWL's open-world assumption.

::::::::::::::::::::::::::::::::::::::::::::::::
