## Pre-processing Spatial datasets-I

### Primary
Basic GIS functions (usually refers to GIS tools eg. area and distance measurments, buffer generation etc.)

### Area and distance measurments
1. Manual
2. Auto population in attribute table

#### Measurment types

|                |                                                                                                                                                                                                                                                                                                                              |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Planar         | Planar measurments use 2D Cartesian mathematics to calculate lengths and areas.<br>This is only possible and available when measuring in a projected coordinate system and the 2D plane of that coordinate system will be used as the basis for the measurments.<br>Generally all the area measurments calculated are planar |
| Geodesic       | The shortest line between any two points on the earth's surface on a spheroid(ellipsoid).<br>One use for a geodesic line is when you want to determine the shortes distance between two cities for an airplane's flight path.<br>This is also known as the great circle line if based on a sphere rather than an ellipsoid   |
| Loxodrome      | Not the shortest distance between two points but instead defines the line of constant bearing or azimuth<br>Great circle routes are often broken into a series of loxodromes which simplifies navigation<br>Also known as rhumb line                                                                                         |
| Great Elliptic | Line on a spheroid defined by the intersection at the surface by a plane that passes through the center of the spheroud and the start and endpoints of a segment<br>This is also known as the great circle when a sphere is used<br>Allows us to create lines only                                                           |

##### Measuring direction of aspect
- Input is DEM. Aspect identifies the downslope direction of the maximum rate of change in value from each cell to its neighbours.
- It can be thought of as slope direction
- The values of each cell in the output raster indicate the compass direction that the surface faces at the location
- It is measured clockwise in degrees from 0 (due north) to 360 (again due north), coming full circle.
- Flat areas having no downslope are given a value of -1
- The value of each cell in the aspect dataset indicates the direction the cell's slope faces

##### Slope calculation
- Calculation can either be in degrees or percentage
- Slope is the maxmimum rate of change between each cell and its neighbors, for example the steepest downhill descent for the cell (the maximum change in elevation over the distance between the cell and its eight neighbours)

![[../attachments/Pasted image 20250521232334.png]]

- Every cell in the output raster has a slope value
- The lower the slope value, flatter the terain and vice versa