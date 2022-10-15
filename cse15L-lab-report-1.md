Ricky Li
Joe Politz
30 September 2022

### CSE 15L Lab Report 1

# Installing VScode

![My Image](sc-lab-report-1.PNG)

For the VSCode part, I didn’t have to do anything because I already used VSCode for cse11 last quarter but you can go to the visual studio code website and follow the instructions to download.

# Remotely Connecting

![My Image](sc-lab-report-1-2.PNG)

For remotely connecting, I personally downloaded OpenShell onto my laptop, then I requested to change my password through the ucsd system in order to log in to my remote cse account. It wouldn’t let me connect during lab hours but once I got back home and changed my password again I went through. I logged in using the ssh command followed by the name of my account
Ex. “ssh cs15lfa22zz@ieng6.ucsd.edu”
It will then prompt you for your password. Typing the password is difficult because it doesn’t show you any inputs. The server will tell you that the authenticity of the host cannot be established then ask you if you still want to connect to the host.
Looking like this
The authenticity of host 'ieng6-202.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])? 

After you say yes, you will then be prompted to input your password again

# Trying Some Commands


![My Image](sc-lab-report-1-3.PNG)
![My Image](sc-lab-report-1-4.PNG)

I ran
ls -lat
This command lists/shows all the recently edited files

ls -a
This command lists all the hidden files

cd ~
cd stands for change directory and the little ~ in front changes the directory to the very beginning usually where it says User then your profile

cp /home/linux/ieng6/cs15lfa22/public/hello.txt ~/
Cp as far as I know stands for class path and I assume that

cat /home/linux/ieng6/cs15lfa22/public/hello.txt ~/
This command printed out the txt file hello.txt on the remote server which outputted “Hi! Welcome to CSE15L Fall 22”

# Moving Files with scp


![My Image](sc-lab-report-1-5.PNG)
![My Image](sc-lab-report-1-6.PNG)

I copied the WhereAmI.java file using the command scp command which allows me to grab a file and copy it over to the remote server on my ucsd account. That is when it printed the os, username, the home directory, and my current directory for wherever I was on the remote server. “Linux
cse15lfa22au
/home/linux/ieng6/cse15lfa22/cs15lfa22au
/home/linux/ieng6/cse15lfa22/cs15lfa22au “

# Setting an SSH Key


![My Image](sc-lab-report-1-7.PNG)
![My Image](sc-lab-report-1-8.PNG)

Then using the command ssh-keygen in the lab, I created two keys. I then used the scp command to move one of the keys onto the remote server. 
scp /Users/ricky/.ssh/id_rsa.pub cs15lfa22au@ieng6.ucsd.edu:~/.ssh/authorized_keys
Now I can ssh using the key I created and instead of typing my entire password to login to the remote server every time, I can just use a simpler phrase to continually log in.

# Optimizing Remote Running


![My Image](sc-lab-report-1-9.PNG)

I ran the ls command on the remote computer using my key to easily list the files in the directory. I simply used my passphrase instead of my normal password.
ssh cs15lfa22au@ieng6.ucsd.edu “ls”
 I also used multiple commands at once to compile and run the WhereAmI java file more efficiently instead of changing the path for the code, compiling, then running the code all in separate lines
“cp WhereAmI.java OtherMain.java; javac OtherMain.java; java WhereAmI”


