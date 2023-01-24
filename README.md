# Computer Science I Device Setup
**[School of Computing](https://computing.unl.edu/)**  
**[College of Engineering](https://engineering.unl.edu/)**  
**[University of Nebraska-Lincoln](https://unl.edu)**

This repository serves as a reference for helping students enrolled in CSCE
155A set up a local development environment and access files stored remotely
on the CSE server.


## Claim Your CSE Account
The first thing you should do as a new student in the School of Computing is
claim your CSE account. You can do so by clicking
[this link](https://cse-apps.unl.edu/amu/claim_start).  

If you run into trouble claiming your CSE account, first read the `School of
Computing Resources` section of the page
[linked here](https://computing.unl.edu/faq-section/account-and-general-issues/).
If you are still having issues, let your TA know and they will either help you
out or point you to sysadmin if it's a trickier problem.


## Unix Basics
***RTM.*** Just kidding, for now use the commands given in the lab 01 quiz. We
will flesh this section out at new commands are introduced. (But also do RTM).


## Secure Shell (SSH)
Now that you have an account on the CSE server, you have some space set aside
for your very own files and directories. But you *probably* need some way to
access it. This can be done through a tool like Secure Shell (SSH).

If your device is running an up-to-date version of Windows or macOS, you should
already be able to use SSH in your terminal. A guide for logging in can be found
below.

<details>
  <summary>Click here for a guide on using SSH in Windows and macOS</summary>  

  1. While focused in your terminal app, you should see a prompt with a blinking
  cursor. This is where you can enter commands and use tools like SSH.

  ```
    Last login: Tue Jul  3 20:59:45 on ttys000
    local-prompt>
  ```

  2. To log in to the CSE server, type `ssh [login ID]@cse.unl.edu` where
  `[login ID]` is replaced with the login ID of your CSE account.
  In this example, my login ID is 'jsmith'. Enter this command and you should
  see a prompt for your password.  

   **NOTE:** You will likely receive a prompt saying that the authenticity of
  host 'cse.unl.edu' can't be established if this is your first time
  connecting to the CSE server through SSH. Enter `yes` to reach the password
  prompt as shown below.

  ```
    local-prompt> ssh jsmith@cse.unl.edu
    The authenticity of host 'cse.unl.edu (10.211.11.120)' can't be established.
    RSA key fingerprint is 3f:1b:f4:bd:c5:aa:c1:1f:bf:4e:2e:cf:53:fa:d8:59.
    Are you sure you want to continue connecting (yes/no)? yes
    (jsmith@cse.unl.edu) Password:
  ```

  3. Type the password for your CSE account into the prompt. You will not see
  anything actually being typed as you do this, this is a security measure just
  like the dots that pop up when you log in to a website.

  If you entered the correct password, you should see a lovely header welcoming
  you to the CSE server!

    ```
      Last login: Tue Jul  3 11:05:12 2019 from 101.231.303.416
      ******************************************************************************
                                     Welcome to CSE
      ******************************************************************************

      The operating system on this computer was upgraded on March 18, 2018.

      Please contact "manager@cse.unl.edu" to report problems, request software
      or ask questions about this system.

      ******************************************************************************
      cse.unl.edu-prompt>
    ```

  4. At this point, you have successfully used SSH to log into the CSE server
  and can view the files and directories you have stored there. Keep in mind,
  you will time out of the server if you are idle for too long. If this happens,
  just login with SSH again (Starting at step 2 of this section).

</details>


## Secure Copy (SCP)
Using SSH, you can view and even edit files that are stored on the CSCE server.
Without the help of another tool, though, you can't move your files between the
server (remote) and your own machine (local). Luckily, we aren't the first
computer scientists to run into this problem and it's already been solved for
us. This tool is called Secure Copy (SCP).  

With SCP, there are two directions we should be concerned with at this point.
Remote to local would copy from the server to your machine. Local to remote
would copy from your machine to the server.  

Both scenarios involve arguments for SCP that look very similar, so be wary. The
simplest way to remember the command is as `scp [source] [target]`. Guides for
either case can be found below.

<details>
  <summary>Click here for a guide on remote to local SCP in Windows and macOS</summary>

  1. While focused in your terminal app, you should see a prompt with a blinking
  cursor. This is where you can enter commands and use tools like SCP.  

   **NOTE:** Notice the prompt below is `local-prompt`, meaning that we are not
  currently logged in to the CSE server via Secure Shell (SSH). Make sure you
  are logged out of the server at this point.

  ```
    Last login: Tue Jul  3 20:59:45 on ttys000
    local-prompt>
  ```

  2. To copy a file stored on the CSE server to your own machine, type `scp
  [login ID]@cse.unl.edu:[remote filepath] [local filepath]`, where `[login ID]`
  is replaced with the login ID of your CSE account. In this example, my login
  ID is 'jsmith'.  

  `[remote filepath]` is the location on the server of the file you'd like to
  copy. A Unix shortcut for home directory is `~`. In this example, I am copying
  a text file called 'my_file.txt' which is stored in a folder on my server
  account called 'my_directory'.

  `[local filepath]` is the location on your machine you'd like to copy *to*. In
  this example, I am copying that text file to a folder in my home directory
  called 'Desktop'.

  If filepaths and command arguments are confusing, please review the `Unix
  Basics` section of this page or reach out to a TA. Enter this command and you
  should see a prompt for your password.  

   **NOTE:** SCP will *mercilessly* overwrite any file stored at your target
  that has the exact same filename as your source. Unix is powerful but make
  sure you know what will happen before executing a command.

  ```
    local-prompt> scp jsmith@cse.unl.edu:~/my_directory/my_file.txt ~/Desktop/
    (jsmith@cse.unl.edu) Password:
  ```

  3. Type the password for your CSE account into the prompt. You will not see
  anything actually being typed as you do this, this is a security measure just
  like the dots that pop up when you log in to a website.

  If you entered the correct password and filepaths, you should see a new line
  in your terminal indicating the status of your desired file.

  ```
    my_file.txt                                 100%    0     0.0KB/s   00:00    
    local-prompt>
  ```

  4. Once the percentage reaches 100%, you have successfully copied a file from
  the CSE server to your own machine! You can find this copy in the location you
  specified as `[local filepath]` when first running SCP.

</details>

<details>
  <summary>Click here for a guide on local to remote SCP in Windows and macOS</summary>

  1. While focused in your terminal app, you should see a prompt with a blinking
  cursor. This is where you can enter commands and use tools like SCP.  

   **NOTE:** Notice the prompt below is `local-prompt`, meaning that we are not
  currently logged in to the CSE server via Secure Shell (SSH).  Make sure you
  are logged out of the server at this point.

  ```
    Last login: Tue Jul  3 20:59:45 on ttys000
    local-prompt>
  ```

  2. To copy a file stored on your own machine to the CSE server, type `scp
  [local filepath] [login ID]@cse.unl.edu:[remote filepath]`, where `[login ID]`
  is replaced with the login ID of your CSE account. In this example, my login
  ID is 'jsmith'.  

  `[local filepath]` is the location on your machine of the file you'd like to
  copy. A Unix shortcut for home directory is `~`. In this example, I am copying
  a text file called 'my_file.txt' which is stored in a folder in my home
  directory called 'Desktop'.

  `[remote filepath]` is the location on the server you'd like to copy *to*. In
  this example, I am copying that text file to a folder on my server account
  called 'my_directory'.

  If filepaths and command arguments are confusing, please review the `Unix
  Basics` section of this page or reach out to a TA. Enter this command and you
  should see a prompt for your password.  

   **NOTE:** SCP will *mercilessly* overwrite any file stored at your target
  that has the exact same filename as your source. Unix is powerful but make
  sure you know what will happen before executing a command.

  ```
    local-prompt> scp ~/Desktop/my_file.txt jsmith@cse.unl.edu:~/my_directory/
    (jsmith@cse.unl.edu) Password:
  ```

  3. Type the password for your CSE account into the prompt. You will not see
  anything actually being typed as you do this, this is a security measure just
  like the dots that pop up when you log in to a website.

  If you entered the correct password and filepaths, you should see a new line
  in your terminal indicating the status of your desired file.

  ```
    my_file.txt                                 100%    0     0.0KB/s   00:00    
    local-prompt>
  ```

  4. Once the percentage reaches 100%, you have successfully copied a file from
  your own machine to the CSE server! You can find this copy in the location you
  specified as `[remote filepath]` when first running SCP. You will need to log
  in via SSH to do this.

</details>


## Frequently Asked Questions
**Q:**  Feel free to ask as many questions as you want during labs! If any are
common enough, we will either update a page section or will address it here.  
**A:**  
