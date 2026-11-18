# Working with Ontologies

An open training on designing, building and publishing OWL ontologies for researchers, built with [The Carpentries Workbench][workbench]. Developed by the [TDCC-NES Ontology Engineers](https://tdcc.nl/nes/ontology-engineers/).

[Read the training](https://tdcc-nes.github.io/ontology-training-carpentries/). The training is a work in progress; see [Instructor Notes](https://tdcc-nes.github.io/ontology-training-carpentries/instructor/instructor-notes.html) for which episodes are still being written.

This lesson adapts the content of [TDCC-NES/ontology-training](https://github.com/TDCC-NES/ontology-training), originally built with [TeachBooks](https://teachbooks.io/), to The Carpentries Workbench ([sandpaper][workbench]) format.

## Preview locally

Follow [the sandpaper-docs instructions](https://carpentries.github.io/sandpaper-docs/) to install R and the `{sandpaper}` package, then from the repository root run, in R:

```r
sandpaper::build_lesson()
```

Open a browser or editor and look under the `site/docs` directory for the rendered pages. Rebuild after editing the source files.

## Credits

Content developed by Kathrin Füllenbach and Dani Metilli ([TDCC-NES](https://tdcc.nl/nes/), [TU Delft](https://www.tudelft.nl/)), adapted from [TDCC-NES/ontology-training](https://github.com/TDCC-NES/ontology-training). See [`CITATION.cff`](CITATION.cff) for how to cite this lesson.

Unless otherwise stated, the training content is licensed under [CC BY 4.0](LICENSE). You may share and adapt it, including commercially, with attribution, a link to the licence and an indication of changes.

## Contribute

[Open an issue](https://github.com/TDCC-NES/ontology-training-carpentries/issues) or submit a pull request. Episodes live in [`episodes/`](episodes/); data files used by the episodes are in [`episodes/data/`](episodes/data/) and figures in [`episodes/fig/`](episodes/fig/). Episode order and other lesson metadata are configured in [`config.yaml`](config.yaml).

For authoring and publishing instructions, see [The Carpentries Workbench documentation][workbench].

[workbench]: https://carpentries.github.io/sandpaper-docs/

