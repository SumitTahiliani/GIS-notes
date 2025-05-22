## Spatial Interpolation Techniques-II

### Non linear interpolation
> [!Tobler's Law of Geography]
> Points close together in space are more likely to bhave similar values than points farther apart

Includes distance weighted interpolation techniques

#### Inverse Distance Weighted Interpolation method
- IDW interpolation estimates cell values by averaging the values of sample data points in the neighbourhood of each processing cell
- The closer a point is to the center of the cell bebing estimated, the more weight it has in the averaging process
- It assumes that the variable being mapped decreases in influence with distance from its sampled location

The characteristics of an interpolated surface can be controlled by limiting the input points used. Points can be limited by specifying a maximum number of points (which selects the nearest points until the maximum number is reached). Alternatively a radius can be specified in map units

