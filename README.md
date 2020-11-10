# RubiksCube

<p align="center">
 <img src="Cube3x3.png" width="400" height="400">
</p>

## Sticker representation

<ul>
 <li> Each face is represented by a length [5, 3] array: [v1, v2, v3, v4, v1] </li>
 <li> Each sticker is represented by a length [9, 3] array: [v1a, v1b, v2a, v2b, v3a, v3b, v4a, v4b, v1a] </li>
 <li> In both cases, the first point is repeated to close the polygon. Each face also has a centroid, with the face number appended at the end in order to sort correctly using lexsort. </li>
 <li> The centroid is equal to sum_i[vi]. </li>
 <li> Colors are accounted for using color indices and a look-up table. </li>
 <li> With all faces in an NxNxN cube, then, we have three arrays: </li>
  <ul>
   <li> centroids.shape = (6 * N * N, 4) </li>
   <li> faces.shape = (6 * N * N, 5, 3) </li>
   <li> stickers.shape = (6 * N * N, 9, 3) </li>
   <li> colors.shape = (6 * N * N,) </li>
 </ul>
 <li> The canonical order is found by doing ind = np.lexsort(centroids.T) </li>
 <li> After any rotation, this can be used to quickly restore the cube to canonical position. </li>
</ul>
