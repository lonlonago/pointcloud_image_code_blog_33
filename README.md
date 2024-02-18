#  First, the principle of the algorithm 

##  1. Calculate the eigenvalue eigenvector 

   For the whole point cloud, the covariance matrix is constructed as: in the formula,; is the center point of all points in the point set. According to the formula, calculate the eigenvalues and eigenvectors of the covariance, where is the eigenvalue of, and; is the corresponding eigenvector. 

##  2. 3D point cloud projection 

    In the formula,; is the center point of all points in the point set; is the corresponding coordinate of the point after the projection. 

>  For the detailed calculation and derivation process, see: Principal Component Analysis PCA Algorithm: Why is the eigenvector matrix of the high-dimensional matrix multiplied by its covariance matrix after de-averaging "projection"? 

##  3. Data recovery 

   Enter the projected data, multiply it by the principal component, and add the mean to get the reconstruction and recovery data. That is: the inverse operation of the projection. 

##  4. Calculate the centroid 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574160361
  ```  
#  Core source code 

##  1. Eigenvalue eigenvector 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574160361
  ```  
##  2. 3D point cloud projection 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574160361
  ```  
##  3. Data recovery 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574160361
  ```  
#  III. Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574160361
  ```  
#  IV. Display of results 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574160361
  ```  
##  1. Primitive point cloud 

 ![avatar]( ec13344fce8a4c3692c77820c876457c.png) 

##  2. Projection point cloud 

 ![avatar]( 99463f0bdfda4fabb85e66bf3de1bd3c.png) 

##  3. Comparison of results 

 ![avatar]( 970c8a13715e41b4b377098362daeccb.png) 

>  White is the projected point cloud, and the origin of the local coordinate system obtained by PCA is (0, 0, 0), so there is a certain deviation between the two. 



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

##  1. Projection model 

##  2. Function analysis 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574191087
  ```  
 The model type used by setting the parameters given by the user, and the parameter Model is the model type. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574191087
  ```  
 Get the model type parameters given by the user. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574191087
  ```  
 Set a pointer to the model coefficients. Model is a pointer to the model coefficients. For different models, there are different coefficient objects. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574191087
  ```  
 Get a pointer to the model coefficients 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574191087
  ```  
 Sets whether to return all points or only the point cloud obtained after the projected inner points. The parameter val is set to true to return all points, and val is set to false to return only the projected inner points. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574191087
  ```  
 Gets a Boolean value that returns all points or just points within the projection. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574191087
  ```  
 Acquire the filtered point cloud output. 

##  3. Reference link 

>  [1] Module sample_consensus 

#  Code example 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574191087
  ```  
#  III. Display of results 

 ![avatar]( 20210207111039708.png) 

#  IV. Application examples 

>  1. Projection to plane, see: PCL point cloud projection to fit plane 2. Projection to sphere, see: PCL point cloud projection to sphere 



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

 ![avatar]( 58f07ae3b4dd4083999e42debca151ee.png) 

   As depicted in the figure, the test point cloud has 15,697 duplicate points.  

 If a point has more than one point within a certain distance threshold area, it is considered to have duplicate points. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574170849
  ```  
#  III. Display of results 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574170849
  ```  
 ![avatar]( b381a17121304a0f80a445b51e4c5ef0.png) 



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

##  1. Overview of the principle 

 ![avatar]( 02d4b3b8e2b4446894c713f8c39c86a7.png) 

   The filtering idea of the radius filter is very straightforward, that is, in the point cloud data, set each point to have at least enough close neighbors within a certain radius, and it will be deleted if it is not satisfied. For example, if you specify a radius d, and then specify that there are at least 1 neighbor within the radius, then only the yellow points in the image below will be deleted from the point cloud. If you specify at least 2 neighbors within the radius, then both the yellow and green points will be deleted from the point cloud.  

##  2. Implementation process 

##  3. Algorithm characteristics 

   The radius filter is more simple and crude than the statistical filter. The algorithm runs fast, and the points left by the sequential iteration must be the densest, but the radius of the sphere and the number of points in the sphere need to be manually specified. The radius filter is more suitable for removing single outliers, and can make a better reservation of the boundary. 

