# Minimum Bounding Box 

A minimum bounding box solver for Rhino3D. All the math is coded from scratch including building up a matrix library, and necessary statistical analysis functions for computation of eigenvalues and eigenvectors for 2x2 and 3x3 matrices. Works with both 2D and 3D point clouds, and meshes! This assists in embedding the tool directly inside Rhino 3D (version 7), where there is no direct support for scientific libraries from the Python ecosystem. (.NET API, IronPython) 

<p align="center" width="100%">
<img src="https://github.com/gasingh/minBoundingBox/blob/main/240508_pca_3d_bBox_kettle_preview2_150421.jpg" width="200" /> 
<img src="https://github.com/gasingh/minBoundingBox/blob/main/240508_pca_3d_bBox_kettle_preview2_150433.jpg" width="200" /> 
<img src="https://github.com/gasingh/minBoundingBox/blob/main/eigenValues%26EigenVectors_03c_2x2implementation_ptInput2g__img2_solved_fileShot-02_trim.JPG" width="200" /> 
<img src="https://github.com/gasingh/minBoundingBox/blob/main/240508_3dboundingBox_ViewCapture20240508_031153.jpg" width="200" /> <br>
</p>

`#statistics` `#linear-algebra` `#unsupervised learning` `#ML` `#applied-maths` `#3d` `#computational geometry`

## Toolkit Purpose
The minimum bounding box toolkit exposes the following new functionalities inside Rhino3D as commands:
1. 2D Symmetry planes from point clouds and 3d mesh data.
2. Minimum Bounding Boxes in 3D.
3. The three principal axes from any input geometry.

## Use cases
1. **3D Axis Systems**: This can be a very useful tool in deriving automatic axis systems to aid in precision 3d modeling tasks.
2. **Estimation and Analysis**: Volumetric estimations, and packaging estimations of digital artifacts.

## Documentation 
### i. 2d minimal bounding boxes

<p align="center" width="100%">
<img src="https://github.com/gasingh/minBoundingBox/blob/main/240426_minimumBoundingBox_simpleCapture2.gif" width="300" />
<img src="https://github.com/gasingh/minBoundingBox/blob/main/240426_minimumBoundingBox_simpleCapture3.gif"  width="300" />
</br>
<i> GIF 1, 2: 2D bounding boxes: on point clouds(L) & on point clouds(R) </i>
</p>

### ii. 3d symmetry planes across point clouds

<p align="center" width="100%">
<img src="https://github.com/gasingh/minBoundingBox/blob/main/240508_3dboundingBox_ViewCapture20240508_031153.jpg"  width="300" /> 
<img src="https://github.com/gasingh/minBoundingBox/blob/main/240508_pca_3d_preview.gif"  width="300" /> <br>
<i> IMG(L) GIF(R): 3D bounding boxes: on point clouds: principal symmetry planes! </i>  <br>
</p>

### iii. 3d axis system generation

<p align="center" width="100%">
<img src="https://github.com/gasingh/minBoundingBox/blob/main/240508_pca_3d_bBox_kettle_preview.gif"  width="300" /> <br>
GIF B: 3D bounding boxes: on point clouds: bounding boxes on kettle geometries </i> <br>
<img src="https://github.com/gasingh/minBoundingBox/blob/main/240508_pca_3d_bBox_kettle_preview2_150444.jpg" width="300" /> 
<img src="https://github.com/gasingh/minBoundingBox/blob/main/240508_pca_3d_bBox_kettle_preview2_150433.jpg" width="300" /> <br>
<i> IMGs B,C,D:  3D bounding boxes: on point clouds: bounding boxes on kettle geometries </i> <br>
</p>

### iv. 3d minimal bounding boxes on Point Clouds and Meshes

<p align="center" width="100%">
<img src="https://github.com/gasingh/minBoundingBox/blob/main/240508_pca_3d_bBox_kettle_preview2_150421.jpg" width="300" />
<img src="https://github.com/gasingh/minBoundingBox/blob/main/240508_pca_3d_bBox_kettleConfig_preview.gif"  width="300" /> </br>
<i>IMG E: 3D bounding boxes: on Meshes: bounding boxes on kettle geometries </i>
</p>

<!--
## Rhino Integration

<p align="center" width="100%">
<img src="https://github.com/gasingh/ICP-3D/blob/main/Capture_silencedPCA_solver_02_snip-00_web.JPG" width="800" /> </br>
<i> IMG F: Screenshot from Rhino3D with the PCA integrated with Rhinocommon to report & augment geometries </i> <br>
</p>

___

