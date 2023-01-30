# CSE15L Lab Report 2

## Part1. Creating a simple web server

In the lab of week 2, we built and ran a NumberServer by using a passed out URL Handler Interface and java server files. By utilizing the process we performed in the second week of the lab, I made a new server called StringServer that records the String data I entered in the URL. The codes is attatched first and then the examples I used is attatched next.




In the first screenshot, I entered "add-message?s=Hello" in the URL. As "add-message" is written in the URL, the code will split the path by "=". Then the 
`parameters[0]` 
is "s" in this case, a String will be output. The String is initialized to 
`""` 
at first so the 
`String message` 
will be updated to 
`parameters[1]` 
which is Hello, in this case. As a result, Hello will be printed in the web page, which is expected.




In the second screenshot, I entered "How Are You" in the URL as I went along. The same way as the first screenshot, the "add-message" will cause the code to split the path by "=", and the `paraneters[0]` is also "s". However, in this case, the 'String message' is not `""`, and it is "Hello" instead, the else statement will be called. This code will record the previous String message and update the message by the next String `parameters[1]` which is "How Are You" in this case. The point is there is a "\n" between the previous String and new String, it will allow to print out the String in the web server in a new line.

