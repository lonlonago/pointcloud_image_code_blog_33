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

