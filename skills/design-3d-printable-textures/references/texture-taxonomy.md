# Texture Taxonomy and Generators

Choose the representation from topology and function, not from the visual name of the pattern.

## Contents

- [Scale classes](#scale-classes)
- [Family matrix](#family-matrix)
- [Helices and swept-strand structures](#helices-and-swept-strand-structures)
- [Knit, weave, and braid](#knit-weave-and-braid)
- [Repeated motifs](#repeated-motifs)
- [Partitioned and cellular surfaces](#partitioned-and-cellular-surfaces)
- [Height-field displacement](#height-field-displacement)
- [Implicit and volumetric geometry](#implicit-and-volumetric-geometry)
- [Slicer and material textures](#slicer-and-material-textures)

## Scale classes

Use scale relative to the qualified process rather than fixed universal dimensions.

| Class | Physical effect | Typical representation |
| --- | --- | --- |
| Macrostructure | Changes silhouette, openings, motion, or primary load path | Solids, shells, swept curves, cells, beams |
| Mesostructure | Produces visible or tactile relief while preserving the base form | Displacement geometry, ribs, grooves, repeated motifs |
| Microtexture | Approaches the process resolution and mainly changes feel, gloss, or layer appearance | Qualified geometric relief or slicer perturbation |
| Appearance only | Changes rendering or material assignment without guaranteed shape | Color, roughness, normal, bump, or material maps |

A pattern may move between classes when scaled. Reclassify it after every major scale change.

## Family matrix

| Family | Use for | Primary parameters | Main risks |
| --- | --- | --- | --- |
| Swept curves | helices, strands, loops, braid, weave, veins, cables | centerline, pitch, phase, profile, crossing order | fused crossings, weak unsupported spans, excessive curvature |
| Repeated motifs | scales, studs, tiles, stitches, dimples | motif, spacing, orientation, phase, clipping | partial motifs, overlap, instance explosion |
| Surface cell graph | partitioned skins, honeycomb, crack or vein networks | seeds, metric, wall or beam width, clipping | disconnected islands, narrow edges, ugly closure seam |
| Volumetric cell field | foam, gyroid-like or blended porous bodies | field function, threshold, cell scale, shell offset | trapped material, thin regions, expensive meshing |
| Height-field relief | leather, wood grain, grip, logos, terrain-like bumps | map, amplitude, baseline, scale, projection | faceting, self-intersection, wall loss, mapping distortion |
| Sculpted or vector relief | controlled ornament, channels, lettering | curves, offsets, draft, depth, fillets | sharp valleys, fragile peaks, support scars |
| Slicer perturbation | fuzzy or randomized sidewall roughness | thickness, point distance, region | non-portable output, dimensional change, limited surfaces |
| Material or color texture | multi-material or full-color intent | image, UVs, material IDs | no physical relief, consumer support varies |

## Helices and swept-strand structures

Represent a helix as a centerline before adding thickness. A basic axial helix can be parameterized by:

`x(t) = radius * cos(t)`

`y(t) = radius * sin(t)`

`z(t) = pitch * t / (2 * pi)`

Create a second strand with a phase offset when required. Parameterize cross-links separately from the strand so their count, angle, and section can be changed without rebuilding the helix.

Check:

- terminal connections and how the structure joins the base;
- strand and cross-link sections in the intended orientation;
- unsupported spans and collision at small pitch;
- whether the helix is decoration, a compliant spring, or a load-bearing structure.

Do not infer mechanical spring behavior from visual similarity to a helix.

## Knit, weave, and braid

Model yarn or strip centerlines and their over-under order. Expose:

- course and wale pitch;
- loop height and width;
- yarn section and bend radius;
- crossing clearance or intentional fusion;
- repeat count, edge treatment, and closure phase.

For a rigid knit-like shell, union intended crossings and remove accidental near contacts. For flexible or print-in-place fabric, preserve qualified motion gaps and test the complete post-process. Avoid scaling a finished mesh when yarn section and gap must scale differently.

## Repeated motifs

Keep one authoritative motif and instance it over points, curves, or cells. Delay realization and boolean union until placement is accepted.

- Derive count from usable domain length and target pitch.
- Resolve closure by distributing pitch error, introducing a designed seam, or clipping within a border.
- Orient motifs from a stable local frame; do not let normals flip unpredictably near poles or inflections.
- Vary scale or rotation through bounded parameters and a saved seed.

## Partitioned and cellular surfaces

Treat a partitioned surface as a cell construction, not merely a visual noise texture.

1. Define a planar, surface, or volumetric domain.
2. Generate deterministic seed points with density and exclusion rules.
3. Compute cells or the dual graph using a declared distance metric.
4. Select cell walls, edges, faces, or struts according to the desired topology.
5. Clip to the target mask and create a designed border or closure seam.
6. Give every retained element a parameterized section or shell thickness.
7. Remove slivers, merge near-coincident vertices, and verify connectivity.

If the pattern carries load, test cell-size distribution, node geometry, anisotropy, and failure location. A decorative cell shell is not automatically an optimized lattice.

## Height-field displacement

For a scalar field `f(u, v)` normalized around a baseline, a common physical mapping is:

`p_textured = p_base + amplitude * f(u, v) * normal`

Choose whether displacement is outward, inward, or symmetric. Preserve the base body separately and track the minimum remaining section after inward displacement.

Treat a photograph or grayscale reference as source material, not measured height. Perspective, lighting gradients, cast shadows, highlights, and image compression can become false geometry. Rectify the repeat, remove illumination artifacts, define the high and low convention, preserve sufficient tonal precision, and record the processed map separately from the original. Make a tile seamless only when continuity is intended; otherwise design and mask its boundary.

Height fields cannot directly represent arbitrary overhangs, undercuts, tunnels, or strand crossings. Switch to explicit curves, solids, or an implicit field when topology must change.

## Implicit and volumetric geometry

Use signed-distance or density fields when many blended elements would make booleans fragile or meshes unmanageable. Keep the field, threshold, smoothing, and sampling resolution parametric.

Confirm that the full export and slicing chain supports the implicit, voxel, or lattice representation. Otherwise bake a mesh at a validated resolution and inspect it as a separate manufacturing artifact.

## Slicer and material textures

Slicer-generated roughness can be efficient when only a supported surface and one manufacturing profile need the effect. Record the slicer version, region, perturbation settings, and dimensional impact.

Color, roughness, normal, and bump maps can remain useful design intent. They do not become physical relief merely because a file format stores them. Convert the relevant scalar or vector field to manufacturing geometry when tactile or geometric behavior is required.
