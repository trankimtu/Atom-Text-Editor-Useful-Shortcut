# OS
<!-- 
================================================================
============================ Set up ============================ 
================================================================
-->
<details>
  <summary>Set up </summary>
  <ul>
    <li> <a href="http://php.net/downloads.php">Download PHP</a> at - http://php.net/downloads.php <br></li>
    <li> <a href="https://www.apachelounge.com/download/">Download apache</a> at - https://www.apachelounge.com/download/ <br></li>
    <li> <a href="https://www.python.org/downloads/">Download python</a> at - https://www.python.org/downloads/ <br></li>
    <li> <a href="https://www.mysql.com/downloads/">Download mySQL</a> at - https://www.mysql.com/downloads/ <br></li>
    <li>Change file</li>
  </ul>
   
</details>

- - - -

<!-- 
================================================================
=========================== Variable =========================== 
================================================================
-->

<details>
  <summary>Variable</summary>
  
  ```
  $x = 5;
  ```
  - Start with $
  - Name:
    - Must start with a leter or underscore
    - Cannot start with number
    - Only contain A-z, 0-9, and _
    - Case sensitive
   
  - Scope:
    - Local
      - Declair inside a function
      - Work only in the function
      
      ```
      function test() {
        $x = 15;
        echo "x = $x";
      }
      ```
      
      - Static: 
        - Value of variable won't be delete when function call done
      
        ```
        function myTest() {

          static $x = 0;
          echo $x;
          $x++;
        }

        myTest(); // result 0
        myTest(); // result 1
        myTest(); // result 2
        ```
      
    - Global
      - Declair outside any function
      - Work anywhere in php scope
     
       ```
       <?php
          $x = 5; // global scope

          function myTest() {
              // using x inside this function will generate an error
              echo "<p>Variable x inside function is: $x</p>";
          } 
          myTest();

          echo "<p>Variable x outside function is: $x</p>";
       ?>
       ```


    - Supper Global
      - https://www.w3schools.com/php/php_superglobals.asp
      - $GLOBALS: access global variables from anywhere in the PHP script (also from within functions or methods).
      - $_SERVER: holds information about headers, paths, and script locations
      - $_REQUEST: collect data after submitting an HTML form
      - $_POST: collect form data after submitting an HTML form with method="post". Also widely used to pass variables</li>
      - $_GET: collect form data after submitting an HTML form with method="get". Also collect data sent in the URL</li>
      - $_FILES
      - $_ENV
      - $_COOKIE
      - $_SESSION
</details>
