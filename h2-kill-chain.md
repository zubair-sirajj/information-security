# H2 Kill Chain

## Summary of "Intelligence-Driven Computer Network Defense Informed by Analysis of Adversary Campaigns and Intrusion Kill Chains"
The paper discusses a smarter way to protect computer networks called "Intelligence-Driven Computer Network Defense." It's based on the Cyber Kill Chain, which breaks down a hacker’s steps into specific stages. This approach moves away from just reacting when attacks happen to actively preparing and stopping attacks by understanding the hackers' moves.

### Advanced Persistent Threats (APT)
APT represents well-resourced and trained adversaries that conduct multi-year intrusion campaigns targeting highly sensitive economic, proprietary, or national security information. Traditional defenses like firewalls and antivirus software often prove ineffective against these sophisticated threats due to their reactive nature. The paper emphasizes the necessity of an intelligence-driven approach to identify and counter these threats.

### What is the Cyber Kill Chain?
The Cyber Kill Chain model helps in understanding and defending against cyber attacks by detailing the sequence of steps an attacker follows:
- **Reconnaissance**: Gathering information about the target to find vulnerabilities.
- **Weaponization**: Creating or adapting malware tailored to exploit the discovered vulnerabilities.
- **Delivery**: Transmitting the malware to the target through methods like phishing emails, malicious websites, or USB drives.
- **Exploitation**: Activating the malware to execute unauthorized actions on the target system.
- **Installation**: Installing additional tools that allow the attacker to maintain hidden access to the system.
- **Command and Control**: Establishing a remote connection that lets attackers control the compromised system and execute further malicious activities.
- **Actions on Objectives**: Achieving the primary goal, which could be data theft, service disruption, or other damage.

By thoroughly understanding these steps, defenders can better prepare to thwart attacks at any stage. Disrupting even one step can potentially stop the entire attack.

### Intelligence-Driven Defense Approaches
- **Linking Defenses to Kill Chain Phases**: Each phase of the kill chain presents specific opportunities for detection and intervention. For instance, improving email filtering can prevent the delivery of phishing emails, while enhancing monitoring of outbound network traffic can help detect signs of command and control communications.
- **Indicator Life Cycle**: Discusses continuous improvement of defense strategies by learning from past attacks. This includes identifying and analyzing indicators of malicious activity to adapt and enhance security measures, making the defense more adept at recognizing and stopping future threats.

### How This Helps
Understanding and disrupting any phase of the kill chain can prevent the full execution of an attack. This model aids organizations in effectively allocating resources by identifying the most vulnerable stages of an attack and the optimal points for intercepting attackers.

### Case Studies and Practical Applications
The paper includes case studies that demonstrate how the Cyber Kill Chain framework has been effectively utilized by various organizations to intercept and mitigate attacks at different stages. These practical applications provide a clear guide for others looking to implement similar strategies.

### Future Directions and Challenges
#### Adapting to Evolving Threats
The paper discusses the evolving nature of cyber threats and the need for dynamic defense strategies that can adapt as new threats emerge. It highlights the ongoing challenge of developing new malware and sophisticated attack vectors that exploit zero-day vulnerabilities.

### Personal Insight/Question
- **Insight**: This paper suggests a shift in how we think about cybersecurity, advocating for a proactive stance where organizations try to predict and counteract hacker actions before any damage occurs.
- **Question**: With the rise of AI and other advanced technologies, how should the Cyber Kill Chain be updated to address these increasingly sophisticated cyber threats?

### Reference:
1. Hutchins et al 2011: Intelligence-Driven Computer Network Defense Informed by Analysis of Adversary Campaigns and Intrusion Kill Chains: https://lockheedmartin.com/content/dam/lockheed-martin/rms/documents/cyber/LM-White-Paper-Intel-Driven-Defense.pdf 

## a) Bookworm. Install Debian 12-Bookworm Linux, in a virtual machine in VirtualBox:
This outlines the steps I took to install Debian 12 "Bookworm" on a Virtual Machine using Oracle VM VirtualBox on a Windows platform.

### System Specifications
- **Host OS**: Windows
- **Debian ISO**: debian-live-12.6.0-amd64-xfce.iso

![Screenshot (203)](https://github.com/user-attachments/assets/f2cb67e6-2a8c-419d-bc61-6774ffb8e16d)

### Steps to Install Debian
**Open VirtualBox, Launch Application and Create Virtual Machine**: I started by opening VirtualBox on my Windows computer which I already had installed. This prepared me to set up a new virtual environment. I clicked on "New" to create a new virtual machine.
![Screenshot (202)](https://github.com/user-attachments/assets/1e3a6003-1510-4849-ad1b-b3288057f9c5)

I entered "Debian" as the name for the virtual machine to identify it easily. I also selected the Debian ISO file. I also skiped Unattended Installation.

![Screenshot (204)](https://github.com/user-attachments/assets/e18c342b-0d2b-42ff-8bf6-4717c6a7dd60)

**Base Memory**: I allocated 4096 MB of RAM to ensure the VM operates smoothly under various workloads.
**CPU**: I allocated just 1 CPU to the virtual machine.

![Screenshot (205)](https://github.com/user-attachments/assets/8fd14b47-99d8-4e56-ba29-4ba6dccd1b05)

I created a virtual hard disk and set the disk size to 20 GB
![Screenshot (206)](https://github.com/user-attachments/assets/c3fa9dbe-d468-48d7-ba7f-2d72881ca985)

I get a summery of everything I selected and I click 'Finish'.

![Screenshot (207)](https://github.com/user-attachments/assets/bbe946a5-5e45-43c2-9e52-3d7bceeb87f9)

Now it's ready to start.
![Screenshot (208)](https://github.com/user-attachments/assets/7e03161a-4c81-48a0-aa7c-f59a752d6ba5)

Then I just start it and it starts powering up.
![Screenshot (209)](https://github.com/user-attachments/assets/33a41427-136a-43d5-8fd4-4f81278c2a00)

The boot menu is showed and from there I select the Live System to boot into a live session of Debian
![Screenshot (210)](https://github.com/user-attachments/assets/bddbd969-66d2-48b5-b4ad-0d56d0e78d2f)

Now it shows an error message, 'This kernel requires an x86-64 CPU, but only detected an i686 CPU. I think this happened because the virtual machine (VM) I used does not support 64-bit architecture.
![Screenshot (211)](https://github.com/user-attachments/assets/28fd2a6d-cd45-471a-b633-d842ae16a6b6) 

I will upgrade it to 64-bit architecture, but I want to try installing the 32-bit Debian.  
![Screenshot (213)](https://github.com/user-attachments/assets/b0a81768-4331-4f84-8cbf-0a2191c6194e)
![Screenshot (214)](https://github.com/user-attachments/assets/21acd49a-baee-4a91-933c-1553ef66455d)
![Screenshot (215)](https://github.com/user-attachments/assets/e3edd18f-8ba1-4ab5-835b-c7f60e339562)
![Screenshot (216)](https://github.com/user-attachments/assets/4ac985a6-b20e-4ff1-84ec-8a892ce768c0)
![Screenshot (217)](https://github.com/user-attachments/assets/f3b59102-7d40-49fe-8e88-7268ef2b860d)
![Screenshot (218)](https://github.com/user-attachments/assets/1418bdb8-ff69-4e7a-968c-d39e3e9ed674)
![Screenshot (219)](https://github.com/user-attachments/assets/66e1ba0e-3534-4e25-9015-372660cb6034)
