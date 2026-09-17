# Working with data and models

Found in Space's materials should help people understand both a phenomenon
and the basis for its representation. These principles apply when building an
experience, proposing a scientific correction, or reusing a dataset.

## Explain what a value represents

Keep the distinction visible between:

- **Measurements:** observations made by an instrument or recorded by a source.
- **Derived quantities:** values calculated or inferred from measurements, such
  as a distance estimate or an absolute magnitude.
- **Model predictions:** results calculated from assumptions and inputs, such
  as orbital positions or eclipse circumstances.
- **Simplified simulations:** deliberately reduced models for investigating
  behaviour, with a stated range of useful interpretation.
- **Representations:** choices about scale, colour, projection, visibility, or
  musical mapping that make the material perceptible.

A representation may combine several of these. Make the distinctions available
at a useful depth without requiring visitors to read implementation details
before enjoying the experience.

## Keep the context needed to reuse the material

Record the source and version, units, coordinate frame, time convention, and
relevant transformations. Explain uncertainty, selection effects, missing data,
and model limits where they affect interpretation. A missing observation should
not silently become zero; a historical example should not be presented as live.

Use stable catalogue identifiers, published references, or dataset versions
when reporting an unexpected result. For a time-dependent calculation, include
the date, time standard, observer location, and relevant model inputs.

## Make transformations replayable

For a dataset build or scientific comparison, retain the exact code revision,
configuration, source versions or hashes, and the commands needed to reproduce
it. Keep generated manifests, counts, and checksums tied to the final outputs.
Regenerate evidence with its owning tools instead of editing generated records
by hand.

The stellar stack separates responsibilities: `pipeline` owns catalogue
processing and merge policy; `octree` owns spatial packaging; `catalogs` holds
publication evidence; application packages own their interpretation and view.
Fix the responsible stage and describe downstream effects. See the
[project map](projects.md#data-evidence-and-delivery) and each repository's
contracts for the details.

For published catalogue releases, follow the catalogue release process and pin
public upstream code by exact commit. Experimental results from a dirty or
locally modified dependency need to remain distinguishable from release
evidence.

## Compare the right things

Separate a rendering choice from a scientific discrepancy. Check units,
reference frames, epochs, observer assumptions, source selection, and model
approximations before concluding that two outputs disagree physically.

Use reference data and meaningful tolerances when validating calculations.
Report the reference's own assumptions and limits. A test that only repeats the
implementation's calculation does not independently establish accuracy.

For an artistic mapping, explain the mapping choices and what a listener or
viewer can reasonably infer. Reusing the same measurements with a different
representation can itself be a useful experiment.

## Make learning and making possible

Offer an appropriate next step: an explanation, a question to investigate, a
small editable example, or a documented component. Exploring, questioning, and
building can each be a complete activity. Play may generate a question before
there is a formal investigation to structure.

Describe the intended learning opportunity. Claims about educational
effectiveness, age suitability, or classroom readiness need supporting evidence.

## Respect source terms and privacy

Code, catalogue data, publications, imagery, and artwork can have different
licences. Read the owning repository's licence, notices, references, and
publication-specific terms before redistributing material. Cite scientific
sources and preserve required attribution.

Use small, shareable examples for public reports. Keep credentials, private
service addresses, personal data, and restricted source material out of issues,
logs, and committed evidence. Large source downloads and generated payloads
belong in the project's documented storage and publication process.
