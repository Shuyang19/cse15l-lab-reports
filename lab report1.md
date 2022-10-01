# Lab Report 1
## step 1: log into a course-specific account on ieng6

[Link](https://sdacs.ucsd.edu/~icc/index.php)
![Image](https://github.com/Shuyang19/cse15l-lab-reports/blob/main/1.jpg)
![Image](https://github.com/Shuyang19/cse15l-lab-reports/blob/main/2.jpg)

## Step 2: Installing VScode
[Link](https://code.visualstudio.com/)
![Image](https://github.com/Shuyang19/cse15l-lab-reports/blob/main/3.jpg)
Go to the link above and click the download button.

If you successfully download the VScode, open it, you will see the screen below
![Image](https://github.com/Shuyang19/cse15l-lab-reports/blob/main/4.jpg)

## Step 3: Remotely Connecting
-open the terminal in the VScode (terminal—new terminal) and enter a command:
ssh yourusername@ieng6.ucsd.edu
(yourusername is the 11-character account you see in step 1 start with cs15l22fa.)

-Press enter/return, it will show some sentence:

The authenticity of host 'ieng6-202.ucsd.edu (128.54.70.227)' can't be established.

RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.

Are you sure you want to continue connecting (yes/no/[fingerprint])?

-Enter yes and press enter/return

-Then it will ask you to enter the password.

-After entering your password, you are now on the remote server and you will see some picture like below:
![Image](https://github.com/Shuyang19/cse15l-lab-reports/blob/main/5.jpg)

-Now you have successfully connected to the CSE basement, and all commands will run on this computer.

## Step 4: Trying Some Commands
Type some command in the terminal, for example:
* pwd
* ls
* ls -lat
*	ls -a
*	ls /home/linux/ieng6/cs15lfa22/other’s_username
*	cp /home/linux/ieng6/cs15lfa22/public/hello.txt ~/
*	cat /home/linux/ieng6/cs15lfa22/public/hello.txt
![Image](https://github.com/Shuyang19/cse15l-lab-reports/blob/main/6.jpg)
You may see something like the picture above.

## Step 5: Moving Files with scp
First log out the account you current using by:
- Ctrl + D
- Type exit in the terminal
Create a file call WhereAmI.java on your own computer:

class WhereAmI {
  		public static void main(String[] args) {
    			System.out.println(System.getProperty("os.name"));
    			System.out.println(System.getProperty("user.name"));
    			System.out.println(System.getProperty("user.home"));
    			System.out.println(System.getProperty("user.dir"));
  		}
}

Using javac and java command to compile and run the file:
	j
	avac WhereAmI.java
  
  	java WhereAmI

Run the scp command:

scp WhereAmI.java cs15lfa22__@ieng6.ucsd.edu:~/ 
(enter your username on the horizontal line.)

Then login to the account again using ssh command, and you need to enter your password
















