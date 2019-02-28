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
  
    implode ( $separateString , $variableArray )
  <li>Passing a simple array</li>
  <li>Return a string which form by using $separateString bond all elements in the array together.</li>
  
    $variableArray = array('lastname', 'email', 'phone');
    
    $comma_separated = implode(",", $variableArray);
    echo $comma_separated."<br>";               // lastname,email,phone
    
  <li>No $separateString mean $separateString = ""</li>
  
    $non_separated = implode($variableArray);
    echo $non_separated."<br>";                  // lastnameemailphone
 </details>
 
 <details>
  <summary>explode</summary>
  
    explode($separateString, $variableArray)
  At $separateString Split original string to many strings 
  
    $pizza  = "piece1 piece2 piece3 piece4 piece5 piece6";
    $pieces = explode(" ", $pizza);
    echo $pieces[0]."<br>"; // piece1
    echo $pieces[1]."<br>"; // piece2
    echo $pieces[2]."<br>"; // piece2
    echo $pieces[3]."<br>"; // piece2
    echo $pieces[4]."<br>"; // piece2

    // Example 2
    $data = "foo:*:1023:1000::/home/foo:/bin/sh";
    list($user, $pass, $uid, $gid, $gecos, $home, $shell) = explode(":", $data);
    
    echo $user."<br>"; // foo
    echo $pass."<br>"; // *
    echo $uid."<br>";  // 1023  
    echo $gid."<br>";  //1000
    echo $gecos."<br>";//
    echo $home."<br>"; // /home/foo
    echo $shell."<br>";// /bin/sh
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
  <details>
  <summary>Simple</summary>
  
   ```count($arrayA):``` Array length
   
    $aboutMe = array("Mike J", 20, "USA", "CSUF CA U.S"); <br>
    echo $aboutMe['0'];   // Mike J
    echo $aboutMe[2]; // USA <br>
  </details>

<details>
  <summary>Associative</summary>
  
    $arrayVariable = array("key1"=> "value1", "key2"=>num2, "key3"=>"value3");
    
    echo $arrayVariable['key1'];  //  value1
    
</details>
<details>
  <summary>Multidimension</summary>
  Nested Array
  
  Nested Array 1 - Array with every element is an array
  
    <?php
      $employees = array (
        array (
          "name" => "Mickey Mouse",
          "title" => "Master of Ceremonies",
          "salary" => 1000000.00
        ),
        array (
          "name" => "Donald Duck",
          "title" => "Court Jester",
          "salary" => 1000.00
        ),

        array (
          "name" => "Minnie Mouse",
          "title" => "Executive Mouse",
          "salary" => 2000000.00
        )
      );
      echo $employees[0]["name"]."<br>";
      echo $employees[1]["title"]."<br>";
      echo $employees[2]["salary"]."<br>";
      // echo ($employees[0])["name"].<"br">;
      print_r($employees);

      echo'<pre>';
      print_r($employees[0]);
      echo "</pre>";

      echo '<pre>';
      print_r($employees);
      echo '</pre>';
    ?>
  Nested Array 2 - Array with the key has value is an array
  
    <?php
      $user = array(
        "info" => array(
          "name"            => "Brett",
          "age"             => 59,
          "location"        => "Corona",
          "educationLevel"  => "MSIS"
        ),
        "hobbies"           => array(
          "racquetball",
          "git-fiddle",
          "watching NCAA Div 1 football"
        )
      );

      echo "my name is " . $user["info"]["name"] . "<br>\n";
      echo "I am " . $user["info"]["age"] . " years young<br>\n";
      echo "I live in " . $user["info"]["location"] . "<br>\n";
      echo "My highest education level is " . $user["info"]["educationLevel"] . "<br>\n";

      echo "I enjoy " . $user["hobbies"][0] . ", " . $user["hobbies"][1] . "<br>\n";
    ?>
</details>
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
  <summary>Object Oriented</summary>


    class user {
        private $uname="userName", $upass="userPass";
        private $id=0, $name="name", $email="email@email.com", $phone="(000) 000-0000", $dob="00000000";

        public function getId()     {return $this->id;}
        public function getName()   {return $this->name;}
        public function getEmail()  {return $this->email;}
        public function getPhone()  {return $this->phone;}
        public function getDob()    {return $this->dob;}
        
        public function setId($idSet)       { $this->id     = $idSet;}
        public function setName($nameSet)   { $this->name   = $nameSet;}
        public function setEmail($emailSet) { $this->email  = $emailSet;}
        public function setPhone($phoneSet) { $this->phone  = $phoneSet;}
        public function setDob($dobSet)     { $this->dob    = $dobSet;}


    }

    $newUser = new user;
    var_dump($newUser);
    echo "<br>";

    echo $newUser->getId()      . "<br>";     //  0
    echo $newUser->getName()    . "<br>";     //  name
    echo $newUser->getEmail()   . "<br>";     //  email@email.com
    echo $newUser->getPhone()   . "<br>";     //  (000) 000-0000
    echo $newUser->getDob()     . "<br>";     //  00000000


    $newUser->setId(1);
    $newUser->setName("John");
    $newUser->setEmail("john@gmail.com");
    $newUser->setPhone(7141234567);
    $newUser->setDob("01021992");

    //Print out everything inside the class
    var_dump($newUser);
    echo "<br>";

    echo $newUser->getId()      . "<br>";
    echo $newUser->getName()    . "<br>";
    echo $newUser->getEmail()   . "<br>";
    echo $newUser->getPhone()   . "<br>";
    echo $newUser->getDob()     . "<br>";


    ?>
</details>

- - - -

<!-- 
================================================================
=========================== Constant ===========================
================================================================
-->

<details>
  <summary>File</summary>
   <details>
    <summary>include</summary>
    include(), require(), include_once(), require_once()<br>
    <li>The require() function is identical to include(), except that it handles errors differently.<br></li>
    <li>If an error occurs, the include() function generates a warning, but the script will continue execution.<br></li>
    <li>The require() generates a fatal error, and the script will stop.<br></li>
    <li>The require_once() statement is identical to require() except PHP will check if the file has already been included,<br>
    and if so, not require it again. include_once is as well <br></li>
    

    include('abc.php');
    
  Can break the page to

    header.php
    index.php
    footer.php


  Inside header.php can include function.php


    
   </details>
<!--      -->  
   <details>
    <summary>readfile</summary>
    readfile() function reads a file and writes it to the output buffer.
  
   </details>

   <details>
    <summary>File Open/Read/Close</summary>
    https://www.w3schools.com/php/php_file_open.asp
    
  
   ```fopen()```: Open file<br>
   ```readfile()```: Read file
   ``` fclose()```: Close file
   
    <?php
      $myfile = fopen("webdictionary.txt", "r") or die("Unable to open file!");
      echo fread($myfile,filesize("webdictionary.txt"));
      fclose($myfile);
    ?>
   </details>

   <details>
    <summary>File Open/Write/Close</summary>
    
   Create file: ```$myfile = fopen("testfile.txt", "w"); ``` <br>
   When open a file to write, everything will be erased then start from blank 
   
    $myfile = fopen("newfile.txt", "w") or die("Unable to open file!");
    $txt = "John Doe\n";
    fwrite($myfile, $txt); // write value of $txt fo $myfile
    $txt = "Jane Doe\n";
    fwrite($myfile, $txt);  
    fclose($myfile);

   </details>

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





