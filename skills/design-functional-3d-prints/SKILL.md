---
name: design-functional-3d-prints
description: "Design robust, parametric, manufacturable parts for polymer 3D printing. Use when Codex needs to create, review, reverse-engineer, replace, or upgrade functional FDM/FFF, SLA, or SLS parts; determine whether geometry is printable; choose among self-supporting redesign, orientation, bridging, splitting, slicer-generated or painted support, custom CAD breakaway support, soluble interfaces, or another process; translate requirements into CAD; select walls, ribs, holes, bosses, clearances, materials, coupons, or a verification plan; or decide whether a model is ready to print."
---

# Design Functional 3D Prints

Turn functional requirements into editable CAD and a print-validation plan. Optimize the part, process, orientation, and test together instead of treating the mesh as the design.

## Load the relevant references

- Read [references/design-rules.md](references/design-rules.md) when choosing geometry, material, process, or orientation.
- Read [references/printability-and-supports.md](references/printability-and-supports.md) whenever a part contains overhangs, bridges, islands, internal ceilings, support-sensitive surfaces, or uncertain build orientation.
- Read [references/production-dfam.md](references/production-dfam.md) for repeatable FDM/FFF production, support-aware geometry, first-layer strategy, holes, text, and toolpath control.
- Read [references/reverse-engineering-and-field-validation.md](references/reverse-engineering-and-field-validation.md) when replacing a damaged or missing part, fitting an existing assembly, upgrading a mechanism, or evaluating service life.
- Read [references/evidence-driven-engineering.md](references/evidence-driven-engineering.md) when making strength, material, tolerance, or durability claims.
- Read [references/verification.md](references/verification.md) before declaring a design complete.
- Read [references/source-notes.md](references/source-notes.md) only when tracing the research basis or looking for visual examples.
- Use `$design-3d-printed-joints` when the part must split, assemble, move, or remain serviceable.

## Workflow

### 1. Write a measurable design brief

Record:

- function, failure consequence, and downstream effects of fragments, debris, leaks, or jams;
- envelope, keep-outs, datum surfaces, and mating interfaces;
- load direction, magnitude, duration, impact, temperature, moisture, UV, and chemicals;
- required life, assembly cycles, appearance, and post-processing;
- printer process, material, nozzle or optical resolution, layer profile, and build volume;
- acceptance criteria and unknowns.

For a replacement or upgrade, also record the current system's measurable behavior, surviving datums, mating components, evidence of wear or failure, and which geometry may change. Do not reproduce a broken surface as nominal geometry or preserve the original failure mode by default.

Do not invent critical dimensions. Mark assumptions and keep them parameterized.

### 2. Choose a manufacturing strategy

Choose FDM/FFF, SLA, SLS, or another process from the required material behavior, feature resolution, surface finish, support access, quantity, and available equipment. Treat printer, material, condition, profile, orientation, build position, and environment as one qualified manufacturing unit.

Decide whether to print one part, split the design, add non-printed hardware, or change process. Prefer a simpler load path over geometric cleverness. For repeated production, optimize successful throughput and controlled operations rather than the nominal print time of one lucky part.

### 3. Map coordinates and load paths

Define the build direction, part axes, datums, assembly direction, and primary load vectors. Route force through continuous material. Keep peak tension, peel, and bending away from weak layer interfaces where possible.

Separate these functions when practical:

- locate the part;
- react shear and torque;
- clamp or retain it;
- provide a hard stop;
- permit assembly and disassembly.

### 4. Build a parametric model

Keep an editable source model as the authority. Name parameters by intent, including wall, rib, boss, hole, clearance, chamfer, fillet, and process compensation. Derive repeated dimensions from shared parameters.

Model stable primary volumes first, then interfaces, load-carrying features, process features, and cosmetic details. Avoid long chains of fragile face references when a datum, sketch, or explicit parameter will remain stable.

When reconstructing an existing part, follow [references/reverse-engineering-and-field-validation.md](references/reverse-engineering-and-field-validation.md). Use scans and photographs as evidence, but rebuild critical datums and fits from measured, parametric geometry. Prototype the uncertain interface before printing the entire part.

### 5. Design a printable build strategy

Apply [references/printability-and-supports.md](references/printability-and-supports.md) before accepting support generation. Classify every risky region as an overhang, bridge, unsupported start, internal ceiling, trapped support region, or unstable slender feature.

Challenge the design in this order: make the geometry self-supporting, change orientation, split and assemble, use a qualified bridge, use selective slicer support, add parameterized CAD breakaway support, use a compatible secondary support material, or change process. Stop at the first option that satisfies function, surface, repeatability, and total production cost. Do not optimize only for minimum support volume.

Then apply [references/design-rules.md](references/design-rules.md). In particular:

- align walls and thin features with achievable toolpaths or exposure resolution;
- use ribs, gussets, shells, and generous transitions instead of uniform bulk;
- add root fillets and avoid abrupt section changes;
- give holes, slots, bridges, trapped volumes, and support interfaces an intentional orientation;
- add lead-ins, edge relief, drainage, powder escape, and tool access where required;
- design the first layer, support or breakaway features, part removal, and visible surfaces as intentional interfaces;
- use local geometry to request useful toolpaths, then confirm the request in the slicer rather than assuming it worked;
- keep dimensional compensation separate from nominal geometry.

### 6. Calibrate interfaces

Never present a tolerance as universal. If fit matters, create the smallest representative coupon that preserves the production orientation, material, profile, wall strategy, and mating geometry. Print a parameter ladder, measure it, select a fit, and feed the result back into the source model.

### 7. Inspect before printing

Check the source solid and exported mesh for units, scale, watertightness, self-intersections, reversed faces, degenerate triangles, thin walls, trapped volumes, and unintended disconnected bodies.

Inspect the sliced preview layer by layer. Verify perimeters, gaps, bridges, supports, seam placement, small features, first-layer effects, tool changes, and estimated material. A valid mesh is not necessarily a printable or strong part.

### 8. Validate with increasing fidelity

Use the cheapest test that can disprove the design:

1. dimension or interference check;
2. cropped feature coupon;
3. interface or assembly prototype;
4. representative material and orientation test;
5. full part under realistic load and environment.

For consequential parts, follow [references/evidence-driven-engineering.md](references/evidence-driven-engineering.md), add an appropriate engineering analysis, safety factor, abuse test, repeat specimens, and independent review. Do not claim safety certification from geometry inspection or a single successful print.

For parts installed in an existing system, repeat the baseline measurements after installation and define field-inspection intervals, retirement criteria, or service-exposure tests when aging, wear, creep, weather, or safety consequence matters.

When a failed test could damage the host system or release a hazardous fragment, reproduce and contain that failure in a separate fixture before progressing to guarded installed tests.

### 9. Deliver reproducible outputs

Provide:

- editable source CAD and neutral STEP when supported;
- STL or 3MF in explicit units;
- orientation and process notes;
- the selected support strategy, protected surfaces, and either the saved slicer project or parameterized CAD support and removal instructions;
- parameter and assumption summary;
- coupon results and chosen compensation;
- verification evidence and unresolved risks.

Prefer concise English identifiers in source code and generated file names.
