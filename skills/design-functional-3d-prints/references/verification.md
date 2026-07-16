# Verification Checklist

## Requirements

- [ ] Define the function, interfaces, environment, life, loads, and failure consequence.
- [ ] Turn important requirements into measurable acceptance criteria.
- [ ] Mark every assumption that could change geometry or material.

## Source model

- [ ] Keep an editable parametric source as the authority.
- [ ] Name process compensation separately from nominal dimensions.
- [ ] Define build direction, part axes, datums, and assembly direction.
- [ ] Check minimum sections, fillets, access, stops, drainage, and trapped volumes.
- [ ] Check every body is intentional and every interface is reachable.

## Exported geometry

- [ ] Confirm units, scale, body count, and intended file format.
- [ ] Check watertightness, normals, self-intersections, degenerate faces, and disconnected shells.
- [ ] Check tessellation error on curved fits, gears, threads, and seals.

## Build preparation

- [ ] Inspect every layer or exposure region, not only the rendered surface.
- [ ] Verify orientation against the load path.
- [ ] Verify walls become stable toolpaths or exposure features.
- [ ] Inspect holes, bridges, supports, seams, first-layer effects, islands, drainage, and powder escape.
- [ ] Confirm local ribs, slots, and micro-features create the intended perimeter and infill paths.
- [ ] Verify supports or CAD support fins are stable, reachable, removable, and kept off critical surfaces.
- [ ] Confirm no support or trapped material blocks assembly or motion.

## Physical validation

- [ ] Print critical feature coupons before the full part.
- [ ] Record printer, material batch, profile, orientation, conditioning, and measured result.
- [ ] Test fit, load, impact, cycles, creep, temperature, moisture, and chemicals as required.
- [ ] Use enough repeat specimens and build positions to expose variation appropriate to the consequence.
- [ ] Record raw measurements, failure locations, conditioning, and any excluded result; do not report only the best specimen.
- [ ] Inspect the failure surface and update the load path or local feature.
- [ ] Re-run affected checks after each geometry or process change.

## Repeatable production

- [ ] Count support removal, insertion, finishing, inspection, and other manual operations.
- [ ] Verify first-layer stability, warping, part removal, and surface damage across representative builds.
- [ ] Define a go/no-go feature, coupon, or measurement that detects relevant process drift.
- [ ] Requalify when the printer, nozzle, material batch, conditioning, profile, orientation, build position, or post-process changes materially.

## Delivery record

Record at minimum:

| Item | Value |
| --- | --- |
| Source revision | |
| Export revision and units | |
| Printer and process | |
| Material and condition | |
| Profile and orientation | |
| Build position and material condition | |
| Calibrated compensation | |
| Acceptance tests | |
| Sample count and variation | |
| Known limits | |
