## Preprocessing of Spatial Datasets-II

### Image Merging
Multi sensor image fusion is the process of combining relevant information from two or more images into a single image. The resulting image formed is more informative than any of the input images

Several applications require high spatial and high spectral resolution in the same image for analysis

In satellite imaging, two types of images are available. Panchromatic images with high spatial resolution and multispectral images with coarser resolution. The pan images are merged with multispectral data to convey better information

Colour space representation using a cube model:
 ![[../attachments/Pasted image 20250522214043.png]]

Image merging technique:
![[../attachments/Pasted image 20250522214310.png]]

PAN image has 5.8metre resolution and LISS-III has 23.5 metre resolution and is multispectral(3 bands). First step is georeferencing (iamge to image registration). 
Then we take the registered FCC image and convert RGB to IHS (Intensity, Hue, Saturation). Pan image becomes intensity image while hue and saturation is taken from conversion, finally we do backward transformation from IHS to RGB

Constraints:
- Dates of the two scenes should be as near as possible

Use case of merging:
![[../attachments/Pasted image 20250522214954.png]]

