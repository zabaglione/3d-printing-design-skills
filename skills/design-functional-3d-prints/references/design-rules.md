# Functional Part Design Rules

Use these as reasoning rules, not universal dimensions. Qualify critical geometry on the intended printer, material, profile, orientation, and environment.

## Process choice

| Process | Prefer when | Watch for |
| --- | --- | --- |
| FDM/FFF | Low cost, large parts, common thermoplastics, controllable toolpaths | Layer-direction weakness, hole shrinkage, seams, first-layer expansion, support scars |
| SLA/DLP | Fine features, smooth surfaces, tight small-part detail | Brittle or aging resins, trapped resin, support marks, post-cure dimensional change |
| SLS/MJF | Complex support-free assemblies, nylon behavior, production batches | Grainy surfaces, powder escape, thermal distortion, process-provider compensation |

Choose from functional material properties after processing. Do not select by filament or resin label alone.

## Geometry and load path

- Route loads through continuous sections and broad contact faces.
- Prefer shells, ribs, gussets, and local bosses over uniform solid mass.
- Keep wall transitions gradual. Add generous fillets at rib, boss, snap, and bracket roots.
- Avoid sharp internal corners in cyclic or impact-loaded regions.
- Place material far from the neutral axis when resisting bending, while preventing thin-shell buckling.
- Use symmetry only when it does not enable incorrect assembly.
- Add hard stops so flexible features do not carry static service loads.

## FDM/FFF-specific reasoning

- Align functional walls with stable perimeter paths. Size them as intentional multiples of the qualified extrusion width when possible.
- Treat Z-direction tension and peel as suspect. Rotate or split the part so principal tension follows deposited roads.
- Use ribs, shells, and local perimeter paths before relying on global infill percentage as a strength control. Confirm that CAD features produce the intended paths in the sliced preview.
- Expect circular holes to print undersize and horizontal roofs to sag. Calibrate, reorient, use a printable roof, bridge, teardrop, polygonal profile, or post-machine critical bores.
- Reinforce a side hole with a local rib or shell when layer paths would otherwise split around a weak opening.
- Chamfer or relieve bed-contact edges that mate with another part.
- Keep the first layer simple enough to inspect and repeat. Balance bed contact against warping, removal, surface quality, and any automated ejection requirement.
- Prefer self-supporting chamfers, arches, or progressive roofs where they preserve the load path; do not apply a fixed overhang angle without testing the selected process.
- When automatic support is wasteful or damages a functional surface, consider removable CAD support fins with stable bases, smooth roots, accessible breakaway sections, and hidden witness marks. Keep them parameterized and verify removal force.
- Keep small pins and columns short or brace them. Their success depends on orientation, path width, cooling, and slenderness.
- Avoid cavities, cutouts, or decorative perforations that add perimeter time and failure points without serving flow, access, compliance, weight, or another explicit function.

## Surface, markings, and handling

- Put critical datums, seals, slides, and visible faces away from seams, supports, and unstable first-layer regions.
- Size embossed and debossed text from the qualified nozzle, line width, layer height, orientation, and viewing distance. Verify every stroke in the slicer.
- Prefer simple sidewall markings when top-surface or first-layer text would be distorted. Add contrast through geometry or texture only when it remains printable and cleanable.
- Add grips, tool access, release tabs, and removal directions as functional geometry rather than relying on undocumented operator technique.

## Resin and powder-process reasoning

- Provide drain and cleaning access to every enclosed volume.
- Avoid uncured resin traps and unvented suction cups.
- Provide powder escape paths for hollow or print-in-place geometry.
- Account for post-cure, thermal, and provider-specific compensation.
- Place support contacts away from sealing, sliding, and datum surfaces.

## Walls, ribs, bosses, and holes

- Set wall thickness from process capability and load, then verify it in the slicer or build preparation software.
- Tie bosses into nearby walls with smooth ribs when they transmit load.
- Give fastener bosses enough surrounding material to resist hoop stress and splitting.
- Use washers, flanges, or shoulders to spread clamping force.
- Separate a precision bore from a printed pilot when drilling or reaming is acceptable.
- Add access for drivers, taps, reamers, insert tools, nuts, and removal.

## Material and environment

- Check stiffness, yield strain, toughness, fatigue, creep, heat deflection, moisture uptake, UV, chemicals, and layer adhesion.
- Distinguish short-term strength from stiffness, impact behavior, fatigue, stress relaxation, and long-term creep. A material can perform well in one and fail in another.
- Prefer tough, fatigue-resistant materials for repeated snap or hinge motion.
- Account for polymer creep under constant clamp or spring load.
- Condition moisture-sensitive materials consistently before dimensional qualification and record whether test values represent dry, conditioned, or service-equilibrated parts.
- Treat filled materials, annealing, and post-processing as process changes that can alter shrinkage, anisotropy, moisture response, and dimensions. Requalify after applying them.
- Treat food, medical, pressure, lifting, vehicle, and protective-equipment uses as requiring domain-specific validation beyond this skill.

## Dimensional strategy

- Preserve nominal geometry and process compensation as separate parameters.
- Dimension from functional datums rather than decorative surfaces.
- Define clearance as per-side, radial, or diametral.
- Calibrate mating features with a representative coupon.
- Use multiple spans and both internal and external features when separating scale, skew, extrusion, and material-shrinkage errors. A single small cube cannot identify all of them.
- Avoid copying a tolerance from another printer, orientation, material, or profile.

## Model and export hygiene

- Keep one authoritative parametric source.
- Use stable datums and intent-based parameter names.
- Confirm units on every export.
- Prefer STEP for editable neutral solids and 3MF when units, multiple bodies, or manufacturing metadata matter.
- Use STL only with an explicit unit convention and sufficient tessellation for the functional surface.
