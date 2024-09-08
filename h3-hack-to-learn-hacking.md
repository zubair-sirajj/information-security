# Hack to Learn Hacking

## X) Read/Watch/Listen and Summarize:

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
`ssh bandit0@bandit.labs.overthewire.org -p 2220`
The password for level 0 is bandit0. 
![1](https://github.com/user-attachments/assets/605e7d78-3f85-4c66-a95e-afeb4347e762)

#### **Bandit Level 0 → Level 1**
Once connected, I listed the files using `ls` and found a file named `readme`. 
![2](https://github.com/user-attachments/assets/c00aeb98-a8a1-43a5-8254-d4682d8acd44)
Using `cat readme`, I got the password for the next level.
![3](https://github.com/user-attachments/assets/f8852a7d-414f-4234-80e2-88cef6dcf5d0)

#### **Bandit Level 1 → Level 2**
The next challenge was to find a file named `-` in the home directory. I used the command:
`cat ./-` This gave me the password for Level 2.
![4](https://github.com/user-attachments/assets/a14eb01c-6790-4d71-af55-7f066f7a0a62)

#### **Bandit Level 2 → Level 3**
For this level, the password was stored in a file named "spaces in this filename". I used:
`cat spaces\ in\ this\ filename` and got the password for Level 3.
![5](https://github.com/user-attachments/assets/882310cb-7fae-43e8-9cce-778f29803250)


#### **Bandit Level 3 → Level 4**
The password for Level 4 was hidden in a file inside the `inhere` directory. I used the following commands:
`cd inhere/
ls -a`
I found a hidden file (...Hidding-From-You) and used `cat ...Hidding-From-You` to get the password.
![6](https://github.com/user-attachments/assets/5cc002a9-8f47-489a-807b-f50009cfcf17)


#### **Bandit Level 4 → Level 5**
For this level, the password was stored in a human-readable file in the inhere directory. To identify the file, I used the command: `find . -type f | xargs file`. I found that file07 contained ASCII text and used this command to get the password `cat ./-file07`.
![7](https://github.com/user-attachments/assets/d8b8341f-adbf-4379-9855-30ce0d6ebc6c)

## b) Can't Fish: 
To test packet loss, I disconnected my internet connection and I ran both command to check connectivity, 'ping 1.1.1.1' (Cloudfare DNS server) and 'ping 8.8.8.8' (Google DNS server).
With the network disabled, the output showed 100% packet loss, indicating that the system couldn’t send or receive packets. This confirmed that the network was down. To stop the ping command, I used `Ctrl + C`.
![8](https://github.com/user-attachments/assets/a918095b-a1a4-4ac1-a2ba-eb729e1b4b48)

I also tried the commands with the network connected and the output showed 0% packet loss, indicating that the system was successfully connected to the network. 
![9](https://github.com/user-attachments/assets/d6d68b32-c48c-401a-b22a-0b2ab649751a)


## c)  Local Only
First, I installed nmap using the command: `sudo apt-get install nmap` and then, I scanned my local system by running: `nmap localhost`
![10](https://github.com/user-attachments/assets/2eab80b9-98a4-4667-a8ec-8480e08df972) Before that I disconnected the internet.
The output showed that ports 22 (SSH), 25 (SMTP), and 631 (IPP) were open, while the remaining 997 common TCP ports were closed. This indicates that there are only a few services running on my local machine before installing any new services.
![11](https://github.com/user-attachments/assets/da8f3b69-822e-405c-8ba5-6621d1a96a83)


## d) Daemon
I installed the Apache2 server using the following commands: `sudo apt-get install apache2`. After starting Apache2, I ran nmap again and this time, port 80 (HTTP) was open, in addition to ports 22, 25, and 631. The addition of port 80 indicates that the Apache web server is running, showing the difference in open ports after installing the daemon.

![12](https://github.com/user-attachments/assets/eb745861-f1b7-4e4f-9ffb-8cd4be6d4485)
![13](https://github.com/user-attachments/assets/21bee26a-6e9f-4c6d-a532-4917235dd34c)

So if we try to differentiate two scenarios, we can see that without Apache2, only SSH, SMTP, and IPP were running and after installing and starting Apache2, port 80 opened up for HTTP traffic, illustrating the addition of services impacts the system's network exposure.



## References:
- Nilsson, M. (2024). How CSPM Can Help to Secure Your Cloud and Avoid Configuration Disasters. Disobey 2024. YouTube: https://www.youtube.com/watch?v=binozoaOpOM&list=PLLvAhAn5sGfiB9AlEt2KD7H9Dnr6kbd64&index=2 (Accessed 8 Sept. 2024).
- Karvinen, T. (2020). Command Line Basics Revisited: https://terokarvinen.com/2020/command-line-basics-revisited/ (Accessed 8 Sept. 2024).
- WikiHow (2024). How to Use SSH: https://www.wikihow.com/Use-SSH (Accessed 8 Sept. 2024).
- OverTheWire (2024). Bandit Wargame: https://overthewire.org/wargames/bandit/ (Accessed 8 Sept. 2024).





