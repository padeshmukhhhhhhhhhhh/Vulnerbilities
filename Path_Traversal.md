# What is directory traversal?
Directory traversal (also known as file path traversal) is a web security vulnerability that allows an attacker to read arbitrary files on the server that is running an application. This might include application code and data, credentials for back-end systems, and sensitive operating system files. In some cases, an attacker might be able to write to arbitrary files on the server, allowing them to modify application data or behavior, and ultimately take full control of the server.
<html>
  <head> </head>
  <body> <img src= "https://www.cloudprotector.com/wp-content/uploads/2021/06/query-string.png"></img>
  </body>
  </html>
  
# Steps
   1)  The sequence ../ is valid within a file path.It is used go back to previous directory.
   2)  Visit following link
     https://magnus.jalatechnologies.com/Employee/Search
   3) For path traversal attack make changes and add internal file name
       https://magnus.jalatechnologies.com/Employee/Search/../../etc/passwd/ 
   4) Some site block this technique, So sometimes we used url encoding.
   5) If an application requires that the user-supplied filename must end with an expected file extension, such as .png, then it might be possible to use a null byte to effectively terminate the file path before the required extension. For example:

        ../../etc/passwd%00.png
        
 # Prevention
   1. The application should validate the user input before processing it. Ideally, the validation should compare against a whitelist of permitted values. If that isn't possible for the required functionality,
     then the validation should verify that the input contains only permitted content, such as purely alphanumeric characters.
   

