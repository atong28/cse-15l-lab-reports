# Lab Report 1
#### Anthony Tong, CSE 15L | PID A17720195
v2
## Sample commands

1. Using `cd`

With no arguments, we simply return to the home directory:
- Current working directory: `/home/lecture1`
- No error
```
[user@sahara ~/lecture1]$ cd
[user@sahara ~]$
```
If we then include the path to a directory as an argument, we enter that directory:
- Current working directory: `/home`
- No error
```
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$
```
Finally, if we include the path to a file as an argument, it throws an error because you cannot change directories into a file:
- Current working directory: `/home/lecture1`
- Error
```
[user@sahara ~/lecture1]$ cd Hello.java
bash: cd: Hello.java: Not a directory
```

2. Using `ls`

With no arguments, we simply list the files of the current working directory:
- Current working directory: `/home/lecture1`
- No error
```
[user@sahara ~/lecture1]$ ls
Hello.class  Hello.java  messages  README
```
If we then include the path to a directory as an argument, we list the files of that directory:
- Current working directory: `/home/lecture1`
- No error
```
[user@sahara ~/lecture1]$ ls messages
en-uk.txt  en-us.txt  es-mx.txt  zh-cn.txt
```
Finally, if we include the path to a file as an argument, it lists that file specifically:
- Current working directory: `/home/lecture1`
- No error
```
[user@sahara ~/lecture1]$ ls Hello.class
Hello.class
```

3. Using `cat`

With no arguments, it enters an input mode which echoes your input back to you:
- Current working directory: `/home/lecture1`
- No error
```
[user@sahara ~/lecture1]$ cat
Hello.java
Hello.java
hi
hi
hello
hello
```
If we then include the path to a directory as an argument, it throws an error because you cannot list the contents of a directory:
- Current working directory: `/home/lecture1`
- Error
```
[user@sahara ~/lecture1]$ cat messages
cat: messages: Is a directory
```
Finally, if we include the path to a file as an argument, it prints the contents of the file:
- Current working directory: `/home/lecture1`
- No error

```
[user@sahara ~/lecture1]$ cat Hello.java
import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
import java.nio.file.Path;

public class Hello {
  public static void main(String[] args) throws IOException {
    String content = Files.readString(Path.of(args[0]), StandardCharsets.UTF_8);    
    System.out.println(content);
  }
}
```
