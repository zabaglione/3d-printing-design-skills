---
name: design-3d-printed-joints
description: "Select, design, parameterize, and validate joints for 3D-printed assemblies. Use when Codex needs to connect split or modular printed parts; choose among locating pins, press or slip fits, tongue-and-slot joints, dovetails, snap-fits, compliant clips, bayonets, printed threads, screws, captive nuts, heat-set inserts, adhesives, magnets, hinges, ball joints, or print-in-place mechanisms; size clearances; orient interfaces; or create joint test coupons."
---

# Design 3D-Printed Joints

Design the joint as a system of locating, load-transfer, retention, stop, assembly, and manufacturing features. Select a pattern from requirements, then calibrate it on the actual print process.

## Load the relevant references

- Read [references/joint-selection.md](references/joint-selection.md) to shortlist joint families.
- Read [references/joint-patterns.md](references/joint-patterns.md) before modeling the selected family.
- Read [references/fit-and-calibration.md](references/fit-and-calibration.md) whenever clearance, interference, motion, or assembly force matters.
- Read [references/source-notes.md](references/source-notes.md) when tracing the research basis or looking for visual examples.

## Workflow

### 1. Classify the joint

Record:

- permanent, occasional-service, frequent-service, or continuous-motion use;
- assembly count and service life;
- tension, compression, shear, torque, peel, bending, impact, vibration, and creep;
- required alignment and acceptable play;
- assembly direction, hand and tool access, blind assembly, and maximum assembly force;
- print process, material, profile, orientation, environment, and non-printed hardware;
- size, appearance, cost, and failure consequence.

If these are unknown, state assumptions and design a reversible experiment before committing to the final joint.

### 2. Separate joint functions

Assign each function deliberately:

- **Locate:** datum faces, pins, keys, pilots, or tongues.
- **Transfer load:** shoulders, broad faces, shear keys, splines, or dovetails.
- **Retain:** clips, screws, threads, wedges, bayonet lugs, magnets, or adhesive.
- **Stop:** hard surfaces that prevent springs, threads, or fasteners from carrying unintended end loads.
- **Enable assembly:** lead-ins, chamfers, reliefs, vents, tool paths, and visible alignment marks.

Do not ask one fragile feature to locate, flex, carry shear, and provide the hard stop unless the tradeoff is intentional and tested.

### 3. Shortlist joint families

Use [references/joint-selection.md](references/joint-selection.md). Compare at least two plausible families when failure consequence, print time, or serviceability matters. Prefer the fewest parts and operations that still meet the acceptance criteria.

### 4. Parameterize the interface

Create named parameters for nominal size, per-side clearance, interference, engagement length, insertion depth, lead-in, root fillet, stop position, flexure length and thickness, fastener pilot, and process compensation.

State whether a clearance is radial, diametral, or per-side. Never use an unlabeled number named only `tolerance`.

### 5. Orient geometry and loads

Choose part split and print orientation together. Keep snap arms, hinge knuckles, pins, hooks, and thread teeth from peeling across layer interfaces. Use broad shoulders to react service loads and keep retention features primarily loaded during assembly.

Design horizontal holes, roofs, and slots for the actual bridging or support strategy. Add first-layer relief where an interface reaches the build plate.

### 6. Add assembly robustness

Add lead-ins before tight engagement, relief at blind ends, escape paths for air, resin, powder, and adhesive, and hard stops before a flexure is overdriven. Key symmetric-looking parts when incorrect assembly is possible. Provide extraction or release access for serviceable joints.

### 7. Calibrate before full-size printing

Follow [references/fit-and-calibration.md](references/fit-and-calibration.md). Use a small fit ladder in the production orientation and process. Preserve the same local wall thickness, toolpath direction, contact length, and entry geometry as the final interface.

### 8. Test the failure modes

Measure assembly force, play, retention, motion, damage, cycle life, creep, and environmental effects as applicable. Inspect layer separation, root cracking, tooth shear, boss splitting, insert pull-out, adhesive peel, wear debris, and permanent set.

Test the intended misuse that the consequence warrants. Redesign the load path rather than merely increasing global infill when a local feature fails.

### 9. Report the design

Deliver the selected family, rejected alternatives, named parameters, print orientation, hardware and assembly instructions, coupon result, acceptance evidence, and remaining risks. Keep source geometry editable so the fit can be recalibrated without remodeling the part.
