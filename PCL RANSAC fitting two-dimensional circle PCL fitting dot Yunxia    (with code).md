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

