---
title: Setup
---

No prior experience with ontologies, RDF, OWL, the Semantic Web or programming is required to take this training. You don't need a use case of your own to get started: a shared running example (a bicycle inventory) is used throughout. All tools are introduced and installed as you go, in the episode where they are first needed, so no advance setup is required.

This page summarises the software used across the episodes, so you can install it ahead of time if you prefer, or come back to it if you hit a missing dependency.

## Data Sets

The Turtle, CSV and XML files used throughout the episodes are provided in [`episodes/data`](../episodes/data/) and linked directly from the relevant episode (for example, the [complete bicycle ontology](../episodes/data/bicycle-ontology.ttl)). No separate download is needed: follow the links in each episode as you reach them.

## Software Setup

::::::::::::::::::::::::::::::::::::::: discussion

### Details

All software below is free to install and works on Windows, macOS and Linux. Each tool is introduced in the episode where it is first used:

- [Build your ontology in OWL](../episodes/build-your-ontology-in-owl.md) introduces **[Protégé](https://protege.stanford.edu/)**, a desktop ontology editor, with the bundled **HermiT** reasoner. Follow the [Protégé installation instructions](https://protegeproject.github.io/protege/installation/).
- [Use and evaluate your ontology](../episodes/use-and-evaluate-your-ontology.md) introduces **[RMLMapper](https://github.com/RMLio/rmlmapper-java)** (which needs **Java 21 or newer**) for converting CSV data to RDF, and **[SHACL Play!](https://shacl-play.sparna.fr/play/validate)**, a browser-based SHACL validator that needs no installation.
- [Publish your ontology](../episodes/publish-your-ontology.md) introduces **[Python 3.12 or newer](https://www.python.org/downloads/)** with the **[pyLODE](https://github.com/RDFLib/pyLODE)** documentation generator, a **GitHub** account for hosting files on GitHub Pages, and **[curl](https://curl.se/)** for checking published RDF.

A plain text editor is useful throughout for inspecting Turtle (`.ttl`) files. You can also use AI assistance to help draft and revise ontologies.

:::::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::: spoiler

### Protégé (desktop ontology editor)

1. Download Protégé Desktop from the [Protégé website](https://protege.stanford.edu/).
2. Follow the [installation instructions](https://protegeproject.github.io/protege/installation/) for your operating system.
3. The example ontologies in this training were checked with HermiT 1.4.3.456, bundled with Protégé 5.6.7.

:::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::: spoiler

### Java and RMLMapper (for converting CSV to RDF)

1. Install [Java 21 or newer](https://learn.microsoft.com/en-us/java/openjdk/install) for your operating system.
2. Confirm the install by opening a terminal (macOS/Linux) or PowerShell (Windows) and running `java -version`.
3. Download the standalone RMLMapper JAR (the file ending in `-all.jar`) from the [RMLMapper 8.1.0 release](https://github.com/RMLio/rmlmapper-java/releases/tag/v8.1.0) and rename it `rmlmapper.jar`.

:::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::: spoiler

### Python and pyLODE (for generating ontology documentation)

1. Install [Python 3.12 or newer](https://www.python.org/downloads/).
2. Create and activate a virtual environment, then install pyLODE:

```sh
python -m venv .venv
source .venv/bin/activate   # On Windows PowerShell: .\.venv\Scripts\Activate.ps1
python -m pip install pylode==3.6.1
```

:::::::::::::::::::::::::::::::::::::::::::::::::
