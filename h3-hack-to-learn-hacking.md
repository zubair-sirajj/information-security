# Hack to Learn Hacking

## X) Read/watch/listen and summarize:

### Disobey 2024: How CSPM Can Help to Secure Your Cloud and Avoid Configuration Disasters
**Presenter**: Mikael Nilsson, Product Security Lead at SAS Institute  
In this video, Nilsson discusses Cloud Security Posture Management (CSPM) and its role in preventing cloud configuration disasters.  
- CSPM monitors cloud infrastructure to prevent misconfigurations.  
- Common risks include open S3 buckets and misconfigured databases.  
- Tools like DataDog assist in monitoring, automation, and compliance with frameworks like ISO 27001.  
- Regular monitoring, meetings for triaging findings, and collaboration between development and operations teams are essential for maintaining cloud security.

### Karvinen 2020: Command Line Basics Revisited
This article covers fundamental command-line operations:
- **Moving and Looking Around**: Use `pwd`, `cd`, and `ls` to navigate directories and display contents.
- **File Manipulation**: Commands like `cp`, `mv`, and `rm` for managing files.
- **SSH Remote Control**: Secure remote connections via `ssh` and file transfers with `scp`.
- **Help**: `man` is used for detailed command manuals and `--help` for quick usage hints.
- **History and Guessing**: Arrow keys are used for history and tab for auto-completion.
- **Important Directories**: Key directories like `/home`, `/etc`, and `/var/log` for user data, configurations, and logs.
- **Administrative Commands**: We can run system-wide operations with `sudo`.
- **Package Management**: We use `apt-get` to install, update, or remove software.

Here, the dollar sign (`$`) indicates the user prompt, and the hash mark (`#`) is used to ignore the rest of the line as a comment.

## a) Bandit oh-five

#### **Bandit Level 0**
I started by opening the terminal in my Debian system. I used the following command to log in via SSH:
ssh bandit0@bandit.labs.overthewire.org -p 2220
The password for level 0 is bandit0. 

#### **Bandit Level 0 → Level 1**
Once connected, I listed the files using ls and found a file named readme. Using cat readme, I got the password for the next level.

#### **Bandit Level 1 → Level 2**
The next challenge was to find a file named - in the home directory. I used the command:
cat ./- This gave me the password for Level 2.

#### **Bandit Level 2 → Level 3**
For this level, the password was stored in a file named "spaces in this filename". I used:
cat spaces\ in\ this\ filename and got the password for Level 3.


#### **Bandit Level 3 → Level 4**
The password for Level 4 was hidden in a file inside the inhere directory. I used the following commands:
cd inhere/
ls -a
I found a hidden file (...Hidding-From-You) and used cat ...Hidding-From-You to get the password.


#### **Bandit Level 4 → Level 5**
For this level, the password was stored in a human-readable file in the inhere directory. To identify the file, I used the command: find . -type f | xargs file. I found that file07 contained ASCII text and used this command to get the password cat ./-file07.

## b) Can't Fish: 
To test packet loss, I disconnected my internet connection and I ran both command to check connectivity, 'ping 1.1.1.1' (Cloudfare DNS server) and 'ping 8.8.8.8' (Google DNS server).
With the network disabled, the output showed 100% packet loss, indicating that the system couldn’t send or receive packets. This confirmed that the network was down. To stop the ping command, I used Ctrl + C.
I also tried the commands with the network connected and the output showed 0% packet loss, indicating that the system was successfully connected to the network. 

## References:
- Nilsson, M. (2024). How CSPM Can Help to Secure Your Cloud and Avoid Configuration Disasters. Disobey 2024. YouTube: https://www.youtube.com/watch?v=binozoaOpOM&list=PLLvAhAn5sGfiB9AlEt2KD7H9Dnr6kbd64&index=2 (Accessed 8 Sept. 2024).
- Karvinen, T. (2020). Command Line Basics Revisited: https://terokarvinen.com/2020/command-line-basics-revisited/ (Accessed 8 Sept. 2024).
- WikiHow (2024). How to Use SSH: https://www.wikihow.com/Use-SSH (Accessed 8 Sept. 2024).
- OverTheWire (2024). Bandit Wargame: https://overthewire.org/wargames/bandit/ (Accessed 8 Sept. 2024).





