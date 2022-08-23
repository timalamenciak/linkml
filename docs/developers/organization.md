# GitHub Organization

The LinkML project is organized in a modular fashion, and consists of different
components. Each component lives in its own GitHub repository. It may also be distributed
as a separate software package on sites like PyPI.

See the [github.com/linkml](https://github.com/linkml) organization on GitHub to browse all repos.

Note that for many LinkML users, there is no need to understand the overall organization.

## Core Packages

The two most important packages are `linkml` and `linkml-runtime`

* [linkml](https://github.com/linkml/linkml)
    - [generators](generators)
    - utilities for working with data
    - this documentation
* [linkml-runtime](https://github.com/linkml/linkml-runtime)
    - code needed by linkml python object models
    - utility code such as [schemaview](developers/manipulating-schemas)
    - includes metamodel (linkml_runtime.linkml_model)

If you are using LinkML in a Python environment, then as a general rule
you should only need `linkml` as a *developer dependency*. This is used for
things like compiling your schema to data classes. This is something the
package developer does prior to release, rather than at *runtime*.

The `linkml-runtime` package is designed to provide runtime support. If you develop
a Python project, then your generated data classes will have a runtime dependency
on this package

## The metamodel  

The metamodel and specification have their own dedicated repo:

* [linkml-model](https://github.com/linkml/linkml-model)
  - self-describing linkml datamodel
  - note that you should not use this module programmatically - use linkml_runtime.linkml_model

There are no programmatic dependencies on this repo. But note that the
python dataclasses generated from this are incorporated into linkml-runtime.

## Productivity utilities

* [linkml-project-template](https://github.com/linkml/linkml-project-template)
  - Project template for new LinkML datamodels
  - **NOTE** this may be replaced by a cookiecutter system soon
* [schema-automator](https://github.com/linkml/schema-automator)
  - tools for bootstrapping schemas
     - from unstructured TSVs
     - from OWL ontologies
     - from JSON-Schema
  - tools for inferring enum ontology mappings using OLS and BioPortal

Note that schema-automator depends on LinkML, but there are no dependencies from
the core package on schema-automator

## Working with different backends

* [linkml-solr](https://github.com/linkml/linkml-solr)
   - provides a way of compiling LinkML schemas to Solr schemas
   - runtime query bindings to Solr updates and queries 

## Additional packages

* [linkml-data-ops](https://github.com/linkml/linkml-dataops) **NEW**
  - extension to runtime to provide:
     - a change/patch API over data
     - a query API over data

## LinkML for other languages

### Javascript/Typescript

* [linkml-runtime.js](https://github.com/linkml/linkml-runtime.js)
* linkml-runtime-java (in progress)