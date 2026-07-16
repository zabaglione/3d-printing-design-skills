# Printability and Support Decisions

Use this reference to decide whether geometry should be redesigned, reoriented, split, bridged, supported, or moved to another process. Do not begin by enabling supports.

## Contents

- [Define the manufacturing condition](#define-the-manufacturing-condition)
- [Classify each risk region](#classify-each-risk-region)
- [Use the elimination ladder](#use-the-elimination-ladder)
- [Choose the support method](#choose-the-support-method)
- [Redesign common risk shapes](#redesign-common-risk-shapes)
- [Configure slicer-generated support deliberately](#configure-slicer-generated-support-deliberately)
- [Design custom CAD support as a disposable mechanism](#design-custom-cad-support-as-a-disposable-mechanism)
- [Account for process-specific support physics](#account-for-process-specific-support-physics)
- [Qualify the decision](#qualify-the-decision)
- [Deliver the support decision](#deliver-the-support-decision)

## Define the manufacturing condition

Record the process, machine, material condition, nozzle or optical system, layer profile, cooling, support material capability, build volume, post-process access, and required surface quality. A fixed overhang angle or bridge length is not portable across these conditions.

Mark protected surfaces before evaluating support:

- datums, fits, seals, bearings, sliding tracks, and fastener seats;
- visible or tactile surfaces;
- thin edges and fatigue-critical roots;
- enclosed regions that tools, solvent, air, resin, or powder cannot reach;
- bed-contact faces and first-layer dimensions.

## Classify each risk region

Classify geometry from the intended build direction rather than from its name.

| Risk region | Meaning | Primary questions |
| --- | --- | --- |
| Supported slope | Each new path or exposure overlaps stable material below | Does the qualified process preserve the edge and surface? |
| Overhang | A path is only partly supported by the preceding layer | Is overlap, cooling, curvature, and local speed sufficient? |
| Bridge | A path spans between two or more supported anchors | Are span, direction, anchors, sag, and underside quality qualified? |
| Unsupported start or island | New material begins with no valid foundation | Can it be connected, reordered, reoriented, or explicitly supported? |
| Internal ceiling | A roof closes a cavity or channel | Can it bridge, arch, drain, depowder, and remain inspectable? |
| Slender or weak feature | Geometry has a foundation but may deflect, detach, or overheat | Can it be shortened, braced, grouped, or reoriented? |
| Trapped support region | Support can be generated but not removed or cleaned | Should the part split, gain access, use another material, or change process? |

Do not treat a bridge as an ordinary overhang. Do not treat an SLA island as an FDM overhang-angle problem. Do not call powder-supported geometry finished until powder escape and thermal behavior are addressed.

## Use the elimination ladder

Evaluate these options in order. Reorder only when a documented functional or production requirement justifies it.

1. **Make the final geometry self-supporting.** Replace abrupt undersides with a ramp, chamfer, arch, progressive roof, shorter span, supported curvature, or permanent rib. Preserve the load path and required envelope.
2. **Change orientation.** Compare several build directions against layer loading, bed stability, support contact, visible surfaces, dimensional accuracy, warping, and throughput. Orientation solves one risk by moving it elsewhere.
3. **Split and assemble.** Put each critical face in a favorable orientation and add intentional locating, load-transfer, retention, and alignment features. Count assembly time and tolerance accumulation.
4. **Bridge intentionally.** Use a bridge only when it has stable anchors, a qualified span and direction, acceptable sag, and no critical unsupported underside.
5. **Use selective slicer-generated support.** Prefer painted regions, enforcers, blockers, build-plate-only rules, or local modifiers over indiscriminate support when the slicer can preserve the decision.
6. **Add custom CAD breakaway support.** Use designed fins, tabs, membranes, sacrificial roofs, or braces when contact, stability, removal direction, and witness marks must be deterministic.
7. **Use a secondary support material.** Consider soluble or breakaway interfaces when the machine, model material, moisture control, tool changes, purging, access, and disposal process are compatible.
8. **Change process.** Use a process with a more suitable support or powder behavior when the prior options compromise function, access, quality, or repeatability.

Support is not a correction for an unresolved build strategy. It is one manufacturing operation with its own interfaces, variation, labor, and failure modes.

## Choose the support method

| Method | Prefer when | Avoid or reconsider when |
| --- | --- | --- |
| No added support | Final geometry is qualified in the chosen orientation | Success depends on an untested angle, span, or hidden island |
| Automatic slicer support | Contacts are accessible, scars are acceptable, and the generated result is stable | The slicer reaches critical faces, fills cavities, or changes unpredictably with profiles |
| Painted or enforced slicer support | Only specific regions need support and the project file can preserve those regions | The deliverable is only an STL or the manufacturing project will not be controlled |
| Custom CAD support | Repeated production needs fixed contacts, stable fins, known break lines, or integrated bracing | The same result is reliable with simpler slicer support or the sacrificial geometry cannot be removed |
| Same-material breakaway support | One tool is available and contact damage is acceptable or finishable | Tight interfaces, inaccessible contacts, or critical surfaces require near-zero gap |
| Soluble or dissimilar interface | Critical undersides or complex access justify tool changes and material handling | Materials do not adhere compatibly, solvent cannot reach, purge waste dominates, or residues matter |
| Split construction | Internal support is trapped or each face needs a different favorable orientation | Assembly, seams, hardware, or tolerance stack causes a larger functional risk |
| Different process | Current process forces unacceptable support, distortion, labor, or surface damage | The alternative cannot provide the required material, size, cost, or qualification evidence |

Automatic support is not inherently less engineered than CAD support. A saved slicer project with explicit painted regions, blockers, interfaces, and profile can be the better controlled artifact. CAD support is preferable only when encoding the disposable structure in geometry creates a measurable benefit.

## Redesign common risk shapes

| Risk | Candidate transformations |
| --- | --- |
| Horizontal round opening | Reorient the axis; use an arch, teardrop, polygonal crown, bridge roof, sacrificial membrane, or post-machined pilot when function permits |
| Broad flat ceiling | Add an arch, vault, progressive roof, ribs that shorten the span, a controlled bridge direction, or split the enclosure |
| Downward-facing detail | Move, rotate, mask, simplify, mirror to an upward face, or isolate on a separately printed insert |
| Free-starting feature | Connect it to a stable path, extend it to the bed, add a permanent rib, or provide explicit support |
| Tall pin or thin wall | Shorten, brace, group, thicken locally, change path direction, or print separately |
| Deep cavity | Add removal access, split the body, create drainage and escape paths, use compatible soluble support, or change process |
| Weak support contact on a critical face | Move the contact to a sacrificial pad, hidden witness region, machining allowance, or replaceable insert |

These transformations are candidates, not automatic improvements. Recheck loads, fits, flow, cleaning, appearance, and assembly after changing geometry.

## Configure slicer-generated support deliberately

Treat the saved slicer project and versioned profile as manufacturing data. Inspect:

- support region selection and excluded protected surfaces;
- support style, base stability, branch or column collision, and build-plate reach;
- contact gap, XY separation, interface density, roof or floor layers, and bridge behavior;
- support material, tool changes, purging, temperature compatibility, and moisture control;
- first-layer footprint, brim or anchoring, travel paths, seams, and collision risk;
- whether support begins on the bed, on the part, or in a cavity;
- whether every support fragment has a safe removal path.

An angle threshold is a generator input, not proof that all selected surfaces need support or that all unselected surfaces will print. Preview every layer and override locally when justified.

## Design custom CAD support as a disposable mechanism

A custom support should have explicit functions:

- a stable base or attachment region;
- a trunk, fin, brace, membrane, or sacrificial roof that carries build loads;
- a small and predictable contact or break line;
- clearance from the final surface except at intended contacts;
- tool and hand access in a declared removal direction;
- a witness mark placed on a non-critical region;
- optional links between supports when they prevent independent tipping;
- parameters that allow suppression and tuning without remodeling the part.

Avoid needle-like supports, broad fused contacts, inaccessible internal fragments, sharp removal hazards, and break lines at fatigue roots. Verify both survival during printing and removal without damage. Record removal tools, force or effort, time, and required finishing.

## Account for process-specific support physics

### FDM/FFF

Evaluate path overlap, line width, layer height, cooling, material temperature, bridge direction, path anchors, and local speed. Supported undersides commonly differ from sidewalls and top surfaces. A contact gap that releases cleanly can also permit sag; a dense interface can improve finish while increasing removal work.

### SLA/DLP

Evaluate islands, peel and suction loads, cup formation, drain paths, support touchpoints, orientation, cleaning, and post-cure. Support decisions are not described adequately by overhang angle alone. Ensure every enclosed region drains and every support or uncured-resin region is accessible.

### SLS/MJF and powder processes

Loose powder may support geometry during the build, but it also creates escape, cleaning, thermal, packing, and inspection constraints. Provide access for depowdering and avoid calling an inaccessible cavity support-free in the production sense.

## Qualify the decision

Use the smallest representative coupon that preserves orientation, material, profile, local curvature, bridge direction, support contact, and removal access. Vary only the uncertain parameters, such as slope, span, contact, interface, fin section, or break line.

Compare candidates using:

- build success and variation across repeat specimens;
- dimensional error and underside or contact-surface quality;
- support material, machine time, tool changes, and slicing stability;
- removal time, required tools, operator risk, surface damage, and finishing;
- trapped fragments, residue, resin, or powder;
- effect on load path, fit, cleaning, and assembly;
- total cost per accepted part rather than print time alone.

Release the part only after reopening the exported manufacturing file, inspecting the sliced or prepared build, and physically qualifying the selected support strategy.

## Deliver the support decision

Record:

| Field | Value |
| --- | --- |
| Manufacturing condition and orientation | |
| Risk regions and protected surfaces | |
| Alternatives considered | |
| Selected redesign or support method | |
| Slicer version, profile, and painted regions | |
| CAD support parameters and removal direction | |
| Coupon and repeat results | |
| Removal time, damage, and finishing | |
| Accepted range and requalification triggers | |
