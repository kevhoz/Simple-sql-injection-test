<div id="header" align="center">
  <img src="https://media.giphy.com/media/M9gbBd9nbDrOTu1Mqx/giphy.gif" width="100"/>
</div>
<div id="badges" align="center">
  <a href="https://www.linkedin.com/in/kevin-christianto/">
    <img src="https://img.shields.io/badge/LinkedIn-blue?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn Badge"/>
  </a>
</div>
<div id="github" align="center">
    <img src="https://komarev.com/ghpvc/?username=kevhoz&style=flat-square&color=blue" alt=""/>
</div>
<div id="body-header" align="center">
<h1>
  Simple SQL Injection Testing
</h1>
</div>
### :hammer_and_wrench: Languages and Tools:
<div>
  <img src="https://github.com/devicons/devicon/blob/master/icons/php/php-original.svg" title="PHP"  alt="PHP" width="40" height="40"/>&nbsp;
</div>

### :woman_technologist: This repository cover:

1. Prepare The Environment.
2. Simple Case of SQL Injection Testing

<div id="prepare-environment">
<h2>
  Prepare The Environment
</h2>

What we need is:

PHP & MYSQL
  - You can install PHP & MYSQL from Xampp (apachefriends.org)
  - We need that 2 to be active for this testing

Get Development Folder Ready:
- Create folder "sql-injection" inside your root folder for web hosting (if xampp, then htdocs)
- Go inside the folder and create 2 file ("index.php" and "secure_login.php"), like this structure:
```
-sql-injection
--index.php
--secure_login.php
```
- Open "index.php" and write this code:

  ![image](https://github.com/user-attachments/assets/3cd5de32-e76b-4ebf-9b75-3b1e16f55740)

- Open "secure_login.php" and write this code:

  ![image](https://github.com/user-attachments/assets/15276732-66c0-4a96-931a-37a5fd00d0ab)

- Next, open PhpMyAdmin to create database, here is the step:
  1. Create database "testdb"
  2. Create table "users"
  3. Create field:
     - id INT AUTO_INCREMENT PRIMARY KEY
     - username VARCHAR(50) NOT NULL
     - password VARCHAR(50) NOT NULL
  4. Then, input data into table with username: "admin" and password: "admin123"
- Or, you can write this code in SQL script:

  ![image](https://github.com/user-attachments/assets/0ff011b8-0f9c-48a8-9617-b95f47047d15)

</div>

<div id="sql-injection">
<h2>
  Use case admin login: SQL Injection
</h2>

- Lets play the SQL Injection case:

- Not safe code:
- Open your php code on: "localhost/sql-injection", it will shown like this:

![image](https://github.com/user-attachments/assets/20241e6a-9039-409c-8868-6c64d1d2cae8)

- Test for login success:
  1. Input "admin" into field username
  2. Input "admin123" into field password
  3. click submit!
  4. it will shown login success

![image](https://github.com/user-attachments/assets/d23c8227-1c19-4bad-a08d-75627fe9c4b1)

- Test for login failed:
  1. Input any value to field username and password
  2. click submit!
  3. it will showrn login failed

![image](https://github.com/user-attachments/assets/3c377cf8-9167-4302-86a6-5c1d6387294a)

- Test for SQL Injection:
  1. Input this value into field username:
  ```
  admin' OR '1'='1
  ```
  2. Let field password empty
  3. click submit!
  4. see the result

- Test the SQL Injection into the secure_login (localhost/sql-injection/secure_login.php)
  1. Input this value into field username:
  ```
  admin' OR '1'='1
  ```
  2. Let field password empty
  3. click submit!
  4. see the result

- Compare it, and why it secure.
- SQL Injection case, Done

</div>
