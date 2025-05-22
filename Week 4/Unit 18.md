## Spatial Interpolation Techniques-I
Turns raw data into useful information by adding greater informative content and value. It reveals patterns, trends and anomalies that might otherwise be missed

Spatial interpolation is the procedure of estimating the value of properties at unsampled sites within the area covered by existing observations

Interpolation predicts values for cells in a raster from a limited number of sample data points. It can be used to predict unknown values for any geographic point data, such as elevation, rainfall, chemical concentrations, noise levels etc

Spatial interpolation can be thought of as a reverse process that is used to select the few points from a DEM which accuractely represents the surface. The rationale behind this is the observation that points close together in space are more likely to have similar values than points far apart (Tobler's law of Geography)

### Understanding Surfaces
Each surface representation is useful for specific situations

A grid representation of a surface is considered to be a functional surface because of any given x,y location it stores only a single z value as opposed to multiple z values. These functional surfaces are continuous

Functional surfaces can be used to represent:
- Terrestial surfaces that depict earth's surface
- Statistical surfaces that describe demographic
- Mathematical surfaces that are based on arithmetic expressions.

Surface representation in the simplest form is done by storing x,y and z values that define the location of the sample. Contours or isolines are used to define a common cahracteristic along a line and technically, contours join locations of equal value to each other

In case of a countour line representing elevation, it is a line drawn on a map taht connects points of equal elevation above a datum that represents mean sea level.

### Classification of Interpolation methods

#### Global vs Local
Global interpolators determine a single function which is mapped across the whole region eg. trend surfaces

Local interpolators apply an algorithm repeatedly to a small portion of the total set of points. eg. IDW (Inverse Distance Weightage interpolation)

#### Exact vs Approximate
Exact honours the input data points (does not mean the entire surface is exact)

Approximate interpolators allow for uncertainty in the input data points, which allows for smoothing

#### Stochastic vs Deterministic
Stochastic methods incorporate the concept of randomness

Deterministic methods do not use probability theory