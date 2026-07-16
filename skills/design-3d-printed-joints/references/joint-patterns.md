# Joint Patterns

## Pins, holes, keys, and fins

- Use one round pin for location only when rotation is constrained elsewhere. Use two spaced pins, a key, or a non-round section to react torque.
- Add a lead-in before the calibrated contact region.
- Put shear into a broad shoulder rather than the pin root when possible.
- Relieve build-plate edges and blind-hole bottoms.
- Use square, diamond, cruciform, or finned sections to key rotation, reduce broad-area binding, or add local compliance.
- Keep flexible fins long enough to bend predictably and add a root fillet and hard stop.

## Tongue, slot, dovetail, and panel joints

- Use a broad tongue or slab for alignment and shear; add a separate lock if axial withdrawal is possible.
- Use T or I sections when retention is required in more than one transverse direction.
- Use a dovetail for a guided seam that must resist separation. Add entry chamfers, end relief, and a positive stop.
- Avoid a long, fully contacting precision fit. Use intermittent pads, flexible fins, or relieved spans to prevent tolerance stack-up from binding the whole seam.
- Add venting to blind slots and reservoirs when adhesive is used.
- Use lap, scarf, finger, or keyed panel joints to lengthen the load path across large or thin parts. Keep bending loads out of a single sharp seam.
- Use bidirectional tabs only when release access or intentional permanence is clear.
- When adapting a mature joint from another manufacturing process, preserve the useful engagement and load path but parameterize insertion direction, engagement length, taper, curvature, relief, and stop. Add each variation only when it improves assembly, load distribution, anti-rotation, orientation, or printability.

## Snap-fits and compliant clips

Choose among cantilever, U-shaped, torsion, annular, leaf-spring, button, or multi-latch patterns from available flexure length, assembly direction, release access, and required cycles.

- Keep the flexure root smooth and away from notches, seams, and layer peel.
- Increase flexure length before making the arm dangerously thin.
- Taper width or thickness when it distributes strain more evenly without creating an unprintable tip.
- Put a chamfer or ramp on the assembly side and choose the retention face angle from desired release force.
- Let a hard stop carry the assembled load. Avoid leaving the arm over-deflected in service.
- Orient the arm so deposited roads or the strongest material direction follow its length and tensile surface.
- Use this constant-section cantilever estimate only as an early screen:

  `maximum_surface_strain ≈ 1.5 * deflection * thickness / length^2`

  Correct for short arms, root-wall compliance, taper, stress concentration, printed anisotropy, creep, and nonlinear material behavior. Validate by analysis and cycling when consequences matter.

## Bayonet and twist locks

- Separate pilot alignment, ramped locking motion, axial load shoulder, rotational stop, and optional detent.
- Use multiple lugs to balance the load, but avoid overconstraint when process error can make only one lug engage.
- Round lug roots and provide debris and wear clearance.
- Make release direction, grip, and visual alignment unambiguous.

## Threads, screws, nuts, and inserts

- Prefer coarse, rounded, process-qualified printed threads. Add lead-in, runout, and radial clearance.
- Keep service load on a shoulder or flange rather than the first thread alone.
- Use captive nuts when a replaceable metal thread and simple installation are more important than a hidden exterior.
- Size a self-tapping pilot and boss through material-specific tests. Check hoop stress, edge distance, and driver access.
- Start a heat-set or press insert pocket from the exact insert manufacturer's data, but do not treat that hole as final. Print a representative diameter ladder and qualify pre-seating, insertion temperature or force, alignment, depth, boss geometry, pull-out, torque-out, and splitting over repeated specimens.
- Add an entry chamfer or shallow relief when it helps alignment and gives displaced material a controlled destination. Preserve a controlled insertion stop and adequate load-bearing material around and below the insert.
- Derive boss candidates from the required pull-out, torque, clamp load, edge distance, continuous wall paths, and the exact insert geometry. If no validated boss rule exists, screen radial boss thickness and material below the insert as separate parameters after selecting a workable hole range.
- Use at least three specimens per promising comparative condition. Increase sample count and production coverage when variation, consequence, or the required confidence demands it.
- Use washers or flanges to spread clamp load and account for polymer creep under preload.
- Let interlocking faces, shoulders, or keys locate the parts and react shear or bending where practical; use the fastener primarily to maintain clamp. Do not make the screw shank or a printed thread carry every joint function by default.
- Capture removable fasteners when loose hardware can enter machinery or the environment. If loss of one fastener is unacceptable, add independent retention or a fail-safe load path and test the joint with that fastener loose or absent.

## Compare structural joints

- Compare candidates in the same material condition, orientation, local wall strategy, span, and load direction.
- Include a continuous unsplit control when it provides a meaningful upper reference.
- Record initial stiffness, permanent deformation, interface slip, peak load, failure location, and whether the joint can be inspected or disassembled.
- A joint that survives once but damages its interface, wedges irreversibly, or moves failure into an unsafe region has not necessarily improved the assembly.

## Adhesive and solvent-assisted joints

- Verify adhesive chemistry against both printed materials, coatings, and the service environment.
- Prefer shear, compression, and broad bonded area over peel and cleavage.
- Add shallow texture, grooves, perforations, or internal keys only when they improve wetting and mechanical interlock without starving the bond line.
- Provide an adhesive reservoir, air escape, squeeze-out path, alignment feature, and clamping method.
- Define cleaning, surface preparation, bond-line control, cure, and inspection as part of the joint.

## Hinges, pivots, bearings, and ball joints

- Use alternating knuckles around a replaceable metal or polymer pin when durability and serviceability matter.
- Add axial retention without clamping the rotating faces.
- Keep bearing length, running clearance, and contact pressure consistent with the material and expected wear.
- Use a living hinge only with a qualified material, print direction, thickness, bend radius, and cycle test.
- For ball-and-socket joints, separate the insertion ramp from the final bearing band. Provide relief slots only where their root strain is controlled.

## Print-in-place joints

- Use a free-motion clearance proven on the production process and orientation.
- Prevent unsupported roofs from sagging into the gap.
- Provide resin drainage, powder escape, or removable support access.
- Include breakaway starters only when the user can reach and remove them without damaging the mechanism.
- Test motion after the full post-process, not directly off the machine.

## Magnets

- Use geometry to locate and react shear; use magnets mainly for normal retention.
- Key polarity and prevent incorrect insertion.
- Retain the magnet with a lip, backer, or qualified adhesive so repeated opening does not pull it from the pocket.
- Keep brittle magnets away from direct impact and excessive press-fit stress.
