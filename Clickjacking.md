# What is clickjacking?

  This is attack which perform using iframe tag. It is a malicious technique of tricking a user into clicking on something different from what the user want.
  <html> <head> image </head>  <body> <img src="https://dpsvdv74uwwos.cloudfront.net/statics/img/ogimage/clickjacking-attacks.png" height=300px, width=300px></img></body></html>
  
# Steps:

1.First make simple html code with iframe tag.

2. To check clickjacking try this <iframe  src="http://magnus.jalatechnologies.com/"></iframe>.
  
3. Then visit html page we created.

4.In response it show "magnus.jalatechnologies.com refused to connect."

5.For bypassing that try <iframe src="http://magnus.jalatechnologies.com/ sandbox="allow-forms"> </iframe>.

6.It also not working.

# Security which website used:
 1. After studying the response of website in burpsuite.
 2. Understand that website using Content Security Policy (CSP) is a detection and prevention mechanism that provides    mitigation against attacks such as XSS and clickjacking. 
 3. Here website using  "X-Frame-Options: sameorigin".
