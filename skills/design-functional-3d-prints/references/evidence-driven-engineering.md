# Evidence-Driven Engineering for Printed Parts

Use this reference when a design depends on strength, stiffness, tolerance, inserts, temperature, moisture, fatigue, or long-term behavior. The goal is to replace confident folklore with a falsifiable claim and a representative test.

## State the claim before choosing a test

Write the claim in measurable form:

`Given <qualified process and condition>, <part or feature> shall <behavior> under <load and environment> for <time or cycles> with <acceptance limit>.`

Separate:

- observation: what was measured;
- inference: why it may have happened;
- decision: what the design will use;
- limit: where the evidence does not apply.

Do not turn a video title, filament label, simulation result, or single specimen into a universal material property.

## Identify the evidence layers

A functional result can change at each layer:

1. **Nominal geometry:** CAD dimensions and load path.
2. **Manufactured geometry:** shrinkage, skew, sag, seams, voids, and surface defects.
3. **Toolpath or exposure:** walls, infill, path direction, temperature history, and bonding.
4. **Material state:** batch, moisture, conditioning, cure, anneal, age, and service temperature.
5. **Assembly and service:** preload, wear, impact, creep, chemicals, and misuse.

Control or record the layers that could change the conclusion.

## Design a useful experiment

1. Choose the failure mode and response metric before printing.
2. Change one primary variable at a time unless the experiment is explicitly factorial.
3. Preserve production orientation, local wall paths, feature size, material condition, and post-process.
4. Use at least three repeats per promising comparative condition, then add specimens, builds, and positions to reveal variation appropriate to the consequence. Never hide an outlier without a recorded cause.
5. Randomize or distribute build positions when position effects matter.
6. Measure the specimen before the destructive test.
7. Record the full load-displacement or time response when peak load alone can mislead.
8. Photograph and classify the failure location and mode.
9. Repeat the test after the design change using the same protocol.

Use a cropped feature coupon for early screening, then confirm the selected design in the real part. A generic tensile bar, hook, or cube cannot reproduce every notch, path, constraint, or environment.

## Reason about strength architecture

- Orientation changes both layer loading and geometry quality. Compare realistic orientations rather than assuming flat, vertical, or 45-degree printing is always best.
- External shells and local load-aligned paths often contribute more efficiently than indiscriminately increasing infill.
- Infill pattern and density still matter when they brace shells, transfer shear, resist crushing, or become part of a tested load path.
- Temperature, cooling, line width, nozzle, and speed can change bonding and geometry together. A stronger coupon that no longer meets dimensions is not automatically a better process.
- Simulation is a load-path aid unless it models printed anisotropy, defects, contacts, and material condition with validated inputs.

## Qualify material state

For every mechanical result, record:

- exact material and batch;
- dry, conditioned, or service-equilibrated state;
- print and chamber conditions;
- post-cure, anneal, or smoothing process;
- test temperature, humidity, and loading rate;
- specimen orientation and age.

Distinguish stiffness, yield, ultimate load, elongation, impact, fatigue, creep, and stress relaxation. Fiber filling, drying, or annealing may improve one result while worsening another or changing dimensions.

## Calibrate dimensions with diagnostic geometry

Do not tune a complete machine from one outside dimension on one small cube.

- Measure multiple distances large enough to reduce instrument and edge effects.
- Include internal and external features to separate path-width effects from global scale or shrinkage.
- Include orthogonal and diagonal spans when skew matters.
- Use the actual hole, slot, pin, or joint orientation for interface compensation.
- Keep mechanical motion calibration separate from material and slicer compensation.
- Verify the correction on a different size before applying it broadly.

For a fit, the representative interface coupon remains the release authority.

## Qualify heat-set and press-in hardware

Treat supplier hole guidance as a starting range.

1. Match the exact insert or hardware geometry and material.
2. Preserve boss wall paths, insertion direction, depth, entry geometry, and installation method.
3. Print a hole-diameter ladder around the starting value.
4. Record pre-seating, alignment, installation force or temperature, displaced material, and final depth.
5. Test pull-out, torque-out, boss splitting, clamp relaxation, and the actual service load as applicable.
6. Repeat specimens and select a robust range, not merely the strongest difficult-to-install sample.
7. Requalify after changing printer, material, condition, orientation, profile, or insert supplier.

If boss geometry is not already qualified, hold the selected hole and installation method constant while separately screening radial boss thickness and material below the insert. This distinguishes installation fit from boss splitting and pull-out load-path capacity.

Use an entry chamfer or shallow relief when it improves alignment and gives displaced polymer a controlled destination, but preserve adequate load-bearing material around and below the insert.

## Evidence level and language

| Evidence | Allowed conclusion |
| --- | --- |
| Slicer inspection only | The intended paths appear in this sliced build |
| One coupon | The concept worked once under the recorded conditions |
| Repeated representative coupons | The feature has an observed range under the recorded conditions |
| Repeated full parts and environments | The design met the stated test protocol |
| Qualified process with controlled inspection | Production is controlled within the documented limits |

Report measured values with sample count and conditions. Use `target`, `estimate`, or `starting point` for unverified numbers. Use `qualified` only with a documented range and protocol.

## Minimum test record

| Field | Value |
| --- | --- |
| Claim and acceptance limit | |
| Source model and specimen revision | |
| Printer, nozzle, material, and batch | |
| Material condition and post-process | |
| Slicer, profile, orientation, and build position | |
| Sample count | |
| Dimensions before test | |
| Test setup and rate | |
| Raw results and variation | |
| Failure mode and location | |
| Decision and qualified limits | |