<details>
  <summary><h4> References </h4></summary>
  
  REFERENCES
  
  - _Websites_
    - [The Mathematics Behind Principal Component Analysis](https://towardsdatascience.com/the-mathematics-behind-principal-component-analysis-fff2d7f4b643)
    - [What is the purpose of subtracting the mean from data when standardizing?](https://math.stackexchange.com/questions/317114/what-is-the-purpose-of-subtracting-the-mean-from-data-when-standardizing)
  - _Videos (YouTube)_
    - ultra-cool
      - [Principal Component Analysis- YouTube Playlist by Victor Lavrenko | 2014 ](https://www.youtube.com/playlist?list=PLBv09BD7ez_5_yapAg86Od6JeeypkS4YM)
      - [COVARIANCE AND VARIANCE - YouTube Playlist by Michel van Biezen | 2021](https://www.youtube.com/playlist?list=PLX2gX-ftPVXWHdoWSeshfEbRarb_LiX-e)
    - cool
      - [StatQuest: Principal Component Analysis (PCA), Step-by-Step by Josh Starmer | 2018 ](https://www.youtube.com/watch?v=FgakZw6K1QQ&vl=en)
      - [StatQuest: PCA main ideas in only 5 minutes!!! by Josh Starmer | 2017 ](https://www.youtube.com/watch?v=HMOI_lkzW08)
      - [Principal Component Analysis (PCA) by Luis Serrano | 2019 ](https://www.youtube.com/watch?v=g-Hb26agBFg&t=193s)
      - [The applications of eigenvectors and eigenvalues- That thing you heard in Endgame has other uses by Zach Star | 2019 ](https://www.youtube.com/watch?v=i8FukKfMKCI&t=323s)
      - [The Applications of Matrices | What I wish my teachers told me way earlier by Zach Star | 2019 ](https://www.youtube.com/watch?v=rowWM-MijXU&t=647s)
      - [Eigenvectors and eigenvalues | Chapter 14, Essence of linear algebra by 3Blue1Brown | 2016 ](https://www.youtube.com/watch?v=PFDu9oVAE-g)
    - also cool
      - [Principal Component Analysis (PCA) by Steve Brunton | 2020 ](https://www.youtube.com/watch?v=fkf4IBRSeEc)
      - [Principal Components Analysis - Georgia Tech - Machine Learning by Udacity | 2015 ](https://www.youtube.com/watch?v=kw9R0nD69OU)
      - [Principal Component Analysis (PCA) by Visually Explained | 2021 ](https://www.youtube.com/watch?v=FD4DeN81ODY)
      - [PCA : the basics - simply explained by TileStats | 2021 ](https://www.youtube.com/watch?v=dz8imS1vwIM)
- _Concept Basics_
  - _Specific Searches_
    - Google: eigenvector computation by hand
      -  [Eigenvector - Definition, Equations, and Examples | ByJus](https://byjus.com/maths/eigenvector/#:~:text=Find%20the%20eigenvalues%20of%20the,is%20associated%20with%20the%20eigenvalue.)
      - [❖ Finding Eigenvalues and Eigenvectors : 2 x 2 Matrix Example ❖ by patrickJMT | 2014 ](https://www.youtube.com/watch?v=IdsV0RaC9jM)
      - [lecture14.pdf | Introduction to Numerical Methods and Matlab Programming for Engineers | Department of Mathematics at Ohio University | 2023 ](http://www.ohiouniversityfaculty.com/youngt/IntNumMeth/lecture14.pdf)  
  - _Books_
    - [A Sampler of Useful Computational Tools for Applied Geometry, Computer Graphics, and Image Processing by Daniel Cohen-Or, Chen Greif, Tao Ju, Niloy J. Mitra, Ariel Shamir, Olga Sorkine-Hornung, Hao (Richard) Zhang | 2015](https://www.taylorfrancis.com/books/mono/10.1201/b18472/sampler-useful-computational-tools-applied-geometry-computer-graphics-image-processing-tao-ju-niloy-mitra-daniel-cohen-chen-greif-olga-sorkine)
    - [Linear Algebra for Everyone by Gilbert Strang | 2020](https://math.mit.edu/~gs/everyone/)
    - [Geometry for Programmers by Oleksandr Kaleniuk | 2023](https://www.manning.com/books/geometry-for-programmers)
    - [Coding The Matrix: Linear Algebra Through Computer Science Applications by Philip Klein | 2013](https://codingthematrix.com/)

___
  
<p align="center" width="100%">
<b>Favourite Book Covers!</b> <br>
<img src="https://www.cs.sfu.ca/~haoz/pubs/images/cohenor_book.png" height="200" />
<img src="https://m.media-amazon.com/images/I/71eYVeebbFL._AC_UF1000,1000_QL80_FMwebp_DpWeblab_.jpg" height="200" />
<img src="https://m.media-amazon.com/images/I/6166Bsz0dPL._AC_UF894,1000_QL80_.jpg" height="200" />
</p>

___

<p align="center" width="100%">
  <b> Mesh Resources </b> <br>
  [1] 3d meshes sourced from <a href="https://github.com/nmwsharp/DDGSpring2016/tree/master/meshes"> DDG2016 </a>. <br>
</p>


</details>

-->
