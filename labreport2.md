# CSE15L Lab Report 2

## Part 1. Creating a simple web server

In the lab of week 2, we built and ran a NumberServer by using a passed out URL Handler Interface and java server files. By utilizing the process we performed in the second week of the lab, I made a new server called StringServer that records the String data I entered in the URL. The codes is attatched first and then the examples I used is attatched next.


<img width="853" alt="スクリーンショット 2023-01-30 13 19 20" src="https://user-images.githubusercontent.com/122579654/215609613-a854a3db-c380-476b-868e-aabb9db47a51.png">

<img width="853" alt="スクリーンショット 2023-01-30 13 24 10" src="https://user-images.githubusercontent.com/122579654/215609724-f7487cc4-a2f3-4a98-b3f0-001301fdd9bd.png">


In the first screenshot, I entered "add-message?s=Hello" in the URL. As "add-message" is written in the URL, the code will split the path by "=". Then the 
`parameters[0]` 
is "s" in this case, a String will be output. The String is initialized to 
`""` 
at first so the 
`String message` 
will be updated to 
`parameters[1]` 
which is Hello, in this case. As a result, Hello will be printed in the web page, which is expected.


<img width="579" alt="スクリーンショット 2023-01-30 13 24 59" src="https://user-images.githubusercontent.com/122579654/215609752-f56a983f-b5fb-4513-9825-e66ae7ba6ef9.png">


In the second screenshot, I entered "How Are You" in the URL as I went along. The same way as the first screenshot, the "add-message" will cause the code to split the path by "=", and the `paraneters[0]` is also "s". However, in this case, the 'String message' is not `""`, and it is "Hello" instead, the else statement will be called. This code will record the previous String message and update the message by the next String `parameters[1]` which is "How Are You" in this case. The point is there is a "\n" between the previous String and new String, it will allow to print out the String in the web server in a new line.

## Part 2. Finding and fixing the symptoms and bugs

In the third week of the lab, we were given a set of example codes and JUnit testing codes which would induce bugs or symptoms. I will introduce one of the examples which I fixed in the lab.

A failure-inducing input for the buggy program, as a JUnit test and any associated code

```java
public class ArrayTests {
	@Test 
	public void testReverseInPlace() {
    int[] input2 = {1,2,3,4};
    ArrayExamples.reverseInPlace(input2);
    assertArrayEquals(new int[]{4,3,2,1},input2);
	}
  ```
  
An input that doesn’t induce a failure, as a JUnit test and any associated code

```java
public class ArrayTests {
	@Test 
	public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}
  ```
  
<img width="1150" alt="スクリーンショット 2023-01-30 14 51 06" src="https://user-images.githubusercontent.com/122579654/215614730-64b26840-b7be-434f-b4d8-90aaceb861d2.png">
<img width="602" alt="スクリーンショット 2023-01-30 14 53 03" src="https://user-images.githubusercontent.com/122579654/215614763-eb3a492c-dd23-43d3-9bbf-e44782662e34.png">

Before:
```java
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
  ```
  
After:
```java
static void reverseInPlace(int[] arr) {
    int[] newArr = new int[arr.length];
    for(int i = 0; i < arr.length; i++) {
      newArr[arr.length - 1 - i] = arr[i];
    }
    for(int i = 0; i < arr.length; i++){
      arr[i] = newArr[i];
    }
  }
  ```

The mistake in the first code is that it constantly updates the array. If you keep updating the array, when you get to the second half of the array, instead of changing the order, you change it to whatever you changed during the current for-loop. This is not what we expected because what you actually want to do is reverse the order of the arrays before the method is called.
The modified version is described next. The modified code creates a new, temporary array which replaces each of its elements with an element from the original array in the reverse order. The key point is that the contents of the arrays are replaced, rather than just replacing the newly created temporary arrays.

# Part 3. 

What I learned from this week's and last week's labs is that even seemingly correct codes can easily be found to be wrong when tested. I took CSE11 last semester where we had to submit our code as a weekly programming assignment, and it was very interesting to see how the autograder was able to find these bugs and symptoms in a matter of seconds. Especially in this lab, I wrote various patterns of code to find bugs and tested them over and over again to see if they were successful. I realized that methods that at first glance seem to be easy to express can actually take a long time to write, and that we need to handle exceptions and so on when writing test code.

