# CSE15L Lab Report 1

## 1. how to install VScode

Go to [VScode](https://code.visualstudio.com/). Before you click download, make sure not to forget choosing the same version as your OS(You can click the arrow button which is on the right of "Download" to choose the different version).
After the installation, open VScode and it should appear the screen like this↓

<img width="1470" alt="スクリーンショット 2023-01-12 16 24 24" src="https://user-images.githubusercontent.com/122579654/212776202-4c292bf5-737c-4eb2-9544-abed62df47cc.png">


## 2. remote connecting

first of all, before you write codes on your terminal, you have to reset your ucsd password in order to connect to the ucsd server. You can register and change your password at https://sdacs.ucsd.edu/~icc/index.php If you are in trouble check the following tutorial site: [Tutorial for changing the password](https://docs.google.com/document/d/1hs7CyQeh-MdUfM9uv99i8tqfneos6Y8bDU0uhn1wqho/edit). 

next, open terminal in your VScode
then next, type the command below

`$ ssh cs15lwi23avj@ieng6.ucsd.edu`

after that, you will be required to enter your own ucsd cse account password. Enter the password then you should see the screen like this

<img width="1470" alt="スクリーンショット 2023-01-12 17 15 49" src="https://user-images.githubusercontent.com/122579654/212776244-77998642-11f4-4fdb-ba17-3631838fc0e8.png">



## 3. trying some commands

In this terminal, you can try lots of commands. For example, if you enter

`$ cat /home/linux/ieng6/cs15lwi23/public/hello.txt`

the cat command will output the contents of the following objects in the repository.

so in this case, you would get "Hello! Welcome to CSE 15L" (See the bottom line in the screenshot)

<img width="1470" alt="スクリーンショット 2023-01-16 14 39 46" src="https://user-images.githubusercontent.com/122579654/212776275-cd67272b-ad5d-4e29-a099-94fc3deaf763.png">

there are other commands you can try

* cd ~
* ls -lat
* cp /home/linux/ieng6/cs15lwi23/public/hello.txt ~/


