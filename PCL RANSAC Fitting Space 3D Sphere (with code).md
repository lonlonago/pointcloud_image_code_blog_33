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

