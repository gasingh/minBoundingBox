# minBoundingBox
A minimum bounding box solver for point clouds using the principal component analysis (PCA) technique. Works with both 2D and 3D point clouds!

<p align="center" width="100%">
<kbd><kbd>
<img src="https://github.com/gasingh/minBoundingBox/blob/main/eigenValues%26EigenVectors_03c_2x2implementation_ptInput2g__img2_solved_fileShot-02_trim.JPG" width="300" />
</kbd></kbd>
</p>

### Highlights
  - No external libraries such as numpy/scipy are used.
  - The solution is completely in Python, with no library calls.
  - The algorithm is integrated inside Rhino 3d, using the Rhinocommon API. 

### Intent
  - Rhino v7 doesnot support scientific computing libraries natively, as it runs IronPython.
  - I'm curious about learning how algorithms work!
  - Hence, this exploration employing matrices, and linear algebra!

### Pseudocode
  - Construct a **2D Data Matrix**.
  - Compute the **Covariance Matrix**.
  - The current implementation considers a **sample population**, so all computations as (N-1).
  - Solve the Linear Equation System obtained by subtracting the **Lambda** from the variances in the Covariance Matrix (across the diagonal of the matrix). Solve the linear equation system to obtain the **eigenValues**.
  - Now, compute the **eigenVectors**.
  - The eigenvectors are the **principal components** of the 2D data. They span across the directions of minimum and maximum variance in the dataset.
  - The extents of the dataset along the two principal components is derived by associatively sorting the Projections of the dataset on the respective PC vectors, and their respective projections (dot products).
  - Finally, some simple Rhinocommon gymnastics to compute a bounding box geometry from the obtained information above.
  - Done!

### References
  - __Websites__
    - [The Mathematics Behind Principal Component Analysis](https://towardsdatascience.com/the-mathematics-behind-principal-component-analysis-fff2d7f4b643)
    - [What is the purpose of subtracting the mean from data when standardizing?](https://math.stackexchange.com/questions/317114/what-is-the-purpose-of-subtracting-the-mean-from-data-when-standardizing)
  - __Videos (YouTube)__
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


  - __Books__
    - [A Sampler of Useful Computational Tools for Applied Geometry, Computer Graphics, and Image Processing by Daniel Cohen-Or, Chen Greif, Tao Ju, Niloy J. Mitra, Ariel Shamir, Olga Sorkine-Hornung, Hao (Richard) Zhang](https://www.taylorfrancis.com/books/mono/10.1201/b18472/sampler-useful-computational-tools-applied-geometry-computer-graphics-image-processing-tao-ju-niloy-mitra-daniel-cohen-chen-greif-olga-sorkine)
    - [Linear Algebra for Everyone by Gilbert Strang](https://math.mit.edu/~gs/everyone/)
___

<!--- <img src="https://github.com/gasingh/minBoundingBox/blob/main/240426_minimumBoundingBox_simpleCapture.gif" style="border: #000000 6px outset; width="500";display: block; margin-left: auto; margin-right: auto;" title="BoundingBox2d-01" /> --->

<p align="center" width="100%">
<kbd><kbd>
<img src="https://github.com/gasingh/minBoundingBox/blob/main/240426_minimumBoundingBox_simpleCapture2.gif" width="500" />
</kbd></kbd> </br>
<b>GIF 1</b> </br> 2D bounding boxes: on shape point clouds
</p>


<p align="center" width="100%">
<kbd><kbd>
<img src="https://github.com/gasingh/minBoundingBox/blob/main/240426_minimumBoundingBox_simpleCapture3.gif"  width="500" />
</kbd></kbd> </br>
<b>GIF 2</b> </br> 2D bounding boxes: on point clouds
</p>

___
