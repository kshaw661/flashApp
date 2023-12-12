# li₃ 

##Installation Process

1. Download the Zip file/github url

2. Place the project in respective folder(We are using windows machine with xampp software)

3. I have taken the li3 library from below path.

   https://github.com/UnionOfRAD/lithium/tree/v2.0.0

4. Place the lithium library files in root folder inside 'libaries' folder.

5. Please install PHP8.1/PHP8.2 version. (We have used PHP8.1 version)

6. Install the flash library that is available in the project root folder as flash.zip, Unzip that file and place the flash libary folder inside 'libraries' folder.

7. Setup the database, the database sql export file is kept inside Database folder, create a new database with the name as "database".

8. Run the project in localhost.



##Issues/Observations

1. We have issue while reading the flash library messages. We have writen a sample Flash::write() and Flash::read() code inside PagesController to showcase the issue.

   We are getting below mentioned error

   Warning: Array to string conversion in C:\xampp\htdocs\FlashApp\app\extensions\adapter\storage\session\Model.php on line 258

2. In config\bootstrap\session.php file we have kept adapter setting as Model, which is the file coming from app\extensions\adapter\session\Model.php

3. We are using the session_set_save_handler function for all the session operations in Model.php file (This is a li3 model adapter file).

4. While trying to read the flash messages, We are getting an issue near _read function (Line no 258). As per the php8 new changes, the return type of the read method is string, so we have later changed return type with typecasting as string.
You can also please remove the typecasting (string) from the code(Line no 258) and check the actual error.

5. We are expecting the issue is somewhere from internal library files.
