# Research Source Notes

These sources informed the reusable workflow. They provide experiments, examples, and design prompts, not universal dimensions. Recheck current manufacturer data and qualify the actual process.

Accessed 2026-07-16.

## Slant 3D: production-aware modeling

- [Slant 3D channel](https://www.youtube.com/@slant3d)
- [Mastering 3D Printing Design: From Beginner to Pro](https://www.youtube.com/playlist?list=PLkUv8_afCbJ8lROgJeu0xRwD8cJqUBS2j) — a 36-video design course covering orientation, walls, holes, ribs, enclosures, support-aware geometry, joints, surfaces, and automated production.
- [How-to Design for Mass Production 3D Printing](https://www.youtube.com/playlist?list=PLkUv8_afCbJ9zfaZxqL4AHBrGHqTaU9lo) — a larger catalog of production-oriented design examples.
- [8 Essential Design Rules for Mass Production 3D Printing](https://www.youtube.com/watch?v=1n_R8shlGcs) — walls, overhangs, first layers, cavities, texture, compliance, and bed contact.
- [3x Part Strength Without Slicer Settings](https://www.youtube.com/watch?v=Lq-SoGgKOcQ) — using CAD geometry to request local paths, subject to slicer and physical verification.
- [The Correct Way to Design Holes for 3D Printing](https://www.youtube.com/watch?v=ip70-Tw6tBE) — side-hole orientation, roofs, ribs, compensation, reinforcement, and compliant fits.
- [How to Design Better Support Fins](https://www.youtube.com/watch?v=vnn4XeKQobs) — stable CAD support fins and controlled breakaway geometry.
- [How to Design Text for Mass Production 3D Printing](https://www.youtube.com/watch?v=upf9ixYtDG4) — orientation-aware text placement, stroke size, and surface selection.

## CNC Kitchen: measurement and failure-mode testing

- [CNC Kitchen channel](https://www.youtube.com/@CNCKitchen)
- [3D Printing for Engineers](https://www.youtube.com/playlist?list=PLEOQTmIWJ_rmoqdFUCgKrNu_BsMVB7e1V) — engineering-focused material, process, calibration, insert, and strength investigations.
- [Strength Tests](https://www.youtube.com/playlist?list=PLEOQTmIWJ_rncRcWmjQIvMKFAeM071CXM) — a catalog of controlled mechanical comparisons.
- [INFILL pattern and SHELLS](https://www.youtube.com/watch?v=AmEaNAwFSfI) — compares infill pattern, density, and shell thickness instead of treating infill percentage as a complete strength specification.
- [Stop Printing Flat: The 45 Degree Secret for Stronger Parts](https://www.youtube.com/watch?v=7aJ4dDyyf20) — tests orientation against strength, surface quality, support, and real-part tradeoffs; the conclusion is explicitly not a universal angle.
- [Calibration Cubes: More Harm Than Good?](https://www.youtube.com/watch?v=H7OsnMLDIMw) — separates skew, shrinkage, and extrusion effects using more diagnostic geometry than one small outside measurement.
- [Are Our Heat-Set Insert Datasheets Wrong?](https://www.youtube.com/watch?v=B5g7R53hcH4) — tests installation and pull-out strength over a hole-size ladder and provides representative calibration parts.
- [Everyone Gets This Wrong When 3D Printing Carbon Fiber Nylon](https://www.youtube.com/watch?v=u8dIpwd6tzo) — compares moisture, creep, annealing, stiffness, impact, strength, and temperature behavior rather than relying on a material label.
- [Threaded Inserts in 3D Prints: How Strong Are They?](https://www.youtube.com/watch?v=iR6OBlSzp7I) — insert geometry and pull-out testing.

## Slicer and support behavior

- [PrusaSlicer Support Material](https://help.prusa3d.com/article/support-material_1698) — automatic, grid, snug, and organic supports; contact and interface controls; build-plate-only support; bridge exclusion; and removal considerations.
- [PrusaSlicer Paint-on Supports](https://help.prusa3d.com/article/paint-on-supports_168584) — explicit support enforcement and blocking, with painted regions preserved in a 3MF project.
- [Modeling with 3D Printing in Mind](https://help.prusa3d.com/article/modeling-with-3d-printing-in-mind_164135) — orientation, splitting, bridges, self-supporting geometry, and modeled breakaway support as alternatives to one fixed overhang rule.
- [UltiMaker Support Material Choices](https://ultimaker.com/learn/which-3d-printing-supports-to-use-pla-pva-or-breakaway/) — tradeoffs among same-material, breakaway, and soluble supports, including dimensional and surface consequences.

## Synthesis rules

- Extract the experimental question and failure mode, not a headline multiplier.
- Preserve the distinction between one creator's setup and a qualified production process.
- Convert promising geometry into a parameterized candidate, sliced inspection, coupon, and acceptance test.
- Treat automatic, painted, CAD, soluble, and breakaway supports as alternative manufacturing strategies rather than a quality ranking.
- Prefer current supplier data and standards for exact material or hardware values; use videos as supporting evidence and practical examples.

## Need It Make It: design and validation techniques

- [This is how I design custom brackets in Fusion and test them to see if they work](https://www.youtube.com/watch?v=RawjWqPGsHs) — measure the baseline behavior, parameterize stock and directional clearances, start with a simple load path, and repeat the same physical measurement after installation.
- [How to design and print replacement parts when you only have one half](https://www.youtube.com/watch?v=lYPmiEJCawY) — use surviving geometry and careful measurements as references, print a material-light fit prototype first, and consider a pierceable modeled membrane over an otherwise support-trapping horizontal hole.
- [Upgrade for Better AIR FLOW on Your Overhangs and Bridges](https://www.youtube.com/watch?v=qAG2BnZKFgQ) — treat bridge capability as a property of the material, cooling, slicer path direction, and profile together, then inspect and test that exact stack before removing support.
- [Design AND Print your own PRINT IN PLACE](https://www.youtube.com/watch?v=zEKWZbtndX4) — qualify moving clearance on the real process and use self-supporting interfaces, first-layer relief, and bridgeable roofs while checking the sliced result for fusion or unwanted support.
- [Strong 3D Printed Connections on BIG parts](https://www.youtube.com/watch?v=fSISiR5XIbk) — make the split location and joint part of the manufacturing design by keeping seams and support scars off mating faces, adding alignment and load transfer, and testing stiffness and failure location.
- [How Strong are 3D Printed Connections?](https://www.youtube.com/watch?v=kfd3mrMZbLQ) — compare candidate joints with a continuous control and record deformation, slip, disassembly, and failure mode as well as peak load.
- [A Unique 3D Printed Screw Connection](https://www.youtube.com/watch?v=Y9Tvs8n1z6c) — let interlocking faces carry and align the load while the fastener clamps them together, and parameterize head, hole, and insert clearances for the calibrated process.
- [Which is the Best 3D Printed Corner](https://www.youtube.com/watch?v=PklGLNkt-5Q) — smooth load transitions and relieve mating inside corners, but choose fillets, sweeps, or gussets through controlled tests in the actual load direction and print orientation.
- [Can the simplest 3D printed extrusion path also be the strongest?](https://www.youtube.com/watch?v=59KvDE7adEU) — wall and infill percentages do not fully describe a part, so inspect generated paths through geometry transitions and test the actual material because the same path strategy can change the result differently by material.
- [Does PLA Warp? If it does, how much compared to PETG and ABS?](https://www.youtube.com/watch?v=L0HNy1M0Xk8) — qualify warpage on representative size, wall, infill, material, cooling, adhesion, and enclosure conditions after complete cooling and bed release rather than relying on a material label.
- [How long will your FUNCTIONAL 3D prints actually last?](https://www.youtube.com/watch?v=U6NzbH4si0Q) — retain and inspect fielded parts for looseness, creep, wear, heat, water, UV exposure, and failure location, and keep lifetime claims provisional until the relevant service exposure has accumulated.
- [Is it SAFE to make and use your own 3D printed push stick? We need to test them.](https://www.youtube.com/watch?v=_DVR7o7Vx2A) — for safety-related tools, add an application-specific pre-use proof check and periodic retirement or reinspection criteria; a simple flex check is useful screening, not universal certification.

Transferable synthesis:

- Begin with service loads, mating datums, assembly access, support removal, and unacceptable failure modes; choose geometry and orientation from those constraints.
- Treat clearance, bridge span, first-layer relief, toolpaths, and material behavior as qualified process parameters rather than universal constants.
- Inspect the sliced paths, seams, bridges, and supports, then use inexpensive fit coupons or partial prototypes before committing to the full part.
- Validate with representative hardware, load direction, environment, and duration, recording stiffness, drift, and failure mode in addition to whether the first print worked.
