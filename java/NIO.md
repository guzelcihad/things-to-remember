# History
- Java IO released in 1996 in Java1 version
- Java NIO introduced in 2002 in Java4
- Java NIO2 introduced in 2011 in Java7

# NIO
New I/O
There are some issues with Java I/O
- writes one byte/char at a time which is not efficient for bulk operation.
- buffering occurs in JVM heap memory which is not good for big files
- handling of charset is not greate
- all the operations are synchronous

NIO Provides
- bulk access to raw bytes
- off heap buffering
- asynchronous
- support for charsets

Ways to read file 

```
Path path = Paths.get("C:\\Users\\cguzel\\Desktop\\deneme.txt");
System.out.println(path.getFileName());

// java 11 way
Path of = Path.of("C:\\Users\\cguzel\\Desktop\\deneme.txt");
System.out.println(of.getFileName());
```

## Reading
Files can be in two format. Binary files and charset files
<br>
Charset can be encoded, there are any encoders. ASCII, UTF-8

- Create a path
- get a BufferedReader 
- read line
```
BufferedReader bufferedReader = Files.newBufferedReader(path);
String line = bufferedReader.readLine();
System.out.println(line);
```

What can be wrong?
File may not exist or not have the right encoding.

We can use;
```
BufferedReader bufferedReader = Files.newBufferedReader(path, StandardCharsets.ISO_8859_1);
```  

## Writing
- Create a path
- get a BufferedWriter 
- Write

``` 
BufferedWriter bufferedWriter = Files.newBufferedWriter(path);
bufferedWriter.write("hi");
``` 

What can go wrong?
- File may not exist
- flush the buffer before closing it.

## Stream API
``` 
Files.lines(path); //Returns a stream
``` 
Stream in java also implements AutoCloseable interface so we can use try-with-resource pattern.