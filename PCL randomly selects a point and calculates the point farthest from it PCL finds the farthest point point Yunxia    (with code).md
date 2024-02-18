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

