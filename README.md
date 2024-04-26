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
  - Solve the Covariance Matrix, and solve the linear equation system to obtain the **eigenValues**
  - Compute the **eigenVectors**.
  - The eigenvalues are the **principal components** of the 2D data. 
  - The extents of the dataset along the two principal components is derived by associatively sorting the Projections of the dataset on the respective PC vectors, and their respective projections (dot products).
  - Finally, some simple Rhinocommon gymnastics to compute a bounding box geometry from the obtained information above.
  - Done!

### References
  - __Videos__
    - [Principal Component Analysis- YouTube Playlist by Victor Lavrenko | 2014 ](https://www.youtube.com/playlist?list=PLBv09BD7ez_5_yapAg86Od6JeeypkS4YM)
    - [COVARIANCE AND VARIANCE - YouTube Playlist by Michel van Biezen | 2021](https://www.youtube.com/playlist?list=PLX2gX-ftPVXWHdoWSeshfEbRarb_LiX-e)
    - [What is the purpose of subtracting the mean from data when standardizing?](https://math.stackexchange.com/questions/317114/what-is-the-purpose-of-subtracting-the-mean-from-data-when-standardizing)
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
