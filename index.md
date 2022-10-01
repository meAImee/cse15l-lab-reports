# Week 1 Lab Report - Aimee He
# Tutorial- Setting up for CSE15L

---
    Setting up an remote access is an expecially important step when you start youe CSE15L, and here is a short tutorial for you to get ready in just a few steps:
---

## Installing VScode
1. Use this [link](https://code.visualstudio.com/download)  to download **VisualStuioCode** according to Operation System you have.
2. Install the application on your laptop and open the application, you should see a window like this:
![Image](https://github.com/meAImee/cse15l-lab-reports/blob/main/VScodeView.png)



## Remotely Connecting
1. Go to <https://sdacs.ucsd.edu/~icc/index.php> and type in your **student account name** and **pid** for your CSE15L account number.
2. Change your password with the CSE15L specific account you just found in **Remotely Connecting- step 1**. Wait for 10-15mins for system to process.
3. Open a **terminal** on **VScode**.
4. Type in the following command:
    ```
    ssh cs15lfa22zz@ieng6.ucsd.edu
    ```
    Where you should replace the **last two characters** before "@" according to your **personal CSE15L account**.
4.Type in the password you set in **Remotely Connecting- Stept 2**.
5. If you receive an output like this, congratulations! You are now connected!
![Image](https://github.com/meAImee/cse15l-lab-reports/blob/main/ConnectingRemotely.png)



## Trying Some Commands
Try some of the following commands:
- `cd~`
- `cd ..`
- `ls -lat`
- `la -a`
- `ls <directory>`
![Image](https://github.com/meAImee/cse15l-lab-reports/blob/main/TryingCommands.png)


## Moving Files with scp

Try with the follwing code:
```
class WhereAmI {
  public static void main(String[] args) {
    System.out.println(System.getProperty("os.name"));
    System.out.println(System.getProperty("user.name"));
    System.out.println(System.getProperty("user.home"));
    System.out.println(System.getProperty("user.dir"));
  }
}
```

Then complie and run using the following command:

```
javac WhereAmI.java
java WhereAmI
```
Then, in terminal, run this command:
```
scp WhereAmI.java cs15lfa22zz@ieng6.ucsd.edu:~/
```
*remember to replace **the last two characters** before "@" according to your **cse15l personal account**.

Type in your password, and then you should be able to access the file with ssh, just like this:
![Image](https://github.com/meAImee/cse15l-lab-reports/blob/main/SCP.png)



## Setting an SSH Key
This is for setting up your **passcode-less** login for your ssh.
1. Type the following command in **terminal**
    ```
    ssh-keygen
    ```
2. Press **enter**.
3. If you’re on Windows, follow the extra `ssh-add` steps here: https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_keymanagement#user-key-generation
4. Now log into your ssh.
5. Type in:
    ```
    mkdir .ssh
    <logout>
    ```
6. Back on client, enter the following command:
    ```
    scp /Users/joe/.ssh/id_rsa.pub cs15lfa22@ieng6.ucsd.edu:~/.ssh/authorized_keys
    ```
    *Remember to use your own username and account.
7. With all the steps above, you should be able to log into your ssh without password, like this:
![Image](https://github.com/meAImee/cse15l-lab-reports/blob/main/SSHKey.png)





## Optimizing Remote Running*/
Here are some hints to make your experience with ssh more pleasant:
1. Add an 'ls' at the end of your ssh command;
    ```
    ssh cs15lfa22@ieng6.ucsd.edu "ls"
    ```
2. Use semicolons to run multiple command at the same time:
    ```
    cp WhereAmI.java OtherMain.java; javac OtherMain.java; java WhereAmI
    ```
3. Recall the last command using the **up-arrow**.
![Image](https://github.com/meAImee/cse15l-lab-reports/blob/main/%E6%88%AA%E5%B1%8F2022-09-30%20%E4%B8%8B%E5%8D%8811.58.09.png)


## Congratulations! You're done!
