## Raster Data
Stores images as rows and columns of numbers with a Digital Value Number(DN) for each cell. The data is classified as continuos(eg image) or thematic(where each cell denotes a feature type)

One cell can only have one attribute value (Each raster data layer represents one data value)

##### Features of Raster
1. Raster is simpler to store in computers
2. A point is single cell
3. Line is groups of neighbouring cells
4. Set up as rows and columns
5. Each cell/pixel is assigned a value

##### Difference between Image and Grid
Both are raster data models, shape of both can be rectangle or sqare

| Characteristics | Image                  | Grid                  |
| --------------- | ---------------------- | --------------------- |
| Unit            | Pixel                  | Cell                  |
| Value           | Only positive Integers | Both positive integer |

##### Arc Seconds
1 arc second == 30 metre
$1/3$ arc second == 90 metres

arc seconds is in terms of latitude and longitude

##### Vector vs Raster data
GIS works with three fundamentally different types of geographic data models: vector(discrete), raster(continuos) and TIN(continuos)

![[../attachments/Pasted image 20250513001233.png]]

In a vector model, information about points, lines and polygons is encoded and stored as a collection of x,y coordinates. The vector model is useful for describing discrete features but less useful when features are continuosly varying(eg soil type).

The raster model was evolved to model continuos features.

###### Advantages of Vector
- Accurate positional information that is best for stroing discrete thematic features (roads, shorelines, sea-bed featueres)
- Compact data storage requirements
- Can associate unlimited attributes with specific features

Vector database (especially with topology) does not require compression and is very high quality as it is. Hence less compression techniques have been developed for it. 

###### Advantages of Raster
- Most common data format 
- Easy to perform mathematical and overlay operations (due to its matrix structure)
- Satellite information is easily incorporated
- Better represents continuous type of data

![[../attachments/Pasted image 20250513002505.png]]
![[../attachments/Pasted image 20250513002701.png]]

Processing can be done either in grid cell or converted to vector format. Grid cells are faster at processing due to 2D array structure and also easy integration with remote sensing data.

Vector to Raster Conversion and vice versa
![[../attachments/Pasted image 20250513003213.png]]

### Uses of Vector and Raster
Raster data is useful for:
- Continuous data types: Elevation, slope, satellite photos
- Large area analysis
- Surface analysis
- Mathematical modelling
- Spatial details are not important

Vector Data:
- Discrete data types: trees, buildings, property boundaries
- Small study areas
- Spatial details are important
- Topology is needed for analysis