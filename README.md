# Found in Space on GitHub

This repository maintains the Found in Space organisation profile and shared
contributor guidance. Found in Space makes scientific data and models into
materials people can explore, question, and build with.

- **Looking for an experience or lesson?** Visit [foundin.space](https://foundin.space/).
- **Looking for code, data, or a place to contribute?** Use the [project guide](docs/projects.md).
- **Maintaining this repository?** The structure and GitHub behaviour are below.

## Repository structure

| File or directory | Responsibility |
| --- | --- |
| [`profile/README.md`](profile/README.md) | The public organisation Overview: mission, starting points, and routes into the projects. |
| [`docs/projects.md`](docs/projects.md) | The fuller project map, reusable package groups, and relationships between repositories. |
| [`docs/data-and-models.md`](docs/data-and-models.md) | Shared guidance on measurements, models, representations, provenance, and reuse. |
| [`CONTRIBUTING.md`](CONTRIBUTING.md) | Default contribution guidance across the organisation. |
| [`SUPPORT.md`](SUPPORT.md) | Where to ask for help and how to make a useful report. |
| [`SECURITY.md`](SECURITY.md) | Private reporting route for software vulnerabilities. |
| [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md) | Participation standards and a private reporting contact. |
| [`.github/ISSUE_TEMPLATE/`](.github/ISSUE_TEMPLATE/) | Default bug, improvement, and scientific/data concern forms, plus help links. |
| [`.github/PULL_REQUEST_TEMPLATE.md`](.github/PULL_REQUEST_TEMPLATE.md) | A short default prompt for the change, evidence, and validation. |
| [`AGENTS.md`](AGENTS.md) | Editing guidance for this repository. |

## How GitHub uses these files

GitHub displays `profile/README.md` on the organisation's public Overview.
The root README explains this repository. This is the
[documented organisation-profile layout](https://docs.github.com/en/organizations/collaborating-with-groups-in-organizations/customizing-your-organizations-profile).

Supported community files in this public `.github` repository provide defaults
when another repository in the organisation has no corresponding file. A local
community file takes precedence. A repository with its own issue templates or
issue-template configuration replaces the entire inherited issue-template set.
Defaults are displayed by GitHub and are not copied into downstream clones.
See [GitHub's default community-file rules](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file).

The issue forms do not depend on organisation-specific labels, issue types,
assignees, or project boards. Blank issues remain available for questions and
reports that do not fit a form. Shared community documents and templates use
absolute links so they work when surfaced in a different repository.

`AGENTS.md`, `docs/`, workflows, and licences are not inherited through this
community-file mechanism. Product-specific setup, release procedures, and
licensing belong in their owning repositories. A security policy documents a
reporting route; it does not enable GitHub's private vulnerability reporting
feature. The email route in `SECURITY.md` works independently of that setting.

## Maintaining the public map

Keep the profile brief and centred on what someone wants to do. Put the fuller
inventory and relationships in `docs/projects.md`, and API details in the
product repositories. New projects should receive a clear place in that map;
they need a profile entry only when they add a useful starting point.

Before changing descriptions or links:

1. Check the organisation's current public repositories and the product's
   current documentation. Where a README is behind the implementation, verify
   the specific capability rather than repeating the old description.
2. Distinguish published packages, development APIs, experiments, and private
   work. Keep private source URLs and internal coordination material out of
   public documents.
3. Check the relative links and heading anchors, YAML form syntax, and public
   destinations. Review the profile as an organisation landing page and the
   templates as defaults for other repositories.
4. Update the project guide's review date after checking its coverage. Keep the
   shared direction consistent: exploration, questioning, and building all
   matter, and the evidence behind a representation remains accessible.

This repository contains Markdown and GitHub templates; there is no application
build. Open issues here for the organisation profile, shared documentation, or
help finding the right repository. Product issues belong in their product repo.
