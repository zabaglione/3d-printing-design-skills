# Fit and Calibration

## Define the dimension convention

Use explicit terms:

- `c_side`: clearance on one planar side;
- `c_radial`: radial clearance between cylindrical surfaces;
- `c_diametral = 2 * c_radial`;
- `i_diametral`: diametral interference, stated as a positive magnitude;
- `engagement`: contact length after assembly;
- `lead_in`: non-contact entry length.

Never label an ambiguous value only as `tolerance`.

## Estimate compensation from measurements

For a hole and pin coupon, define signed process errors:

- `e_hole = measured_hole - cad_hole`
- `e_pin = measured_pin - cad_pin`

For a target actual diametral gap `g_target`, start the next CAD iteration with:

`g_cad = g_target - e_hole + e_pin`

Treat this as local empirical compensation, not a printer-wide constant. Recalibrate after changing size range, shape, material, profile, orientation, cooling, cure, or supplier.

Do not derive interface compensation from one outside measurement on a small calibration cube. Internal features, external features, holes, pins, orthogonal axes, diagonals, and long spans expose different combinations of scale, skew, shrinkage, and path-width error.

## Build a representative coupon

1. Copy the actual local interface, including shape, wall, entry, engagement, and print orientation.
2. Remove unrelated bulk while preserving heat flow, support, and toolpath behavior near the fit.
3. Create a monotonic ladder of at least five candidate gaps or interferences around the best current estimate.
4. Emboss durable English labels that remain readable after slicing.
5. Print the mating features together when shared process drift matters, or separately when production does.
6. Condition and post-process them exactly like production parts.
7. Repeat each promising comparative candidate at least three times to screen variation. Add builds, positions, and specimens when the consequence or release confidence demands it.

## Classify the result by behavior

Record behavior instead of only dimensions:

| Fit class | Acceptance evidence |
| --- | --- |
| Free-running | Moves through the full range without sticking after post-process |
| Sliding | Moves by hand with controlled play and no damage |
| Locating | Seats repeatably against datums with acceptable play |
| Push fit | Requires intentional hand force and survives removal if required |
| Press fit | Meets controlled insertion and retention force without splitting |
| Snap fit | Meets assembly, release, retention, and cycle targets |
| Print-in-place | Releases and moves after the complete manufacturing process |

## Test more than the first assembly

- Measure assembly and extraction force when they matter.
- Inspect whitening, cracking, layer separation, permanent set, wear, and debris.
- Cycle the joint for the required life plus an appropriate margin.
- Hold loaded polymer joints long enough to expose creep.
- Repeat across multiple builds or positions when process variation matters.
- Test at service temperature and humidity when they change dimensions or material response.

## Record the qualified fit

| Field | Value |
| --- | --- |
| Joint and nominal size | |
| Printer or provider | |
| Process and material batch | |
| Profile and orientation | |
| Post-process and conditioning | |
| Coupon revision | |
| CAD gap or interference | |
| Measured dimensions | |
| Assembly and retention result | |
| Cycle and environment result | |
| Qualified range and limits | |
