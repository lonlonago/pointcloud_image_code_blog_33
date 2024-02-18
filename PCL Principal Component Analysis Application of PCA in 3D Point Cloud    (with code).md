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

