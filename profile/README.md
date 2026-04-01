# Found in Space

Found in Space is an open educational project that takes real astronomical data — starting with ESA's [Gaia mission](https://www.cosmos.esa.int/web/gaia) and the Hipparcos survey — and turns it into something you can explore in a browser: a 3D map of the stars around our Sun, built from actual measurements.

The whole process is shared, from the raw catalogue downloads all the way through to the interactive viewer. If you're curious about any part of it — or just want to look at the stars — you're very welcome here.

You can visit the project at [foundin.space](https://foundin.space), or browse the repositories below to see how it all works.

## The repositories

The project is split across several repositories. They follow a natural sequence — each one feeds into the next — so the easiest way to understand the project is to follow the data as it moves through the system.

### [Found-in-Space/pipeline](https://github.com/Found-in-Space/pipeline)

This is where the data journey starts. The pipeline takes raw star catalogues from ESA's Gaia mission and the older Hipparcos survey, processes them (selecting distances, computing positions, assigning temperatures and magnitudes), cross-matches the two catalogues to resolve the roughly 100,000 stars that appear in both, and merges everything into a single clean dataset. The output is a set of HEALPix-partitioned Parquet files — one canonical row per star, with Sun-centred 3D coordinates in parsecs. The pipeline also handles a small number of manual overrides for stars like the Sun (which doesn't appear in either catalogue) and famous binaries where the automated matching struggles.

### [Found-in-Space/octree](https://github.com/Found-in-Space/octree)

A browser can't download a table with over a billion rows, so the merged star data needs to be repackaged for streaming. This repository converts the pipeline's Parquet output into a spatial octree — a tree that divides 3D space into nested cells across 14 levels. Each star is placed into a level based on its brightness: the brightest stars sit in the shallowest, largest cells, while the faintest go into the deepest, smallest ones. The threshold at each level is tuned to how far away a star of that brightness would still be visible to the human eye (defaulting to a naked-eye limit of magnitude 6.5). At runtime, the viewer loads cells level by level — bright-star cells have large visibility radii so they load from anywhere, while faint-star cells only load when the observer is nearby. The output is a compact binary file (`stars.octree`) along with optional sidecars for metadata like star names and identifiers.

### [Found-in-Space/skykit](https://github.com/Found-in-Space/skykit)

SkyKit is the viewer runtime — a JavaScript toolkit for building interactive 3D sky experiences. It handles loading octree data, managing what's visible, and rendering stars using WebGL shaders. It can be used as a standalone viewer for desktop or VR, or as a library for building custom visualisations. It's published on npm as `@found-in-space/skykit`.

### [Found-in-Space/website](https://github.com/Found-in-Space/found-in-space.github.io.git)

The public-facing site at [foundin.space](https://foundin.space), built with Astro and hosted on GitHub Pages. This is where the technical work becomes something people can actually use: guided explorations, learning content, and transparent documentation of how the data pipeline works. The site is structured around exploring the sky, learning about what you're seeing, and understanding how it was all built.

### Other repositories

- **[Found-in-Space/pipeline-dust](https://github.com/Found-in-Space/pipeline-dust)** — A companion to the main pipeline that builds a 3D interstellar dust map from the Rezaei Kh. et al. (2024) survey. The output is a compact binary in the same coordinate frame as the star data, ready for overlay in the viewer.

- **[Found-in-Space/stellarium-skycultures](https://github.com/Found-in-Space/stellarium-skycultures)** — Packaging workspace for constellation artwork derived from the Stellarium project. Each culture (currently Western) is published as a standalone npm package with embedded 3D anchor directions, keeping constellation art decoupled from the viewer itself.

## About the project

Found in Space is built by [Kaj Siebert](https://k-si.com) — an astrophysicist by training who spent two decades in data science and technology before returning to the stars. The aim is not just to publish code, but to share the whole process of turning astronomical measurements into something people can explore and learn from. Data is a wonderful way to understand the universe, and the universe is a wonderful way to learn about data.

If you have questions, suggestions, or ideas, they would be very welcome. You can find more context at [foundin.space](https://foundin.space).
