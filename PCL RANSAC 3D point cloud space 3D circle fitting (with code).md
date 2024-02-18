#  First, the principle of the algorithm 

##  1. Fit a 3D circle 

   When a sphere intersects a plane, its intersection line is a circle. Conversely, any circle in space can be expressed as the intersection line of a sphere and a plane. Therefore, the Cartesian coordinate equation of the space circle is: pcl :: SampleConsensusModelCircle3D defines the RANSAC fitting segmentation model of the three-dimensional circle. 

##  2. Specific steps 

   1) Initialize the number of cycles and the local point set. 2) 3 points are randomly selected from the boundary point set, and the parameters of the circle are solved through these 3 points, that is, the center and radius of the circle. 3) Calculate the distance from each boundary point to the center of the circle obtained in step 2). If, the points are included in the local point set; otherwise, it is regarded as an outsider point. 4) Calculate the number of internal points on the circle, and record it as, if it is greater than the threshold, it is considered that the estimate is successfully transferred to step 5); otherwise, it is transferred to step 6). 5) Recalculate the parameter model of the circle with the least squares method for all points in the point set, and get the final result. 6), if, then end; otherwise, turn to 2). 

##  3. Model coefficients 

 The three-dimensional circle model coefficients are defined as: 

##  4. References 

>  [1] Luo Zhiguo. Parametric equation of space circle and its application [J]. Journal of Natural Sciences of Hunan Normal University, 2012, 35 (06): 24-26. [2] pcl :: SampleConsensusModelCircle3D 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574131118
  ```  
#  III. Display of results 

 ![avatar]( 3e879b71e7c274092fc66c430aa2da40.png) 