##  4. References 

>  [1] doc: Removing outliers using a StatisticalOutlierRemoval filter [2] PCL: pcl :: RadiusOutlierRemoval class realizes radius filtering [3] Chen Hongyi, Hu Xiaobin, Li Chongrui. Application of ground 3D laser scanning technology in deformation monitoring [J]. Surveying and Mapping Bulletin, 2014 (12): 74-77. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574134979
  ```  
#  III. Display of results 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574134979
  ```  
 ![avatar]( f17d8428ff784314959b019e93db4d7c.png) 

#  IV. Relevant links 

 [1] PCL 读取、保存点云 [2] PCL 代码运行时间计算方法汇总 [3] PCL 点云可视化汇总 



--------------------------------------------------------------------------------

##  First, the principle of the algorithm 

>  For the detailed specific principle of the algorithm, see: Faster Methods for Random Sampling

PCL PCL :: Random Sample class to achieve the algorithm, the implementation is relatively simple only need to set the number of fixed sampling points. The algorithm is also integrated in CloudCCompare software. CloudCompare software implementation operations are as follows: 

 ![avatar]( 20201230092648371.gif) 

##  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574218341
  ```  
##  III. Display of results 

 ![avatar]( 20201111171202700.png) 



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

##  1. Overview 

   Selecting a random point from the point cloud and then selecting the three farthest points from it to form a four-point base pair is an important step in the 4PCS registration algorithm. Therefore, selecting a point from the point cloud and calculating the farthest point from that point is an important step in realizing handwritten 4PCS and its improved algorithm. 

##  2. Main functions 

    PCL :: get Max Distance () point cloud data, given a point, find the point farthest from that point. This function has two overloading methods, the second one has one more indices than the first, mainly to select the point with the largest distance in the indices, rather than in the entire point cloud. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574269724
  ```  
   For the function analysis of random point selection, see: the usage of random functions rand () and srand () in C/C++. Its implementation process is: get the index of all points in the point cloud, then randomly select points in the index, and finally select points in the original point cloud according to the index. 

   For visual related code analysis, see: PCL Common Graphics Visualization Summary  

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574269724
  ```  
#  III. Display of results 

 ![avatar]( 0a695e1846944bf0ab74dc6f7135a377.png) 



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

#  I. Overview 

   Use the RANSAC algorithm to fit and split multiple lines, output the fitting parameters of each line to the console, and save the line point cloud to the local folder. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574187296
  ```  
#  III. Display of results 

##  1. Primitive point cloud 

 ![avatar]( 1f0327a606214e94b150a8178de359cd.png) 

##  2. Fitting results 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574187296
  ```  
##  3. Segmentation results 

 ![avatar]( 5d4d975b14a84e2283cda84adac633a4.png) 



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

##  1. Cylinder equation 

 ![avatar]( 20210530162828422.png) 

 The cylindrical equation can be expressed as follows: The following figure is a schematic diagram of a cylindrical space.  

    Among them, a point on the axis of the cylinder, the direction vector of the axis of the cylinder, and the radius of the cylinder, these seven parameters can determine a cylindrical equation. 

##  2. Model coefficients 

 Model coefficients are defined as: 

##  3. References 

>  Cylinder model segmentationpcl::SampleConsensusModelCylinder 

#  Code implementation 

 This tutorial illustrates how to run a sample consensus segmentation of a cylindrical model. To make the example more practical, apply the following to the input dataset (in order): 

>  Data points 1.5 meters away are filtered to estimate the surface normals for each point. A flat model (describing the table in the demo dataset) is segmented and saved to disk. A cylindrical model (describing the mug in the demo dataset) is segmented and saved to disk. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574180688
  ```  
#  III. Display of results 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574180688
  ```  
 ![avatar]( 8eec2e9e78354421af5e2c156d58e5c6.png) 

#  IV. Application cases 

 Acquire the cylindrical model coefficients and visualize the model fit results 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574180688
  ```  
