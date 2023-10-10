# Lab Report 1

## “cd” command
   
1. With no argument

```
[user@sahara ~]$ cd
```
* There is no output for this command.
* The working directory is "user@sahara~" when the command was run. 
* There is no specified path provided for changing the working directory; as a result, this command does not make sense, and there is no output
* The output is not an error.

2. With a path to a directory as an argument
   
```
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$ 
```

* The working directory is "user@sahara~" when the command was run.  
* When a path to a directory "lecture 1" is provided, the "cd" command alters the working directory from "user@sahara~" to "user@sahara ~/lecture1"
* The output is not an error.
      
3. With a path to a file as an argument
```
[user@sahara ~/lecture1]$ cd Hello.java
bash: cd: Hello.java: Not a directory
```

* The working directory is "user@sahara ~/lecture1" when the command was run.  
* When a path to a file "Hello.java" is provided, the "cd" command alters the working directory from "user@sahara~" to "user@sahara ~/Hello.java"
* The output is an error because the "cd" command expects a directory path, not a file path.

  
## “ls” command

1. With no argument
 
```
[user@sahara ~]$ ls
lecture1
```

* The working directory is "user@sahara~" when the command was run. 
* The "ls" command is used to list the files in the current working directory" "user@sahara~", which is "lecture 1"
* The output is not an error.

2.  With a path to a directory as an argument
  
```
[user@sahara ~]$ ls lecture1
Hello.class  Hello.java  messages  README
```
    
* The working directory is "user@sahara~" when the command was run. 
* The "ls" command is used to list the files in the given path "lecture1", which are "Hello.class", "Hello.java", "messages" and "README".
* The output is not an error.

    
3. With a path to a file as an argument
   a. case 1:
      
```
[user@sahara ~]$ ls Hello.java
ls: cannot access 'Hello.java': No such file or directory
```
* The working directory is "user@sahara~" when the command was run. 
* The "ls" command is used to list the files in the given path "Hello.java" 
* The output is an error because "Hello.java"  is not located directly under "user@sahara~".
      
   b. case 2:
```
[user@sahara ~/lecture1]$ ls Hello.java
Hello.java  
```
* The working directory is "user@sahara ~/lecture1" when the command was run. 
* The "ls" command is used to list the files in the given path "Hello.java".Since 'Hello.java' is a standalone file, the output consists of the file name itself, which is 'Hello.java'.
* The output is not an error.
  
## “cat” command

1. With no argument
```
[user@sahara ~]$ cat
```
* There is no output for this command.
* The working directory is "user@sahara~" when the command was run. 
* The "cat" command is used to print the content of the files given by paths
* The output is an error. There is no specified path provided for printing the contents of the files; as a result, this command does not make sense, and there is no output.
      
2. With a path to a directory as an argument
```
cat lecture1
cat: lecture1: Is a directory
```      
  
* The working directory is "user@sahara~" when the command was run. 
* The "cat" command is used to print the content of the files given by paths "lecture 1".
* The error occurs because the 'cat' command is intended for displaying the contents of files, not directories. Since 'lecture1' is a directory and not a file, attempting to use 'cat' on it results in an error.

3. With a path to a file as an argument

   a. case 1:
```
[user@sahara ~]$ cat Hello.java
cat: Hello.java: No such file or directory
```
* The working directory is "user@sahara~" when the command was run. 
* The "cat" command is used to print the content of the files given by paths "Hello.java".
* The output is an error because "Hello.java" is not located directly under "user@sahara~". 
    
   b. case 2:

```
[user@sahara ~/lecture1]$ cat Hello.java
import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
mport java.nio.file.Path;

public class Hello {
public static void main(String[] args) throws IOException {
String content = Files.readString(Path.of(args[0]),StandardCharsets.UTF_8);    
System.out.println(content);}}[user@sahara ~/lecture1]$ 
```

* The working directory is "user@sahara~" when the command was run. 
* The "cat" command is used to print the content of the files 
"Hello.java", given by paths "Hello.java".
* The output is not an error. 
