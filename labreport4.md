# CS15L Lab Report 4

## Cse Labs "Done Quick"

In the last lab, we tried using several shortcuts to complete the lab tasks as fast as possible. I will introduce some of the commands I used to improve the lab tasks efficiency. 

### Logging into ieng6 account

As we've done generating SSH Keys for ieng6 account, we are no longer need to enter the password for our own ieng6 from our local computer. So, just typing `ssh cs15lwi23avj@ieng6.ucsd.edu` will leads you to log in to your account automatically. 
<img width="746" alt="スクリーンショット 2023-02-27 13 29 20" src="https://user-images.githubusercontent.com/122579654/221690776-33a1de57-8994-4499-b19f-ad64d5a15e59.png">

### Cloning the fork from the repository

Before setting the timer, do not forget to go to your forked lab7 github repository and copy the ssh url. And then enter `git clone <cmd-C><enter>`

<img width="704" alt="スクリーンショット 2023-02-27 13 29 52" src="https://user-images.githubusercontent.com/122579654/221694852-de31a958-5fd9-46fa-beee-dabfd2c0797d.png">


### Run the tests

In order to run the tests, first we have to move the current directory to the lab 7 directory. And after that, to compile the java files, I pressed `<up><up><up><up><enter>` because the command `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` was 4 up in my search history. And then, to run the tests, I, again, pressed `<up><up><up><up><enter>` to get the command `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests`. I assume these two commands were in the same place because I always use these commands sequentially.
<img width="1172" alt="スクリーンショット 2023-02-27 13 56 48" src="https://user-images.githubusercontent.com/122579654/221695030-0b8d2466-6383-4c43-a9d5-09eb19ebd4a4.png">


### Editing the code

In order to edit the code in the ieng6 account, I use `nano`. By entering `nano ListExamples.java` a window below appears.
<img width="1172" alt="スクリーンショット 2023-02-27 14 03 33" src="https://user-images.githubusercontent.com/122579654/221696182-f1801699-289e-445f-b10a-c46871934ffe.png">
Edit the code where the cursor is(delete 0 and the comma) and the bottom `index1` to `index2`.
When finish editing press`<ctrl-o><enter><ctrl-x>` so that the file will be saved and closed.

### Run the tests again

After editing the code by using nano, we have to re-compile and run the java file. So, again, press `<up><up><up><enter>` so that we can compile the java file(just look up the history by clicking `<up>`). Press `<up><up><up><enter>` to run the tests, and it succeeds!
<img width="1176" alt="スクリーンショット 2023-02-27 14 10 35" src="https://user-images.githubusercontent.com/122579654/221697315-6315518b-1313-424e-b28b-b35d37513997.png">

### Commit and push the resultin change

When finishing most part of the parts, it's time to commit and push to your own Github account. Enter `git command -m "Changes"`("Changes" can be any message you want). And `git push origin`. The changes will be updated.
<img width="1176" alt="スクリーンショット 2023-02-27 14 12 14" src="https://user-images.githubusercontent.com/122579654/221697624-2c7891a2-5319-4de2-acd0-47caf8510fc3.png">
