---
tags:
  - "#tin"
---
## TIN Data structure
Surface representation derived from irregulary spaced point and breakline features. Input of TIN is points or polylines. Each sample point has an x,y coordinate and a z-value or surface value. The TIN model represeant a surface as a set of contiguous, non overlapping triangles.

Within each triangle the surface is represented by a plane and the triangles are made from a set of points called mass points.

#### Delaunay Triangulation
Proximal method that satisfies the requirement that a circle drawn through three nodes of a triangle will contain no other node
![[../attachments/Pasted image 20250513162135.png]]

A node table lists each triangle and its defining nodes. Edge table lists the three adjacent triangles for each facet.X Y coordinate table stores node coordinates, Z table stores elevation values. 

 The triangles vary in size based on the roughness/complexity of the terrain. 

#### Advantages/Disadvantages of TIN
- Terrain parameteres, eg slope and aspect claculated for each traingle and stored as an attribute of the facet
- For areas of complex relief, TIN works better than raster
- More detailed representation for higher density of data points
- Break-point features are more accurate (eg ridge lines, valley bottoms etc)
- Significantly more processing required to generate TIN to start
- Errors along edges

TIN can describe the surface at different levels of resolution, it is efficient for storing data but requires visual inspection and manual control of the network.

#### Applications of TIN
1. DEMs: Drawing contour lines and interpolation and computation of earth work (cuts and fills)
2. Surface Reconstruction: Constructionf of 3D models for industrial applications, games, simulators etc. 