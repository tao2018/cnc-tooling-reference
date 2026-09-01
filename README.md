# CNC Drawing Feature to Carbide Tool Selection Reference

This public technical reference helps process planners turn drawing callouts into a defensible carbide-tool list. It is an independent educational resource: it does not represent a machine shop, supplier, customer, or confidential production project.

The central rule is simple: select the tool from the **feature, tolerance, material and access condition together**. A large pocket and a narrow internal radius may share a setup, but they should rarely share the same cutter.

## A six-question drawing review

Before choosing diameter or coating, answer these questions:

1. Which datum controls the feature, and when will that datum be created?
2. Is the requirement dimensional, positional, form-related, surface-related, or a combination?
3. How much radial and axial access remains after the fixture and neighboring walls are considered?
4. Will the material smear, work-harden, abrade, chip, or retain heat at the cutting edge?
5. Can the feature be roughed and finished with separate edges, or does access force a compromise?
6. How will the result be inspected after the part is released from the fixture?

## Compact feature-to-tool map

| Drawing feature | Practical first choice | Selection logic | Common alternative rejected |
|---|---|---|---|
| Open aluminum pocket | 3-flute polished carbide end mill, uncoated or ZrN | Large flute space and a sharp edge reduce chip welding | A dense 5-flute steel geometry can recut packed chips |
| Deep heat-resistant-alloy cavity | 5-flute variable-pitch carbide rougher, AlTiN/AlCrN, corner radius | Tough edge, controlled engagement and stable axial cutting | A sharp aluminum cutter is vulnerable to notch wear and edge chipping |
| Thin wall or rib | Necked, short-flute semifinisher followed by a dedicated finisher | Cutting length stays short while reach clears the wall | A long general-purpose end mill adds bending without useful cutting edge |
| Tight internal radius | Undersized micro end mill with verified runout | Diameter is chosen from residual stock and corner access, not pocket volume | Forcing the rougher into the corner raises deflection and rubbing |
| H7/H8 bore | Carbide drill or helical roughing, then fine boring or reaming as justified | Position is established before diameter and finish are released | A drill alone cannot reliably correct entry runout or meet every bore tolerance |
| Cross-hole burr | Purpose-built back-chamfer or reverse-cut carbide tool | Controlled edge break can be inspected and repeated | Manual scraping creates inconsistent break size inside the bore |
| Sealing face | PCD face tool for non-ferrous material, positive wiper carbide for ferrous alloys | Tool material and insert geometry are matched to chemistry and finish | PCD is unsuitable for conventional cutting of iron-based alloys |

## Why tool diameter alone is not a tooling plan

Two cutters with the same nominal diameter can behave very differently. Flute count sets chip-space and tooth loading; helix affects axial force; coating changes friction and thermal behavior; edge preparation trades sharpness for strength; neck length provides reach but reduces stiffness; and the holder determines how much of the catalog accuracy survives at the spindle.

For micro features, measured runout can consume a meaningful share of the chip load. For thin walls, flute length beyond the actual axial engagement acts as unnecessary compliance. For abrasive laminates, tool material and coating dominate edge life even when cutting forces are low.

## Worked technical references

- [7075-T651 waveguide filter: thin iris walls and R0.6 cavity corners](https://axkxa.com/7075-t651-waveguide-filter-cnc-tooling-thin-iris-walls-cavity-corners/) shows why bulk roughing, wall semifinishing and micro-corner cleanup need separate carbide geometries.
- [AISI 8620 gerotor housing: epitrochoid bore and carburizing stock](https://axkxa.com/aisi-8620-gerotor-housing-cnc-tooling-epitrochoid-bore-carburizing-stock/) connects cutter selection to heat-treatment allowance and post-carburizing restoration.
- [Incoloy 800H tube-support grid: bore array and expansion slots](https://axkxa.com/incoloy-800h-tube-support-grid-cnc-tool-selection-bore-array-expansion-slots/) demonstrates checkerboard sequencing, work-hardening control and separate rough/fine bore tools.

More drawing-led case studies and multilingual tooling notes are maintained at the [CNC Precision Hub technical knowledge site](https://axkxa.com/technology/).

## Repository contents

- [`docs/drawing-to-carbide-tool-selection.md`](docs/drawing-to-carbide-tool-selection.md) — a longer decision workflow with holder, reach, coating and inspection gates.
- [`CONTRIBUTING.md`](CONTRIBUTING.md) — evidence and editorial rules for additions.

## Scope and safety

Values in this repository are educational starting points, not released manufacturing instructions. The approved drawing, machine limits, tool-maker data, workholding analysis and inspection plan remain authoritative. Hypothetical examples are labeled as such.

