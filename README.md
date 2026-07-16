# 3D Printing Design Skills

Reusable agent skills for designing functional polymer 3D prints and the joints that connect them.

This repository captures transferable design workflows rather than product-specific recipes. The skills treat geometry, material condition, print process, orientation, toolpaths, fit calibration, production operations, and physical validation as one engineering system.

## Included skills

### `design-functional-3d-prints`

Turn functional requirements into parametric, process-aware parts. Covers load paths, orientation, walls, ribs, bosses, holes, designed supports, first layers, material condition, production operations, export hygiene, slicer inspection, and evidence-driven validation.

### `design-3d-printed-joints`

Select and validate reusable joint families. Covers pins, keys, fins, tongue-and-slot joints, dovetails, snap-fits, compliant clips, bayonets, threads, fasteners, inserts, adhesives, magnets, hinges, ball joints, large-panel joints, and print-in-place mechanisms.

## Core principles

- Design from measurable requirements and failure modes.
- Keep nominal geometry separate from process compensation.
- Choose part split and print orientation together.
- Separate locating, load transfer, retention, stop, and assembly functions.
- Never assume one clearance works across printers, materials, profiles, sizes, or orientations.
- Use representative fit coupons and record the qualified process.
- Convert strength and tolerance claims into representative, repeatable tests.
- Inspect the sliced build and validate the physical part before making performance claims.

## Research basis

The guidance synthesizes reusable principles from production-oriented modeling examples by [Slant 3D](https://www.youtube.com/@slant3d), controlled engineering tests by [CNC Kitchen](https://www.youtube.com/@CNCKitchen), joint-design examples found through the requested YouTube search, and manufacturer engineering references. Source notes are included inside each skill. No creator-specific dimensions are presented as universal rules.

## Install

Clone the repository and copy either skill directory into your Codex skills directory:

```bash
git clone https://github.com/zabaglione/3d-printing-design-skills.git
mkdir -p ~/.codex/skills
cp -R 3d-printing-design-skills/skills/design-functional-3d-prints ~/.codex/skills/
cp -R 3d-printing-design-skills/skills/design-3d-printed-joints ~/.codex/skills/
```

Restart or reload Codex after installation.

## Example prompts

```text
Use $design-functional-3d-prints to design a wall-mounted sensor enclosure for FDM printing.
```

```text
Use $design-3d-printed-joints to compare a dovetail, snap-fit, and screw joint for a serviceable enclosure.
```

## Scope

The skills provide design reasoning and validation workflows, not certification. Safety-critical, pressure, lifting, medical, food-contact, vehicle, and protective-equipment applications require appropriate domain engineering, standards, testing, and independent review.

## License

MIT. See [LICENSE](LICENSE).
