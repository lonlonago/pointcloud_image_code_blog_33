#  First, the principle of the algorithm 

##  1. Algorithm overview 

   Morphological filtering adopts the operation process of corrosion first and then expansion, which can filter out small ground objects in the specified size window and retain large ground objects. The progressive morphological filtering algorithm proposed by Zhang on this basis can effectively filter out buildings, vegetation, vehicles, pedestrians and traffic accessories in the scene, and retain road pavement and curbs. 

##  2. Parameter calculation 

   The so-called progressive method is to filter out non-ground points through the iterative operation process of continuously increasing the window, but this will cause the top of some terrain undulations to be erroneously filtered, so that the filter generates a surface lower than the real ground. In order to prevent some ground points from being erroneously filtered, Zhang introduced the height difference threshold to judge the point cloud, and reserved the points smaller than the height difference threshold, which are the grid size, the terrain slope parameter, the window size of the second filter, the initial height difference threshold, the maximum height difference threshold, and the height difference threshold under the current filtering window. Among them, the terrain slope parameter, the initial height difference threshold, and the maximum height difference threshold all need to be preset by the user. 

##  3. Efficiency analysis 

   The height difference threshold is a key factor affecting the final result of the progressive morphological filtering algorithm, and the terrain slope value is a key parameter for calculating the height difference threshold. The algorithm needs to preset the terrain slope parameters in advance, and the algorithm needs to operate on all the points contained in the current window when starting the operation. The running time of the algorithm is too long to affect the filtering efficiency in the iterative process of the loop. 

##  4. References 

>  1. PCL :: ProgressiveMorphologicalFilter class realizes morphological filtering to remove ground points. 2. Link to the original paper: A Progressive Morphological Filter for Removing Nonground Measurements From Airborne LIDAR Data 3. About the theory of morphological filtering, this blog and this blog talk about it in detail. 4. Progressive Morphological Filter Algorithm 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574222629
  ```  
#  III. Display of results 

 The running time of the algorithm is 1.83 seconds. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574222629
  ```  
 ![avatar]( f8dd78599d644a1ab10dfd915d1c621e.png) 

>  Red is the ground point, and non-ground points are rendered in elevation. 

