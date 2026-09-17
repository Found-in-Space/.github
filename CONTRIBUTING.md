# Contributing to Found in Space

Found in Space makes scientific data and models into materials people can
explore, question, and build with. Contributions can improve a reusable tool,
the evidence behind a result, or someone's ability to understand and use it.

Code, documentation, examples, scientific checks, accessibility improvements,
teaching material, and reproducible bug reports are all useful contributions.

## Choose the owning project

Use the [project guide](https://github.com/Found-in-Space/.github/blob/main/docs/projects.md)
to find the repository for your change. Follow that repository's README,
contribution guidance, and `AGENTS.md` where present. Its specific instructions
take precedence over these shared defaults.

For an organisation-profile or shared-documentation change, use
[Found-in-Space/.github](https://github.com/Found-in-Space/.github). If ownership
is unclear, an issue there is a reasonable place to start.

Search existing issues and pull requests before starting. Small fixes can go
directly to a pull request. For a substantial new capability, public API change,
or change to scientific interpretation, open an issue describing the use case
and proposed approach before investing in a large implementation.

## Work from a reproducible starting point

Fork or branch the owning repository and follow its documented setup. The
projects have different toolchains and release states; use the commands and
lockfile belonging to that repository rather than assuming one setup fits all.

Use a small example or fixture when possible. Check the configuration, intended
outputs, storage needs, and evidence capture before running large downloads or
full dataset builds. Keep secrets and private configuration out of the change.

## Make a focused change

Explain who the change helps and what they will be able to do. Keep unrelated
refactoring separate. Update the relevant documentation or example when user
behaviour, an API, or a data contract changes.

For scientific and data work, read
[working with data and models](https://github.com/Found-in-Space/.github/blob/main/docs/data-and-models.md).
Include sources, assumptions, units, input versions, and suitable comparisons.
Distinguish measurements, derived values, predictions, and presentation choices.
Preserve provenance and use the owning tools to regenerate evidence.

For learning material, describe the audience and activity, leave room for
exploration and making, and make the evidence behind the view available. State
what the material is intended to help people learn without claiming outcomes
that have not been evaluated.

## Validate and open a pull request

Run the checks documented for the affected part of the project. For a behaviour
change, add or update meaningful tests or scientific comparisons. For
documentation changes, check links, examples, and any relevant rendering.

The pull request should explain:

- the problem or opportunity and the resulting behaviour;
- the scope, including any affected packages or downstream consumers;
- how it was checked, with commands or other evidence and any checks not run;
- sources, data versions, assumptions, or compatibility changes when relevant.

For visual or interactive changes, a screenshot or short recording can help
reviewers understand the result. Describe accessibility and device behaviour
where the change affects them. Follow the repository's changelog and release
instructions rather than inventing a separate release process.

You remain responsible for the correctness, provenance, and rights of a
contribution, including material prepared with automated tools. Explain how you
validated it; do not submit private data or credentials in generated output.

## Licensing and community

Check the owning repository's licence and any separate data, asset, or
publication terms. Only contribute material you have the right to share under
the relevant terms, and preserve source attribution.

Follow the [code of conduct](https://github.com/Found-in-Space/.github/blob/main/CODE_OF_CONDUCT.md).
Use [support guidance](https://github.com/Found-in-Space/.github/blob/main/SUPPORT.md)
for help, and [private security reporting](https://github.com/Found-in-Space/.github/blob/main/SECURITY.md)
for vulnerabilities.
