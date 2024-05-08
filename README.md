# minBoundingBox
A minimum bounding box solver for point clouds using the principal component analysis (PCA) technique. Works with both 2D and 3D point clouds!

<p align="center" width="100%">
<img src="https://github.com/gasingh/minBoundingBox/blob/main/240508_pca_3d_bBox_kettle_preview_143614.jpg" width="300" /> 
<img src="https://github.com/gasingh/minBoundingBox/blob/main/240508_pca_3d_bBox_kettle_preview_143626.jpg" width="300" /> 
<img src="https://github.com/gasingh/minBoundingBox/blob/main/eigenValues%26EigenVectors_03c_2x2implementation_ptInput2g__img2_solved_fileShot-02_trim.JPG" width="300" /> <br>
</p>

`#statistics` `#linear-algebra` 

`#unsupervised learning` `#machine-learning` 

`#applied-maths` `#3d` `#geometry`

### Highlights
  - No external libraries such as numpy/scipy are used.
  - The solution is completely in Python, with no library calls.
  - The algorithm is integrated inside Rhino 3d, using the Rhinocommon API. 

### Intent
  - Rhino v7 doesnot support scientific computing libraries natively, as it runs IronPython.
  - I'm curious about learning how algorithms work!
  - Hence, this exploration employing matrices, and linear algebra!

### Pseudocode
  - _Math_
    - Construct a **2D Data Matrix**.
    - Compute the **Covariance Matrix**.
    - The current implementation considers a **sample population**, so all computations as (N-1).
    - Solve the Linear Equation System obtained by subtracting the **Lambda** from the variances in the Covariance Matrix (across the diagonal of the matrix). Solve the linear equation system to obtain the **eigenValues**.
    - Now, compute the **eigenVectors**.
    - The eigenvectors are the **principal components** of the 2D data. They span across the directions of minimum and maximum variance in the dataset.
  - _Geometry_
    - The extents of the dataset along the two principal components is derived by associatively sorting the Projections of the dataset with the **projection formula** on the respective PC vectors, and their respective **projections** (dot products).
    - Finally, some simple Rhinocommon gymnastics to **compute bounding box geometry** from the obtained information above.
    - Done!

### References
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

<!--- <img src="https://github.com/gasingh/minBoundingBox/blob/main/240426_minimumBoundingBox_simpleCapture.gif" style="border: #000000 6px outset; width="500";display: block; margin-left: auto; margin-right: auto;" title="BoundingBox2d-01" /> --->

<p align="center" width="100%">
<b>2D BOUNDING BOXES!</b><br><br>
<img src="https://github.com/gasingh/minBoundingBox/blob/main/240426_minimumBoundingBox_simpleCapture2.gif" width="500" />
</br>
<b>GIF 1</b> </br> 2D bounding boxes: on shape point clouds
</p>
<p align="center" width="100%">
<img src="https://github.com/gasingh/minBoundingBox/blob/main/240426_minimumBoundingBox_simpleCapture3.gif"  width="500" />
</br>
<b>GIF 2</b> </br> 2D bounding boxes: on point clouds
</p>

___


<p align="center" width="100%">
  <b>3D BOUNDING BOXES!</b><br><br>
<img src="https://github.com/gasingh/minBoundingBox/blob/main/240508_3dboundingBox_ViewCapture20240508_031153.jpg"  width="500" />
 </br>
<b>IMG 1</b> </br> 3D bounding boxes: on point clouds
</p>
<br>
<p align="center" width="100%">
<img src="https://github.com/gasingh/minBoundingBox/blob/main/240508_pca_3d_preview.gif"  width="500" /> <br>
<b>GIF A</b> </br> 3D bounding boxes: on point clouds: principal symmetry planes! <br>
<img src="https://github.com/gasingh/minBoundingBox/blob/main/240508_pca_3d_bBox_kettle_preview.gif"  width="500" /> <br>
<b>GIF B</b> </br> 3D bounding boxes: on point clouds: bounding boxes on kettle geometries <br>
<img src="https://github.com/gasingh/minBoundingBox/blob/main/240508_pca_3d_bBox_kettle_preview_143509.jpg" width="500" /> <br>
<img src="https://github.com/gasingh/minBoundingBox/blob/main/240508_pca_3d_bBox_kettle_preview_143614.jpg" width="500" /> <br>
<img src="https://github.com/gasingh/minBoundingBox/blob/main/240508_pca_3d_bBox_kettle_preview_143626.jpg" width="500" /> <br>
<b>IMGs 2,3,4</b> </br> 3D bounding boxes: on point clouds: bounding boxes on kettle geometries
</p>

___


<p align="center" width="100%">
  <b> Note </b> <br>
  [1] GIFs scaled for viewing on a mobile phone. <br>
  [2] 3d meshes sourced from <a href="https://github.com/nmwsharp/DDGSpring2016/tree/master/meshes"> here </a>. <br>
</p>

___
  
<p align="center" width="100%">
<b>Favourite Book Covers!</b> <br>
<img src="https://www.cs.sfu.ca/~haoz/pubs/images/cohenor_book.png" height="200" />
<img src="https://m.media-amazon.com/images/I/71eYVeebbFL._AC_UF1000,1000_QL80_FMwebp_DpWeblab_.jpg" height="200" />
<img src="https://m.media-amazon.com/images/I/6166Bsz0dPL._AC_UF894,1000_QL80_.jpg" height="200" />
</p>
