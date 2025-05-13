## Vector Data Compression
Resampling of vector data is the key here.

The conception is that to compress data, we extract a subset B from the set A which is a collection of the points that compose vector graphics, then try to make this subset B reflect the original dataset A within the certain accuracy as much as possible, and make sure the points of subset B are as little as possible.

generalised vector data compression should include storage compression and resampling of vector data. Storage compression is done to reduce the amount of vector data and then to speed up transmission and processing by converting the data type or file type

Vector data usually does not have redundancy but in large datasets compression becomes necessary.

#### Point data compression
UTM coordinates(Universal Traverse Mercarator), points are described by easting and northing coordinates respectively.

If data is over a smaller area, there is considerable redundancy because all points have first two or three digits same.

To save space, it is possible to define a local origin and store all coordinates relative to new origin. These new coordinates will be smaller numbers than the original ones and can be stored in a smaller amount of storage.

#### Linear Features compression 
Procedure for point features can also be applied to linear features where only the first point is saved with the full coordinate information. All remaining coordinates use local origin as reference.

#### Freeman coding compression
Rasterising vector data onto a regular grid and proceeding with freeman/chain coding method.