#  V. Display of results 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574180688
  ```  
 ![avatar]( 0807242887d847aa9163a0b6c1460aed.png) 



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

##  1. Overview 

   The random sample consensus algorithm (RANSAC) is an iterative method for calculating the parameters of a mathematical model from a series of data containing divorced values. The RANSAC algorithm essentially consists of two steps, which are continuously looping: (1) randomly select the minimum number of elements that can form a mathematical model from the input data, and use these elements to calculate the parameters of the corresponding model. The selected number of these elements is the minimum number that can determine the parameters of the model. (2) Check which elements in all the data can conform to the model obtained in the first step. Elements that exceed the error threshold are considered outliers, and elements smaller than the error threshold are considered inliers. This process is repeated many times, and the model with the most points is selected to obtain the final result. 

##  2. Fitting the ball 

   The standard equation for a sphere, which represents the spherical center of the sphere, is that the radius is SampleConsensusModelSphere defines the RANSAC fitting segmentation model of the three-dimensional sphere. 

##  4. References 

>  [1]pcl ::  SampleConsensusModelSphere  

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574140811
  ```  
#  III. Display of results 

 ![avatar]( 36a8c95ba5eb702914f05bb95eece63b.png) 



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

##  1. Introduction to the algorithm 

   The RANSAC algorithm, proposed by Fischler and Bolles in 1981, is a method for iteratively and robustly estimating model parameters from data sets. The basic ideas of the algorithm are: continuously randomly select sample sets from the data set to seek model parameters that support more interior points; use the model remainder to test the obtained model parameters; through a certain number of iterations, when the consistency probability of the sampled sample set and the comprehensive understanding is the largest, the sampled sample set is regarded as the comprehensive understanding sample set, and the correctness of the parameter solution is supported by the sample remainder test. The data set contains correct data (inner point inliers) and abnormal data (outer point outliers). The essence of the calculation process of the algorithm is to assume and test: assume that the randomly sampled data are all interior points, use the randomly sampled data to calculate the model parameters; test the estimated model parameters through other points. The RANSAC algorithm requires to ensure that under a certain confidence probability, the minimum number of samples N of its basic subset and the probability of obtaining at least one benign sampling subset satisfy the relationship of equation (1). In the formula: the probability of interior points in the data set, that is, the minimum amount of data required to calculate the model parameters. The data obtained in practical applications often contain noisy data, which can interfere with the construction of the model. We call such noisy data points outliers, and those that play a positive role in model construction are called inliers. RANSAC first selects some points randomly, uses these points to obtain a model (for straight line fitting, this so-called model is a straight line model), and then uses this model to test the remaining points. If the tested data points are within the allowable range of errors, the data points will be judged as inlier, otherwise it will be judged as outlier. If the number of inliers reaches a certain threshold, it means that the selected data point set has reached an acceptable level. Otherwise, continue all the steps after the previous random selection of point sets, and repeat the process until the selected data point set has reached an acceptable level. At this time, the obtained model can be considered as the optimal model construction for the data points. 

##  2. Straight line fitting 

   The parameter setting of the RANSAC algorithm applied to the fitting of spatial straight lines is as follows: 1) Objective function. Objective function: that is, the process of maximizing the number of inner points under the model parameters in different iteration processes through the second iteration. The objective function of the RANSAC algorithm applied to the fitting of spatial straight lines is to obtain the parameter model containing the most inner points according to the distance threshold of the known spatial straight line. 2) Sampling subset size. In the iterative calculation process, the model parameters need to be calculated using a subset, and each sampling subset should be the minimum sampling set with the size of the data volume. Spatial straight line fitting requires at least 2 spatial points, so when the RANSAC algorithm is applied to the fitting of three-dimensional spatial straight lines, take. 3) Iteration termination condition. The number of iteration termination of RANSAC can be obtained by theoretical calculation. Under the condition of confidence level, there is at least one sample in the loop process, so that the points of the sampled subset are all interior points, thus ensuring that at least one sample can obtain the maximum value of the objective function in the iteration process. Therefore, from equation (1), the loop termination condition should satisfy the conditional expression (2).  

 ![avatar]( 31a31c45912749bf928d10edbc9ec22a.png) 

   In the formula: the confidence level is generally set to within the range of [95%, 99%]; in general, as the probability of interior points in the data set, it belongs to the unknown parameter. Therefore, the proportion of interior points under the worst condition can be taken, and then the proportion of the current maximum interior points can be continuously updated as the number of iterations increases. The confidence level is generally set to 99%. In summary, the process of using the RANSAC algorithm to solve the geometric parameters of space straight lines is shown in the figure below.  

