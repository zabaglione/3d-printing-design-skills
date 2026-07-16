# 3D Printing Design Skills

Reusable agent skills for designing functional polymer 3D prints, the joints that connect them, and the physical textures that shape their surfaces and structures.

This repository captures transferable design workflows rather than product-specific recipes. The skills treat geometry, material condition, print process, orientation, toolpaths, fit calibration, production operations, and physical validation as one engineering system.

## Included skills

### `design-functional-3d-prints`

Turn functional requirements into parametric, process-aware parts. Covers load paths, orientation, walls, ribs, bosses, holes, first layers, and a universal decision flow for self-supporting redesign, bridges, splits, slicer-generated support, custom CAD support, secondary support materials, and process changes.

### `design-3d-printed-joints`

Select and validate reusable joint families. Covers pins, keys, fins, tongue-and-slot joints, dovetails, snap-fits, compliant clips, bayonets, threads, fasteners, inserts, adhesives, magnets, hinges, ball joints, large-panel joints, and print-in-place mechanisms.

### `design-3d-printable-textures`

Choose, generate, map, bake, and validate physical textures. Covers swept curves, repeated motifs, cellular structures, height-field relief, curved-surface mapping, protected regions, slicer roughness, mesh complexity, and the boundary between printable geometry and appearance-only maps. Buildability and support decisions route through the functional-print skill instead of being tied to named pattern examples.

## Core principles

- Design from measurable requirements and failure modes.
- Keep nominal geometry separate from process compensation.
- Choose part split and print orientation together.
- Redesign for self-support before accepting support; when support remains, choose slicer-generated, custom CAD, secondary-material, split, or process-change strategies from measurable production requirements.
- Separate locating, load transfer, retention, stop, and assembly functions.
- Never assume one clearance works across printers, materials, profiles, sizes, or orientations.
- Use representative fit coupons and record the qualified process.
- Convert strength and tolerance claims into representative, repeatable tests.
- Treat bump, normal, color, and material maps as appearance until required relief is baked into supported manufacturing geometry.
- Inspect the sliced build and validate the physical part before making performance claims.

## Research basis

The guidance synthesizes reusable principles from production-oriented modeling examples by [Slant 3D](https://www.youtube.com/@slant3d), controlled engineering tests and texturing tools by [CNC Kitchen](https://www.youtube.com/@CNCKitchen), replacement-part reconstruction and iterative field testing by [Need It Make It](https://www.youtube.com/@NeedItMakeIt), joint-design examples found through the requested YouTube search, official geometry-tool documentation, manufacturing file specifications, and manufacturer engineering references. Source notes are included inside each skill. No creator-specific dimensions or headline results are presented as universal rules.

## Install

Clone the repository and copy any skill directory into your Codex skills directory:

```bash
git clone https://github.com/zabaglione/3d-printing-design-skills.git
mkdir -p ~/.codex/skills
cp -R 3d-printing-design-skills/skills/design-functional-3d-prints ~/.codex/skills/
cp -R 3d-printing-design-skills/skills/design-3d-printed-joints ~/.codex/skills/
cp -R 3d-printing-design-skills/skills/design-3d-printable-textures ~/.codex/skills/
```

Restart or reload Codex after installation.

## Example prompts

```text
Use $design-functional-3d-prints to decide whether this part should be redesigned, reoriented, split, bridged, supported by the slicer, or given custom CAD support.
```

```text
Use $design-3d-printed-joints to compare a dovetail, snap-fit, and screw joint for a serviceable enclosure.
```

```text
Use $design-3d-printable-textures to add printable tactile relief to a curved enclosure without disturbing its fits or bed-contact face.
```

## Scope

The skills provide design reasoning and validation workflows, not certification. Safety-critical, pressure, lifting, medical, food-contact, vehicle, and protective-equipment applications require appropriate domain engineering, standards, testing, and independent review.

## License

MIT. See [LICENSE](LICENSE).
