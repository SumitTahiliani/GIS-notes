---
tags:
  - "#topology"
---
## Topology
Describes spatial relationships between adjacent features (what is inside, what is outside)

> [!NOTE]
> Topology is a collection of rules that when coupled with with a set of editing tools and techniques, enables the geodatabase to more accurately model geometric relationships

Mathematical topolgy assumes that geographic features occur on a 2D plane. Through planar enforcement, spatial features can be represented through nodes, edged, or polygons

#### Advantages of topology
- Provide an automated way to handle digitizing and editing errors as well as artifacts
- Reduce data storage for polygons because boundaries between adjacent polygons is stored only once 
- Enables advanced spatial analysis such as adjacency, connectivity and containment(control)
- A map with topoly contains space-filling non overlapping polygons

#### Types of topological models
1. Path topological models
	1. Spaghetti model
	2. Polygon model
2. Graph Topological models
	1. DIME (Dual Independent map encoding)
	2. POLYVERT (Polygon Converter)
3. TIN (Triangulated Irregular Network)

![[../attachments/Pasted image 20250512175138.png]]