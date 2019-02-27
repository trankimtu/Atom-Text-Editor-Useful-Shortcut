# PHP
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


- - - - - - - -


<!-- 
================================================================
=========================== Constant ===========================
================================================================
-->

<details>
  <summary>Constant</summary>
  
  ```
  define(name, value, case-insensitive) 
  ```  
  - name: Specifies the name of the constant
  - value: Specifies the value of the constant
  - Case-insensitive: Specifies whether the constant name should be case-insensitive. Default is false
  - Constants are automatically global and can be used across the entire script.
</details>

- - - -

<!-- 
================================================================
========================= PHP Data type ========================
================================================================
-->

<details>
  <summary>PHP Data type</summary>
  
  - String
  - Integer
  - Float (floating point numbers - also called double)
  - Boolean
  - Array
  - Object
  - NULL
  - Resource

</details>

- - - -

<!-- 
================================================================
======================== Echo and Print ========================
================================================================
-->

<details>
  <summary>Echo and Print</summary>
  
  - Echo and Print use to output data to the screen
  - Echo
    - Has no return value
    - Can take multiple parameters
    - Faster than print
    
    ```
    <?php
      $a = 5;
      echo "Double quote : a = \$a = $a <br>";          //  Double quote : a = $a = 5 
      echo 'Single quote : a = $a = $a <br>';           //  Single quote : a = $a = $a  <-- print out character, does not regconize variable
      echo "Double quote .\$a: a = $a = ".$a."<br>";    //  Double quote .$a: a = 5 = 5
      echo 'Single quote .$a: a = $a = '.$a . '<br>';   //  Single quote .$a: a = $a = 5
    ?>
    ```
  - Print
    - Has a return value of 1 so it can be used in expressions
    - Can take one argument
    
    ```
    <?php
      $a = 5;
      print "Double quote : a = \$a = $a <br>";         //  Double quote : a = $a = 5 
      print 'Single quote : a = $a = $a <br>';          //  Single quote : a = $a = $a 
      print "Double quote .{$a}: a = $a = ".$a."<br>";  //  Double quote .5: a = 5 = 5
      print 'Single quote .$a: a = $a = '.$a . '<br>';  //  Single quote .$a: a = $a = 5
    ?>
    ```
  
</details>

- - - -

<!-- 
================================================================
=========================== Operator ===========================
================================================================
-->

<details>
  <summary>Operator</summary>
  
Operator      |               | Function        |Comparison    | 
------------- | ------------- | -------------   | -------------|
"+"           | +=            | Add             | != , <> , !==
"-"           | -=            | Subtract        | == , ===
"*"           | *=            | Multiple        | > , >= , >==
**            | **=           | Power           | < , <= , <==
/             | /=            | Divide          | max "=": check type
%             | %=            | Mod             
.             | .=            | Concatenate string  |
  
</details>

- - - -

<!-- 
================================================================
======================= String Handling ========================
================================================================
-->

<details>
 <summary>String Handling</summary>
   https://www.w3schools.com/php/php_ref_string.asp
 <details>
  <summary>index access</summary>
   Return character at the index of the string
          
    echo "Hello"[1];  //  e
    
 </details>
 
 <details>
  <summary>strlen </summary>
  return number of characters in the string
    
    echo strlen("1 22 333");     // 8
    
 </details>
  
 <details>
  <summary>str_word_count </summary>
  return number of word of the string
  
    echo str_word_count("0 1a b2 3 444 name");  // 3 
  "0", "3", and "444" are contain all number, so they're not be counted
 </details>
  
 <details>
  <summary>strrev </summary>
  Return a string reverse of the original string
     
    echo strrev ("Hello");  // olleH 
 </details>
  
 <details>
  <summary>strpos</summary>
  Return 1st index of substring inside a string
        
    echo strpos("Hello Fullerton", "lo");  // 3
 </details>
  
 <details>
  <summary>str_replace</summary>
  Replace original substring by new substring in a string
    
    echo str_replace("Anaheim", "Fullerton", "Welcome to Anaheim");   // Welcome to Fullerton
 </details>
  
 <details>
  <summary>substr</summary>
 
    echo substr("0123456789", 3)       // 3456789  Start from 3 to end
    echo substr("0123456789", 1, 4)    // 1234     Start from 1 to 4
 </details>
  
 <details>
  <summary>strcmp</summary>
    ASCII compare, therefore it's base on case sensitive
    Return int $value
    <li>$value < 0 mean $var 1 < $var2</li>
    <li>$value > 0 mean $var 1 > $var2</li>
    <li>$value = 0 mean $var 1 = $var2</li>

    var1 = zello
    var2 = hello
    strcmp($ var1, $ var2) = 1

    var1 = hello
    var2 = hello
    strcmp($ var1, $ var2) = 0

    var1 = Hello
    var2 = hello
    strcmp($ var1, $ var2) = -1
    
    $var1 is not equal to $var2 in a case sensitive string comparison
    var1 > var2 
 </details>
 
 <details>
  <summary>implode</summary>
  
    implode ( $glueString , $arrayVariable )
  <li>Passing a simple array</li>
  <li>Return a string with all element separate by $glueString.</li>
  
    $arrayV = array('lastname', 'email', 'phone');
    
    $comma_separated = implode(",", $arrayV);
    echo $comma_separated."<br>";               // lastname,email,phone
    
  <li>No $glueString mean $glueString = ""</li>
  
    $nonseparated = implode($arrayV);
    echo $nonseparated."<br>";                  // lastnameemailphone
 </details>
 
 <details>
  <summary>a</summary>
 </details>
 
 <details>
  <summary>a</summary>
 </details>
 
 <details>
  <summary>a</summary>
 </details>
 
 <details>
  <summary>a</summary>
 </details>
 
 <details>
  <summary>a</summary>
 </details>
 
 
</details>

- - - -

<!-- 
================================================================
=========================== Loop ===========================
================================================================
-->

<details>
  <summary>Loop</summary>
</details>


- - - -

<!-- 
================================================================
=========================== Array ===========================
================================================================
-->

<details>
  <summary>Array</summary>
</details>

- - - -

<!-- 
================================================================
=========================== sortArray() ===========================
================================================================
-->

<details>
  <summary>Sort Function for array</summary>
  
 ```sort() ``` - sort arrays in ascending order
 
 ```rsort()``` - sort arrays in descending order
 
 ```asort()``` - sort associative arrays in ascending order, according to the value
 
 ```ksort()``` - sort associative arrays in ascending order, according to the key
 
</details>

- - - -

<!-- 
================================================================
=========================== Constant ===========================
================================================================
-->

<details>
  <summary></summary>
</details>

- - - -

<!-- 
================================================================
=========================== Constant ===========================
================================================================
-->

<details>
  <summary></summary>
</details>

- - - -