##  3. Model coefficients 

   The linear equation has three representations: general, point-to-point, and parametric. PCL uniformly adopts the point-to-point equation, and the point-to-point equation of the straight line is: where, direction vector, known points. Used to determine the line model, the six coefficients of the line are given by the points on the line and the direction of the line: [point_on_line point_on_line point_on_line line_direction x line_direction y line_direction] 

##  4. References 

>  [1] pcl :: SampleConsensusModelLine [2] Bao Jianqiang, Zhang Xianzhou, Li Yuan, Xiao Yuanmiao, Chen Xiao, Luo Chao. Application analysis of various spatial straight line fitting methods [J]. Science of Surveying and Mapping, 2020, 45 (05): 132-139 + 151. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574132799
  ```  
#  III. Display of results 

>  Red is the point cloud located within the threshold range of the fitted line 

 ![avatar]( 20210307170711936.png) 



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

##  1. Overview 

   The principle of the least squares method is to determine the best function match for a set of data based on minimizing the sum of squares of errors. The principle of its specific fitting circle is as follows. Assuming that the circle equation is known: Equation (1) can be written as: Rewrite equation (2) into the form of the right equal to 0, and convert the formula: Therefore, the values of the three parameters of the above binary quadratic equation can be determined, so as to calculate the radius of the fitting circle and give the coordinates of the center of the circle. The distance from the point in the sample set to the center of the circle: In order to obtain the most accurate fitting of the actual parameters of the circle, use the distance from the sample point to the center of the circle to square the difference with the radius, and find the value that minimizes the sum of squares, that is, the final solution, so as to determine the parameters of the circle and draw the circle. 

##  2. Fit the plane 2D circle 

   In the standard equation of a circle, there are three parameters, that is, the coordinates of the center of the circle are, as long as it is obtained, the equation of the circle is determined at this time, so to determine the equation of the circle, three independent conditions are required, among which the coordinates of the center of the circle are the positioning conditions of the circle, and the radius is the shape condition of the circle. SampleConsensusModelCircle2D defines the RANSAC fitting segmentation model of a two-dimensional circle on the X-Y plane. 

##  3. Model coefficients 

 The two-dimensional circle model coefficients are defined as: 

##  4. References 

>  [1]pcl :SampleConsensusModelCircle2D 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574149334
  ```  
#  III. Display of results 

 ![avatar]( 98ddf14f782340309823e89af0694dbd.png) 



--------------------------------------------------------------------------------

#  I. Overview 

   The core principle of using PCL segmentation to extract multiple cylinders is still RANSAC fitting cylinders. Here is just a simple modification, which is suitable for extracting multiple cylinders. For the specific implementation principle, see: PCL RANSAC fitting segmentation cylinder model. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574198690
  ```  
#  III. Display of results 

##  1. The original data source 

 ![avatar]( ff0fba96e31c42a6a0f3bad6d21415dc.png) 

##  2. Extract the results 

 ![avatar]( eb3d57dfa48d404fb0c7bc8cb2830cbd.png) 



--------------------------------------------------------------------------------

#  I. Overview 

   The core principle of using PCL segmentation to extract multiple spheres is still RANSAC fitting spherical surfaces. Here is just a simple modification, which is suitable for extracting multiple spheres. For the specific implementation principle, see: PCL RANSAC fitting spatial 3D spheres. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574130629
  ```  
#  III. Display of results 

##  1. The original data source 

 ![avatar]( 71dc335271ec4f8eb14bae8fec098312.png) 

##  2. Extract the results 

 ![avatar]( e995e07f02c6483881c9792adc3d0435.png) 



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

   The core principle of the algorithm is still the RANSAC fitting plane. For the specific theory, please refer to: PCL uses RANSAC to fit the plane. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574161413
  ```  
#  III. Display of results 

 ![avatar]( 20201110204323808.png) 

#  Attachment: Classification and preservation of segmentation results 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574161413
  ```  


