# Mapping, Printability, and Verification

## Choose a mapping domain

| Mapping | Prefer when | Watch for |
| --- | --- | --- |
| Planar | flat panels and shallow patches | stretching on slopes, abrupt border |
| Cylindrical | bottles, handles, tubes, rings | axial seam, cap transition, circumference closure |
| Spherical | near-spherical forms | poles, meridian seam, area distortion |
| Triplanar or cubic | box-like or irregular forms without authored UVs | blending artifacts, motif discontinuity at direction changes |
| UV or patch-based | deliberate art direction over complex surfaces | unwrap distortion, island seams, scale inconsistency |
| Surface-intrinsic | even spacing or geodesic flow matters | algorithm cost, singularities, difficult closure |
| Volumetric | texture fills or cuts through the body | thresholding, trapped volumes, representation support |

Preview a coordinate grid or a simple directional motif before the final texture. It exposes scale distortion and flipped orientation more clearly than noise.

## Control seams and boundaries

- Put seams on a hidden, low-wear, low-stress, or naturally divided region.
- Match phase and pitch around periodic cylindrical or looped domains.
- Use a border, fade, or designed interruption when exact closure would distort the pattern.
- Prevent masks from crossing datums, seals, holes, fits, bed contact, support contacts, or thin edges.
- Use a smooth falloff where displacement would otherwise end in a sharp notch.
- Preserve a flat reference region when the part needs measurement, fixturing, or process inspection.

## Match geometric sampling to the texture

The source surface must contain enough samples to represent the narrowest retained feature and highest useful curvature. A procedural field can contain frequencies that the mesh and printer cannot reproduce.

- Start coarse for composition, then refine only the accepted regions.
- Compare the sampling length, pattern wavelength, relief amplitude, and process resolution.
- Remove frequencies that disappear in slicing instead of exporting invisible triangles.
- Inspect faceting at silhouettes and glancing angles.
- Record tessellation or voxel resolution as a manufacturing parameter.

Keep repeated elements as instances and curves as centerlines while editing. Realize, boolean, or mesh them only when the target operation requires explicit geometry. Maintain a triangle or voxel budget appropriate to the downstream CAD, slicer, and archival format.

## Protect base geometry

For inward displacement, compute or inspect:

`remaining_section = base_section - maximum_inward_depth`

Use the local surface normal only when it produces a valid offset over the amplitude and curvature range. Large offsets near tight concave or convex regions can fold or self-intersect.

- Mask tight radii and acute corners, reduce amplitude, or use a remeshed implicit union.
- Keep peaks away from sliding, sealing, and wear datums.
- Round load-bearing groove roots and strand junctions.
- Do not let relief break through a shell unless porosity is intentional.
- Treat a texture that changes stiffness or section as structural geometry and revalidate the part.

## Process reasoning

### FDM/FFF

- Compare strand, groove, and wall sections with qualified line width and layer height.
- Choose orientation so critical relief does not become unsupported downward faces or fragile Z-oriented peaks.
- Inspect whether valleys cause excessive seams, travels, retractions, or unfilled gaps.
- Keep bed-contact surfaces flat or explicitly mask and restore them.
- Treat slicer fuzzy skin as a profile-specific perimeter perturbation, not portable source geometry.

### SLA/DLP

- Compare relief and gaps with optical resolution, exposure, orientation, and support access.
- Avoid cups, resin traps, inaccessible valleys, and unsupported islands.
- Account for cleaning, post-cure, and support removal changing fine texture.

### SLS/MJF and powder processes

- Provide powder escape from cellular, woven, or porous structures.
- Avoid long blind channels and cell networks that cannot be cleaned or inspected.
- Account for provider-specific feature limits, grain, thermal distortion, and surface finishing.

## Functional consequences

Texture can alter more than appearance:

- grip depends on direction, pressure, compliance, contamination, and wear;
- grooves can initiate cracks or redirect layer paths;
- protrusions can abrade mating parts or concentrate contact pressure;
- porous textures change airflow, fluid retention, cleaning, and acoustic behavior;
- dense relief increases surface area, file size, print time, and perimeter count;
- random geometry can add production variation unless the seed and process are fixed.

State these as hypotheses until tested on representative geometry.

## Build a texture coupon

Choose the smallest coupon that preserves the risk:

- flat tile for relief scale, feel, and process resolution;
- cylinder or curved patch for mapping seam and distortion;
- cropped shell for minimum remaining wall and slicing behavior;
- repeated cell block for connectivity, powder or resin removal, and strength;
- print-in-place swatch for knit, weave, or flexible lattice motion.

Use a labeled ladder or matrix across uncertain variables. A practical screening matrix can vary pattern scale on one axis and amplitude or section on the other. Print promising conditions at least three times before treating the result as repeatable.

Record visual and tactile judgments against a physical reference or ranked sample, not memory alone.

## Inspect and export

Before export:

- apply or bake physical displacement;
- realize instances when the target format or consumer does not preserve them;
- confirm units, transforms, normals, connected components, and watertightness;
- remove unintended internal faces and duplicate shells;
- check minimum section and self-intersections after booleans or remeshing;
- retain the untextured source and generator separately from the baked output.

After export, reopen the manufacturing file and inspect the sliced layers or exposure regions.

3MF can carry mesh geometry, materials, texture coordinates, and optional extensions. Consumer support for material, beam-lattice, implicit, or volumetric extensions varies. Declare every required extension and provide a baked mesh fallback when interoperability matters. Do not assume a stored 2D texture or display property creates surface relief.

## Acceptance record

| Field | Value |
| --- | --- |
| Texture family and purpose | |
| Base model revision | |
| Generator revision and seed | |
| Mapping, seam, and mask | |
| Scale, amplitude, and section parameters | |
| Tessellation or voxel resolution | |
| Process, material, orientation, and profile | |
| Coupon revision and sample count | |
| Functional and appearance results | |
| File size, slicing time, and print time | |
| Qualified range and known limits | |
