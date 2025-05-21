## Raster Data Compression
Raster data tends to be spatially auto correlated, meaning that objects which are close to each other tend to have similar pixel/cell values.

#### Run length coding/encoding/RLE (lossless)
The primary data elements are pairs of values or tuples. consisting of a pixel value and a repetition count which specifies the number of pixels in the run.

It allows the points in each mapping unit to be stoerd per row in terms, from left to right of a begin cell and end cell.
![[../attachments/Pasted image 20250514195648.png]]

 