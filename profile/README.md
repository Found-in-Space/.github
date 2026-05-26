# Found in Space

**Explore the nearby stars. Learn from the data behind the view.**

Found in Space turns real astronomical measurements into interactive 3D experiences, lessons, games, and tools for making new journeys through the solar neighbourhood.

It starts with open catalogues from ESA's [Gaia mission](https://www.cosmos.esa.int/web/gaia), Hipparcos, and other sources. From there, the whole process stays visible: how raw measurements become cleaned star data, how that data is indexed for the browser, how the viewer renders it, and how the result can become something you can fly through, question, teach with, or build on.

The project is part planetarium, part classroom, part open data lab. The aim is not just to show a beautiful sky, but to help people ask why the sky looks that way, what the data can and cannot show, and how measurements become understanding.

Start at **[foundin.space](https://foundin.space)**.

## Featured projects

### Found in Space

The main site is the public front door: guided visualisations, lessons, teaching material, build guides, and open technical notes. Start with Orion, parallax, the HR diagram, star clusters, or the radio bubble, then follow the data behind the scene.

Links: [foundin.space](https://foundin.space) · [GitHub repo](https://github.com/Found-in-Space/found-in-space.github.io)

### Star Pilot

Star Pilot is the playful side of the same data. It streams Gaia-derived stars into a 2D slice of the solar neighbourhood and lets you pilot a small ship through real local space. It is game-like on purpose: a way to make stellar geography feel immediate, explorable, and playable.

Links: [foundin.space/star-pilot](https://foundin.space/star-pilot) · [GitHub repo](https://github.com/Found-in-Space/star-pilot)

### SkyKit Studio

SkyKit Studio is the video journey workshop. It lets authored `fis-journey-v1` explorations be previewed, edited, retimed, rendered, and exported as deterministic browser-captured videos. It is how the project can turn interactive star journeys into shareable explanations, lessons, and film-like tours.

Links: [foundin.space/skykit-studio](https://foundin.space/skykit-studio) · [GitHub repo](https://github.com/Found-in-Space/skykit-studio)

### Touch OS

Touch OS is a headless virtual-device UI runtime for scene-mounted panels, XR tablets, HUDs, cockpit displays, and other tool surfaces that live inside 3D applications.

Links: [foundin.space/touch-os](https://foundin.space/touch-os) · [GitHub repo](https://github.com/Found-in-Space/touch-os)

## The open stack

Everything here is inspectable. If you want to understand how the experiences are made, follow the data through the repositories.

### [pipeline](https://github.com/Found-in-Space/pipeline)

This is where the star map begins. The pipeline downloads and processes astronomical catalogues, merges Gaia with Hipparcos, handles difficult duplicate and bright-star cases, chooses working distance estimates, and produces the cleaned Parquet data used by the rest of the project.

### [octree](https://github.com/Found-in-Space/octree)

A browser cannot download a billion-row table. The octree tools turn the processed catalogue into a streaming spatial index, so nearby and visible stars can arrive as you move through the scene instead of all at once.

### [skykit](https://github.com/Found-in-Space/skykit)

SkyKit is the JavaScript viewer runtime for building interactive 3D sky experiences. It loads octree data, manages visible cells, renders stars, and provides the foundation for the website, experiments, and future tools.

### [stellarium-skycultures](https://github.com/Found-in-Space/stellarium-skycultures)

Constellation art and sky-culture data are packaged separately so the viewer can use familiar sky stories without hard-wiring them into the core runtime.

## Why open?

Found in Space is open because the process is part of the lesson. Seeing a star map is one thing; understanding how measurements, assumptions, uncertainty, and rendering choices shape that map is where the learning really starts.

The code, data pipeline, viewer runtime, authoring tools, and public site are here for anyone who wants to inspect them, teach with them, fork them, or use them as a starting point for a new data-driven experience.

## About

Found in Space is built by [Kaj Siebert](https://k-si.com), an astrophysicist by training who spent two decades in data science and technology before returning to the stars.

Data is a wonderful way to understand the universe, and the universe is a wonderful way to learn about data.