--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

>  Fit the plane first, then calculate the distance from the point to the plane, set the threshold, and delete the point that the distance from the point to the plane is outside the threshold range. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957415933
  ```  
#  III. Display of results 

 ![avatar]( 20201207215636439.png) 



--------------------------------------------------------------------------------

#  First, PCLPointCloud2 

    PCL :: PCL PointCloud2 is a ROS message type that replaces the old sensors_msgs :: PointCloud2. The pcd forms that can be saved are: ASCII, Binary, and BinaryCompressed. 

##  1、PCDReader/PCDWriter 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574264737
  ```  
##  2、I 

    Only iOS read operations and no iOS save operations 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574264737
  ```  
#  PointCloud 

##  1、PCDReader/PCDWriter 

 PCD formats that can be saved are ASCII, Binary, and BinaryCompressed. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574264737
  ```  
##  2、I 

 PCD formats that can be saved are ASCII, Binary, and BinaryCompressed. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574264737
  ```  
#  Third, the transformation of PCLPointCloud2 and PointCloud 

##  1. Main function 

 PCL 1.11.1 provides the following functions for converting from one type to another. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574264737
  ```  
##  2. Code example 

 Convert PCLPointCloud2 to PointCloud 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574264737
  ```  
 Convert PointCloud to PCLPointCloud2 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574264737
  ```  
#  IV. Copy a point 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574264737
  ```  
 Application example: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574264737
  ```  
#  Understanding of Bin and Ascii 

 Computer files are basically divided into two types: binary files and ASCII (also known as plain text files). 

    Text files Ascii are characters that can be seen, and binary files Bin are invisible characters, such as pictures. Binary files: Files containing data or program instructions written in ASCII and extended ASCII characters. Computer files are basically divided into two types: binary files and ASCII (also known as plain text files), graphic files and word processing programs are all binary files. These files contain special formatting and computer code. ASCII is a simple text file that can be read with any word processing program. Since it is difficult to strictly distinguish between the concepts of text files and binary files, we can simply assume that if a file is dedicated to storing data for text characters and does not contain any other data other than characters, we call it a text file, and files other than that are binary files. 

    For example, if an article is written in Chinese, you can understand it at a glance, and you can define it as text mode. Correspondingly, the same content, you write in English or Oracle, you can define it as binary mode. Xinhua Dictionary can be defined as "Notepad" for the time being, and it is OK to read this article with the corresponding. If you use Xinhua Dictionary to try to read articles written in English, you can call it garbled. 2. The two opening methods are slightly different, that is, the newline code 0D0A indicates that the text thinks it is a character, and the binary recognition is 2 characters. You can understand that the text file is a kind of binary file. There is no such thing as text in the world, it is made up of too much food. Whether it is a text file, or the encoding of unicode and ascii, these are the ways in which the file is interpreted. For example, if there is a word "apple" in the file, then if you are asked to open it in Chinese mode, then "apple" will be displayed, but for the content of the file, it is still apple, and it has not changed, but the way of interpretation has changed. Binary is read and written in bytes without any additional actions. The text mode handles carriage returns and line breaks. Computer storage is physically binary, so the difference between a text file and a binary file is not physical, but logical. The two are only different at the encoding level. In simple terms, text files are files based on character encoding. Common encodings include ASCII encoding, UNICODE encoding, and so on. Binary files are files based on value encoding. You can specify what a certain value means according to the specific application (such a process can be regarded as custom encoding). From the above, it can be seen that text files are basically fixed-length encoded (there are also non-fixed-length encodings such as UTF-8). Based on characters, each character is fixed in the specific encoding. ASCII codes are 8-bit encodings, and UNICODE generally accounts for 16 bits. And binary files can be regarded as variable-length encoding, because it is value encoding. It is completely up to you to decide how many bits represent a value. 



--------------------------------------------------------------------------------

#  Overview of the process 

    Read the coordinates of the point cloud from a TXT file and visualize it using PCL. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574265299
  ```  
#  III. Display of results 

 ![avatar]( 2b2dbfd7891340bd85ea19fda3cf9708.png) 



--------------------------------------------------------------------------------

