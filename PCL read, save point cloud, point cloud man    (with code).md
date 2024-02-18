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

