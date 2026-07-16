# Joint Selection

Select from function and failure mode before choosing a familiar shape.

## Decision sequence

1. Decide whether the joint must move, open repeatedly, open occasionally, or remain permanent.
2. Decide whether printed geometry alone is a requirement or non-printed hardware is acceptable.
3. Identify the dominant service load and the weakest likely print direction.
4. Assign locating, load-transfer, retention, stop, and assembly functions.
5. Shortlist two families and compare print risk, assembly risk, life, and serviceability.
6. Calibrate the selected interface on the production process.

## Family matrix

| Family | Best use | Strengths | Main risks |
| --- | --- | --- | --- |
| Slip-fit pins and keys | Repeatable location before another retainer acts | Simple, cheap, easy to inspect | Play, rotation with one round pin, weak printed pins |
| Press or interference fit | Compact permanent or low-cycle assembly | No hardware, distributed friction | Splitting, process variation, creep, high assembly force |
| Tongue and slot | Long seams, shear transfer, panel alignment | Broad load area, self-aligning | Binding, trapped air, weak thin tongues |
| Dovetail or T-slot | Guided assembly with transverse retention | Resists pull-apart across the seam | Requires an insertion path, wedges under error |
| Flexible fin or S-clip | Variation-tolerant embedded retention | Compliance absorbs fit error | Fatigue, root cracking, orientation sensitivity |
| Cantilever, U, torsion, or annular snap | Tool-free assembly and release | Few parts, fast assembly | Overstrain, creep, wear, layer delamination |
| Bayonet or twist lock | Repeated service with short rotation | Fast, positive stop, compact | Ramp wear, accidental release, lug shear |
| Printed thread | Large, coarse, low-load service joint | Fully printed and adjustable | Tooth damage, friction, fine-feature error |
| Screw with captive nut or insert | Reliable clamp and repeated service | Replaceable hardware, controlled preload | Boss failure, access, added parts and operations |
| Adhesive joint | Permanent sealed or cosmetic seam | Distributes load over area | Material compatibility, peel, cure control, irreversibility |
| Magnet with locator | Frequent light-duty access | Fast and quiet | Low structural retention, polarity and pocket failure |
| Pin hinge or printed bearing | One-axis rotation | Predictable motion and replaceable pin options | Wear, clearance, axial retention, knuckle splitting |
| Ball-and-socket | Multi-axis aiming or articulation | Compact adjustable motion | Socket strain, wear, difficult retention tuning |
| Print-in-place joint | No assembly access or part-count reduction | Captive mechanism, one build | Fused gaps, trapped support, weak orientation |
| Lap, finger, scarf, or panel key | Large parts and thin panels | Extends seam and spreads bending or shear | Visible seam, local thickness, assembly alignment |

## Quick exclusions

- Exclude a snap when the material cannot survive the required strain and cycles.
- Exclude a dovetail or T-slot when no insertion path exists.
- Exclude a press fit when a split outer wall, creep, or dimensional drift is unacceptable.
- Exclude printed threads when the required pitch is below proven process capability.
- Exclude magnets as the only structural retainer under shock, lifting, or safety-critical load.
- Exclude adhesive-only joints when surface preparation and curing cannot be controlled.
- Exclude print-in-place motion when support, resin, or powder cannot be removed.
