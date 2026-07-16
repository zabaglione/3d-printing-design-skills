# Research Source Notes

These sources support the representation and manufacturing distinctions in this skill. They are implementation references, not universal feature dimensions.

Accessed 2026-07-16.

## Geometry generation and displacement

- [Blender Geometry Nodes manual](https://docs.blender.org/manual/en/latest/modeling/geometry_nodes/index.html) — curve, instance, mesh, volume, and procedural texture operations for non-destructive generators.
- [Geometry to Instance](https://docs.blender.org/manual/en/4.2/modeling/geometry_nodes/geometry/geometry_to_instance.html) — why instancing avoids creating a large joined mesh during iteration.
- [Displace Modifier](https://docs.blender.org/manual/en/5.0/modeling/modifiers/deform/displace.html) — physical vertex displacement from procedural or image textures, with coordinate, direction, strength, and baseline controls.
- [Geometry Nodes texture notes](https://docs.blender.org/manual/en/3.4/modeling/geometry_nodes/texture/index.html) — procedural texture frequencies can exceed geometric sampling and create missing detail or aliasing.

## Manufacturing file semantics

- [3MF Core Specification](https://github.com/3MFConsortium/spec_core/blob/master/3MF%20Core%20Specification.md) — core mesh, material, composition, extension, and interoperability rules.
- [3MF Materials and Properties Extension](https://github.com/3MFConsortium/spec_materials/blob/master/3MF%20Materials%20Extension.md) — material and 2D texture properties; these describe appearance or material intent rather than automatic relief.
- [3MF Beam Lattice Extension](https://github.com/3MFConsortium/spec_beamlattice) — a compact standardized representation for beam lattices when the consumer supports the extension.
- [3MF Volumetric Extension](https://github.com/3MFConsortium/spec_volumetric) — volumetric and implicit representation work for spatially varying properties and complex fields.

## Print-oriented texture examples

- [PrusaSlicer Fuzzy Skin](https://help.prusa3d.com/article/fuzzy-skin_246186) — slicer-side random perimeter resampling, regional application, thickness, and point-distance controls.
- [BumpMesh by CNC Kitchen](https://bumpmesh.com/) — a print-oriented displacement implementation with planar, cylindrical, spherical, cubic, and triplanar mapping; masks; overhang and bed-contact protection; resolution and triangle limits; and baked STL or 3MF export.
- [Texturing 3D Prints for Strength](https://www.youtube.com/watch?v=3-ygdNQThAs), CNC Kitchen — an example of texture interacting with printed mechanical behavior rather than appearance alone.
- [3D Printing Surface Finishes](https://www.slant3d.com/slant3d-blog/3d-printing-surface-finishes-tips-for-mass-production-3d-printing), Slant 3D — production tradeoffs among orientation, layer appearance, surface finish, and throughput.

## Synthesis rules

- Use tool documentation to understand representations, but keep the skill tool-independent.
- Treat shader, material, and slicer texture as separate from baked geometry.
- Keep procedural frequency below both geometric sampling and qualified manufacturing resolution.
- Preserve an editable generator and verify a baked manufacturing artifact.
- Qualify tactile and structural claims with physical coupons.
