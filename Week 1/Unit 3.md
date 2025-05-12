Different types of vector data

## Spatial Data in GIS
Week 1 Unit 3

#### Vector data
1. Point
2. Line/Polyline
3. Polygon

#### Raster data
1. Grid
2. Image

#### Vector data terminology
Vertex or node is a point that specifies a position on a line for arcs, polylines or polygons. A point in GIS is considered to be a 0-dimensional vector entity

Points are normally used to represent a geographic feature too small to be displayed as a line or area. e.g. roorkee within india will be a point due to relative sizing. If a map of haridwar is displayed then roorkee is a polygon/area 0 -> 2 dimensional entity.

![[../attachments/Pasted image 20250512155251.png]]

Coordinates in vector data are provided in geographical format (latitude/longitude) however some point features (e.g. airplane locations) might also have a Z coordinate to locate in 3D space.

3D point features embed the Z coordinates inside the geometry of the feature class. Simply put, Z values are automatically included with every new point feature, allowing representation of any 3D position irrespective of its relative position to the ground

#### Lines
Simplest 1 dimensional object is a straight line between two points (start node and end node) or a polyline when there are more than 2 points (start node, inter nodes and end node).

![[attachments/Pasted image 20250512162827.png]]

Same as vectors, some might include Z value or height. 3D line features embed their Z values inside the geometry, or shape field of their feature class.

Examples of 3D line features: underground transportation lines, aircraft flight paths

#### Polygons/Area
2 dimensional object (area as well as perimeter)

Polygons are used to represent Areas (fully encompassed by a series of connected lines)

A polygon is defined by the lines that make up its boundary and a point inside its boundary for identification. They have attributes that describe the geographic entity they represent

![[../attachments/Pasted image 20250512163652.png]]

