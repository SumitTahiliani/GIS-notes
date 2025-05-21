## Georeferencing

a map coordinate system is defined using a map projection ( a method by which the curved surface of the earth is portrayed on a flat surafa)

georeferencing transforms images/maps from geometric coordinate system to geogrpahic coordinate system using base map/image having geographic coordinates

when we georeference raster data, we define its location using map coordinates and assign the coordinate system of the data frame. This allows raster data to be viewed, queried, and analyzed with other geographic data

When an image is acquired from satellite, the resulting image has certain systematic and non systematic geometric errors introduced through sensor distortion, scan skewnessm panoramic distortion and attitude of the platform (velocity, altitude, pitch, roll, yaw)

![[../attachments/Pasted image 20250521203017.png]]

Images are stored as raster data, where each pixel in the image has a row and column number and hence are in geometric coordinate system. Hence, in order to display and analyse images with other georeferenced maps/datasets it is necessary to establish an **image-to-world transformation** that converts the image coordinates to real-world coordinates

 A common method of georeferencing is is to statistically find a polynomial of a given order that minimizes the error in transformation from the original image coordinates to the rectified image coordinates. The transformation is found by performing a **Least Squares fit** for the coefficients of the given polynomial using ground control points that are picked by the user
 ![[../attachments/Pasted image 20250521221857.png]]
Any point that does not move wrt time can be takens as a GCP. Eg. bridge on a river, railway bridges, rivers etc. Conversely bending of a river in plain area cannot be taken as a reference point

#### Steps for georeferencing
1. Identifying GCP and registering them with the master map
2. Finding the polynomial coefficient (transformation function)
3. Finding the pixel values

#### Orders of polynomial in transformation function
Order of polynomial depends on amount of distortion in image

![[../attachments/Pasted image 20250521222357.png]]

- Simple transformation from geometric domain to geographic domain can be done using first order polynomials or conformal transformation.
- If image requires rotation or change in scale then we use second order/affine transformation
- Second order plus warping (image covers large enough part of earth that it is curved) requires third order polynomials

Usually we do not go beyond third order since most of the distortion can be taken care of using third order. Going higher we need more control points which can be challenging

![[../attachments/Pasted image 20250521222830.png]]

#### Applying transformation to pixel values
Once the transformation is found, it is applied to every pixel of the input image 

The other operation performed is determining the pixel value. This is done using resampling techniques (nearest neighbour, bilinear of cubic convolutions)

The transformation can be represented by a polynomial of order m such as: 
 
$$ x' = \sum_{j=0}^{m} \sum_{k=0}^{m-j} a_{jk} x^j y^k $$
$$
y' = \sum_{j=0}^{m} \sum_{k=0}^{m-j} b_{jk} x^j y^k
$$

We are trying to find new locations of all pixels using existing geometric data

![[../attachments/Pasted image 20250521223650.png]]

Y scale has negative value because we come from top to bottom. Origin of image and geographic coordinate system are different

#### Interpreting root mean square error

When the general formula is derived and applied to the control point, a measure of the error (called residual error) is returned. The error is the difference between where the from point ended up as opposed to the actual location that was specified (the to point position). Essentially where it should have been vs where it actually was

Total error computed by taking RMS sum of all residuals to commpute the RMS error

**Note:** Adding more GCPs does not always lead to a better registration. If possible, GCPs should occupy the entire raster dataset rather than being concentrated in a small area

Generally, having atleast one GCP near each corner of the dataste and few throughout the interior produces best results

**Note:** When the error is large, we can remove or add control points to adjust. Additionally, although RMS is a good assessment of the transformation accuracy, a low RMS does not always mean accurate registration. It may still contain significant errors due to poorly entered control points

#### Resampling methods
##### Nearest neighbour resampling

determines the pixel value from the closest pixel to the input coordinate specified, and assigns that value to the output coordinate

This method is considered the most efficient procedure in terms of computation time.

It does not alter the pixel values, this is desirable if subtle changes in pixel value need to be retained. However this method induces a small error into the corrected image. The corrected image may be offset spatially by up to half a pixel

##### Bi-linear resampling
Determines the weighted average of the four nearest pixels in the uncorrected image. Closer the central points of the pixels, the greater contribution or weight it will have to the final DN value to be assigned to the corrected pixel 

Bi-linear resampling generates a smoother appearing resampled image, the pixel value is altered in the image resulting in blurring or loss of image resolution

This method requires three to fourt times the computation time compared to nearest neighbours method

##### Cubic convolution
Weighted average of sixteen surrounding pixels of the uncorrected image to approximate the pixel value of the new pixel space in the corrected image

