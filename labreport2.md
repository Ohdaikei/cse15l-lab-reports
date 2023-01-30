# CSE15L Lab Report 2

## Part1. Creating a simple web server

In the lab fo week 2, we built and ran a NumberServer by using a passed out URL Handler Interface and java server files. By utilizing the process we performed in the second week of the lab, I made a new server called StringServer that records the String data I entered in the URL. The codes is attatched first and then the examples I used is attatched next.

<img width="853" alt="スクリーンショット 2023-01-30 13 19 20" src="https://user-images.githubusercontent.com/122579654/215600056-7da2a72f-3229-4268-bafe-a806afebb413.png">

<img width="853" alt="スクリーンショット 2023-01-30 13 24 10" src="https://user-images.githubusercontent.com/122579654/215600283-e21faed0-74d3-4ec7-bebc-35307f9c7b8a.png">

In the first screenshot, I entered "add-message?s=Hello" in the URL. As "add-message" is written in the URL, the code will split the path by "=". Then the'parameters[0]' is "s" in this case, a String will be output. The String is initialized to '""' at first so the 'String message' will be updated to 'parameters[1]' which is Hello, in this case. As a result, Hello will be printed in the web page, which is expected.

<img width="579" alt="スクリーンショット 2023-01-30 13 24 59" src="https://user-images.githubusercontent.com/122579654/215603256-26ff78e8-d1b9-42a8-ba52-5ddf94d792fc.png">


In the second screenshot, I entered "How Are You" in the URL as I went along. The same way as the first screenshot, the "add-message" will cause the code to split the path by "=", and the 'paraneters[0]' is also "s". However, in this case, the 'String message' is not '""', and it is "Hello" instead, the else statement will be called. This code will record the previous String message and update the message by the next String 'parameters[1]' which is "How Are You" in this case. The point is there is a "\n" between the previous String and new String, it will allow to print out the String in the web server in a new line.

