# Find your place in Found in Space

Found in Space makes scientific data and models usable for exploration,
investigation, and creation. Choose a starting point by what you want to do;
you can use a focused package without adopting the whole stack.

Public repository coverage reviewed on **17 September 2026**. Project maturity
and API stability vary; each repository's releases and documentation are the
authority for what is available. This guide describes roles rather than pinning
versions. [Browse the organisation](https://github.com/orgs/Found-in-Space/repositories)
for subsequent additions.

## Tools and experiences

| Project | What it is for | Where to begin |
| --- | --- | --- |
| [SkyKit](https://github.com/Found-in-Space/skykit) | Compose applications from packages for astronomical data access, analysis, 2D maps, 3D rendering, and spatial interaction. | [Public lessons](https://foundin.space/learn-build/skykit/) and the repository's package guides. |
| [Pas de Géant](https://github.com/Found-in-Space/pas-de-geant) | Explore scale and motion in a WebXR Solar System, with Earth and Moon surfaces, other major bodies, satellite layers, and an Eclipse Observatory. | The [application guide](https://github.com/Found-in-Space/pas-de-geant/blob/main/apps/pas-de-geant/README.md) covers setup and current capabilities. A desktop fallback is available. |
| [Shadowline](https://github.com/Found-in-Space/shadowline) | Calculate solar-eclipse geometry and local circumstances, export map data, and explore the result from different viewpoints. | The repository's package example and [browser explorer](https://foundin.space/shadowline/browse/). It is an early alpha; consult its accuracy and validation notes. |
| [SkyKit Studio](https://github.com/Found-in-Space/skykit-studio) | Author, preview, edit, retime, and export journeys through astronomical scenes. | The README and editor examples; Studio consumes SkyKit and owns journey authoring and video export. |
| [Touch OS](https://github.com/Found-in-Space/touch-os) | Build interactive surfaces for 3D scenes: panels, tablets, wrist displays, and cockpit tools. | The README's core runtime and Three.js host examples. The runtime is domain-neutral and can be used outside astronomy. |
| [Star Pilot](https://github.com/Found-in-Space/star-pilot) | Explore a slice of Gaia-derived stars through a small piloting game. | The README and [browser demo](https://foundin.space/star-pilot/). Its game representation makes deliberate choices about star visibility and brightness. |

### Aeolian Measure: in private development

Aeolian Measure turns measured systems into structured music through explicit
analysis, mapping, and composition. It extends the same mission into listening
and musical creation. Its source is currently private, so there is no public
repository or contribution route to link here yet.

## Reusable package groups

Repository names are only one level of the ecosystem. These package groups help
you choose a smaller piece to work with. Follow the linked READMEs for current
installation, release status, examples, and API boundaries.

| Need | Packages or entry points |
| --- | --- |
| Coordinates, poses, and navigation | SkyKit's [`spatial`](https://github.com/Found-in-Space/skykit/tree/main/packages/spatial). |
| Stream and inspect star data | [`star-octree-provider`](https://github.com/Found-in-Space/skykit/tree/main/packages/star-octree-provider), [`star-trees`](https://github.com/Found-in-Space/skykit/tree/main/packages/star-trees), and [`meta-sidecar-provider`](https://github.com/Found-in-Space/skykit/tree/main/packages/meta-sidecar-provider). |
| Draw or analyse a stellar sample | [`star-map-canvas`](https://github.com/Found-in-Space/skykit/tree/main/packages/star-map-canvas), [`three-star-field`](https://github.com/Found-in-Space/skykit/tree/main/packages/three-star-field), and [`hr-diagram`](https://github.com/Found-in-Space/skykit/tree/main/packages/hr-diagram). |
| Place images in a sky view | [`anchored-image`](https://github.com/Found-in-Space/skykit/tree/main/packages/anchored-image) and the assets from Stellarium Skycultures. |
| Compose a viewer | [`skykit`](https://github.com/Found-in-Space/skykit/tree/main/packages/skykit), including its documented optional XR helpers. |
| Calculate eclipse geometry | [`shadowline`](https://github.com/Found-in-Space/shadowline/tree/main/packages/shadowline) with the separate [`shadowline-astronomy-engine`](https://github.com/Found-in-Space/shadowline/tree/main/packages/shadowline-astronomy-engine) astronomical provider. |
| Create virtual tool surfaces | Touch OS's core, components, services, and explicit host adapters. |

Development-branch documentation may describe APIs ahead of a published
package. Match the documentation and examples to the release you install.

## Data, evidence, and delivery

| Repository | Responsibility |
| --- | --- |
| [pipeline](https://github.com/Found-in-Space/pipeline) | Download and process Gaia, Hipparcos, supporting identifiers, and curated corrections into the canonical merged HEALPix Parquet view. |
| [octree](https://github.com/Found-in-Space/octree) | Turn merged Parquet into bounded-memory spatial builds, streamable star artifacts, and supporting sidecars. |
| [catalogs](https://github.com/Found-in-Space/catalogs) | Maintain citable, versioned catalogue publications with provenance, manifests, checksums, and build evidence. |
| [pipeline-dust](https://github.com/Found-in-Space/pipeline-dust) | Prepare interstellar dust and H-alpha volume products. Check compatibility with the intended viewer; volume integrations are separate from the current SkyKit package learning path. |
| [stellarium-skycultures](https://github.com/Found-in-Space/stellarium-skycultures) | Package constellation artwork, anchors, and sky-culture resources for applications. The Western skyculture has a published package; consult the repository for other cultures' status and upstream terms. |
| [infra](https://github.com/Found-in-Space/infra) | Manage shared delivery infrastructure, including public DNS, object storage, certificates, and CDN configuration. |

The main stellar processing path is:

```text
Source catalogues, identifiers, and curated corrections
  -> pipeline: merged HEALPix Parquet
  -> octree: spatial artifacts and sidecars
  -> SkyKit: data access, analysis, and rendering
  -> applications, lessons, and authored journeys
```

`catalogs` preserves publication inputs and evidence. `infra` provides shared
delivery services. These are supporting responsibilities, not extra processing
stages that every application must run. Eclipse calculations, planetary models,
UI tools, and music also have their own inputs and can be used independently of
the stellar stack.

For reuse and scientific contributions, read
[working with data and models](data-and-models.md). Record the exact data and
code versions you use and follow the relevant licences and attribution terms.

## Website and shared documentation

| Repository | Responsibility |
| --- | --- |
| [found-in-space.github.io](https://github.com/Found-in-Space/found-in-space.github.io) | The public website at [foundin.space](https://foundin.space/): experiences, teaching material, explanations, and routes into building. |
| [.github](https://github.com/Found-in-Space/.github) | This developer entry point, the project map, and default contribution, support, security, and conduct guidance. |

## Related projects

These projects share an approach and remain separately maintained repositories:

- [Galaxy-JS](https://github.com/kws/galaxy-js): a simplified gravitational
  simulation for exploring how physical rules produce galactic encounters.
- [CERN map overlays](https://github.com/kws/cern-map-overlay): reusable map
  overlays that connect accelerator dimensions to familiar places.

## Contribute or ask for help

Start in the repository that owns the code, data, or experience. If ownership
is unclear, open an issue in [this repository](https://github.com/Found-in-Space/.github/issues).
Use the [contribution guide](https://github.com/Found-in-Space/.github/blob/main/CONTRIBUTING.md)
or [support guide](https://github.com/Found-in-Space/.github/blob/main/SUPPORT.md)
for the next step.
