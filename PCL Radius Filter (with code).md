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

