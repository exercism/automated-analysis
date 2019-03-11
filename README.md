# Automented Mentoring Support on Exercism

The Automated Mentoring Support Project is a long-term endeavour to support our mentors through the use of automated code analysis.

## Background

The project started in Febuary 2019. You can read the [blog post that launched it](https://exercism.io/blog/automated-mentoring-support-project) or the [About Document](./docs/about.md) for more information.

## Analyzers
- [Ruby](https://github.com/exercism/ruby-analyzer)

If you would like to create an analyzer for a different language, please follow the [these instructions](./docs/creating-an-analyzer.md).

If you would like to get involved in an existing analyzer, please open an issue in that repository asking if there is somewhere you can help.

## The Interface

Analyzers are responsible for analyzing code. The are managed by an orchestrator and must adhere to an interface, which is [defined here](./docs/interface.md).

## Copyright

All content in this repository is Copyright to Exercism and licenced under MIT.
