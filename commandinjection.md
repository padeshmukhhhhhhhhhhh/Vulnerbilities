# what is command injection
   OS command injection (also known as shell injection) is a web security vulnerability that allows an attacker to execute arbitrary operating system (OS) commands on the server that is running an application, and typically fully compromise the application and all its data
   <html>
   <head> </head>
     <body> 
       <img src="https://knowledge-base.secureflag.com/assets/images/vuln/code_injection/os_command_injection_vulnerability/kb_0.png"></img>
      </body>
      </html>
      
  # Steps
   1. First visit   https://magnus.jalatechnologies.com/Employee/Search this page 
   2. Then click on delete, and intercept request in burpsuite.
   3. Add this  ||whoami in id parameter.
   4. Nothing is happend,Then add ||ping+-c+10+127.0.0.1|| in id parameter, If response is delay then there is blind command injection.
   5.But not working, Then add ||whoami>/var/www/html/Content/img/output.txt. in id parameter value.
   6 Then visit https://magnus.jalatechnologies.com/Content/img/user-profile.png and change the userprofile image with output.txt. and access it.
   7. When accessing the page it give internal server error, it means either file successfully created andserver block the user to access output.txt. or file does'nt created.
   
 # Sreenshots
   ![Screenshot (3)](https://user-images.githubusercontent.com/103956597/202894768-1a3db629-007a-409c-b498-3343f2d198e6.png)
   
   ![Screenshot (4)](https://user-images.githubusercontent.com/103956597/202894785-6d2b1c75-4160-4b5b-bf60-f2808687601d.png)
    
 # Prevention
  By far the most effective way to prevent OS command injection vulnerabilities is to never call out to OS commands from application-layer code. In virtually every case, there are alternate ways of implementing the required functionality using safer platform APIs.

If it is considered unavoidable to call out to OS commands with user-supplied input, then strong input validation must be performed. Some examples of effective validation include:

Validating against a whitelist of permitted values.
Validating that the input is a number.
Validating that the input contains only alphanumeric characters, no other syntax or whitespace.

      
