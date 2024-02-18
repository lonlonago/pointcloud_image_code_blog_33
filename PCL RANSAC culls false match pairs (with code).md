#  First, the principle of the algorithm 

##  1. Overview of the method 

   In PCL, the matching points between the source point cloud and the target point cloud are added to the Correspondences, and the inner points are filtered by random sampling algorithm (ransac). 

>  1, about RANSAC can refer to: RANSAC algorithm introduction 2, pcl :: registration :: CorrespondenceRejectorSampleConsensus class based on random sampling consistency to determine the inner point (remove outliers), to achieve a false correspondence removal algorithm, where the outliers represent the wrong correspondence, the inner point represents the correct correspondence to be retained. 

##  2. Implementation process 

   The steps of RANSAC algorithm to remove erroneous corresponding point pairs are as follows: (1) randomly select three corresponding point pairs in the corresponding point set and solve the rigid body transformation matrix. (2) Calculate the distance error of the remaining point pairs in the corresponding point set under this rigid body transformation matrix. If the distance error of one point pair is less than the set threshold error, the point is the inner point of the sample, otherwise it is the outer point of the sample, and count the former number. (3) Repeat the above steps until the upper limit of the number of iterations is reached. The number of points in the sample under different rigid body transformation models is counted, and the one with the largest number of points in the sample is used as the best mathematical model. All the points in the sample are retained, and the outer points of the sample are excluded. The most correct point pair of the corresponding point pair that excludes the outer point is used for the next point cloud registration operation. Due to the improvement of the ratio of the correct point pair in the corresponding point set optimized by the RANSAC algorithm, the obtained rigid body transformation matrix is more accurate, and the error of point cloud registration is effectively reduced. When using the RANSAC algorithm, attention should be paid to the setting of the threshold error and the number of iterations. Reasonable setting is helpful to improve the rejection effect of the wrong point pair. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574189043
  ```  
#  III. Display of results 

 ![avatar]( 20200702162338919.png) 

