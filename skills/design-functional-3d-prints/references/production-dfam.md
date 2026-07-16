# Production-Aware FDM/FFF Design

Use this reference to turn FDM/FFF manufacturing behavior into CAD intent. These are reusable design rules, not guaranteed dimensions.

## Qualify a manufacturing unit

Treat this combination as the process being designed:

- printer and nozzle;
- material, batch, and moisture condition;
- slicer version and profile;
- part orientation and build position;
- support, removal, and post-processing method;
- expected production environment.

A successful build on a different combination is evidence, not qualification.

## Optimize successful throughput

For repeated production, minimize total cost per accepted part:

`accepted_part_cost = machine_time + material + manual_work + inspection + failure_and_rework`

Do not optimize only nominal print time. A slower geometry can be better when it removes support work, prevents one failure mode, or makes inspection deterministic.

Ask of every feature:

1. What manufacturing or product function does it serve?
2. What new perimeter, bridge, travel, support, seam, or manual operation will it create?
3. Can the same function be achieved with a simpler and more repeatable path?

## Choose orientation before detailing

Score candidate orientations against:

- service loads and layer interfaces;
- support and bridge risk;
- first-layer stability and warping;
- datum, sealing, sliding, and visible surfaces;
- surface stepping and shrink lines;
- part removal and handling;
- throughput and nesting.

Angled printing can distribute a load across layers, but it can also add support, surface error, and production variability. Treat it as a candidate to test, not a universal strength rule.

## Design the first layer

- Prefer a continuous, inspectable first layer without fragile islands.
- Use enough contact to resist warping and handling, but avoid unnecessary contact that slows removal or damages the visible face.
- Relieve mating edges affected by first-layer expansion.
- Add a removable raft, foot, or fin only when its break line, removal direction, and witness mark are controlled.
- For automated removal, validate the lower edge, contact area, cooling state, and ejection direction on the actual machine.

## Make geometry and toolpaths agree

CAD defines a volume; the slicer decides how that volume is filled. Use geometry to request useful paths, then inspect the result.

- Size functional walls so they resolve into stable perimeter paths.
- Add ribs, gussets, local shells, slots, or small reliefs when they place continuous paths along the load route.
- Prefer local reinforcement over raising infill everywhere.
- Avoid tiny features that disappear, alternate unpredictably, or create isolated start-stop paths.
- Recheck after changing line width, nozzle, wall generator, infill, or slicer version.

Do not call a hidden feature a strength improvement until the sliced paths and a physical test support the claim.

## Design holes and roofs by orientation

For each hole, record its axis relative to the build direction and its function.

- Vertical holes usually avoid roof sag but still need dimensional calibration.
- Side holes may interrupt load paths and create a weak crown. Consider a bridge roof, teardrop, polygonal or arched crown, local rib, or post-machined pilot.
- Use a hexagonal or other non-circular profile only when its functional fit permits it.
- Add a lead-in without shortening the calibrated bearing region.
- Reinforce threaded and fastener holes locally and keep clamp force off unsupported crowns.

## Replace accidental support with designed support

When the part cannot be reoriented or split, CAD support fins can make support behavior explicit.

- Give the fin a broad, stable base and a smooth root.
- Connect adjacent fins when that prevents independent tipping.
- Use small, accessible breakaway contacts that do not become the functional surface.
- Put removal marks where they can be hidden or finished.
- Parameterize the fin so it can be tuned or suppressed.
- Test both build survival and removal force.

Automatic support remains appropriate when it is reliable, accessible, and cheaper than maintaining designed support geometry.

## Use compliance to absorb process variation

Rigid, fully contacting interfaces accumulate print error. Use intentional compliance when alignment and load allow it:

- flexible fins instead of a broad interference surface;
- interrupted locating pads instead of a long precision contact;
- relief behind a snap, press feature, or grip fin;
- a hard stop so the compliant feature does not carry static load.

Calibrate the compliant feature for strain, assembly force, creep, and cycles, not just initial fit.

## Treat markings and texture as manufacturing features

- Tie minimum text stroke and relief depth to the qualified line width and layer height.
- Prefer simple, open glyphs and verify every stroke in the sliced preview.
- Keep first-layer and top-surface text away from regions where expansion or skin paths erase detail.
- Use sidewall text when it provides more stable paths and acceptable stepping.
- Use texture for grip, visual contrast, or stiffness only after checking cleanability, path density, and stress concentration.

## Production review

Before release, answer:

- What is the intended orientation, and why?
- Which CAD features deliberately control toolpaths?
- Which surfaces touch the bed or support?
- What manual operations remain, and how are they inspected?
- What coupon or go/no-go feature detects drift?
- What changes require requalification?
- What evidence shows repeatability beyond one build?
