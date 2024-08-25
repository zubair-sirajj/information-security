# Assignment: Should Tero Wear a Helmet?

## Threat Modeling

### 1. Braiterman et al. 2020: Threat Modeling Manifesto

The Threat Modeling Manifesto is all about making sure threat modeling isn't just a one-time thing but a continuous process. It stresses the importance of involving people throughout, keeping security practical, and always learning and adapting.

- It focuses on involving people throughout the process.
- Makes sure security measures are practical and aligned with actual risks.
- Focuses on ongoing learning and adaptation.
- Threat modeling is an ongoing continuous process, not a one-time task.

The core questions it raises are:
- What are we working on? – Figuring out what parts of the system we need to protect.
- What can go wrong? – Spotting the threats and weak spots in the system.
- What are we going to do about it? – Deciding how to fix or reduce those risks.
- Did we do a good enough job? – Checking if the fixes actually worked and improving where needed.

Question: How can we blend continuous threat modeling into an agile development process without slowing everything down?

### 2. Shostack 2022: Welcome to the World's Shortest Threat Modeling Course

This course offers a concise introduction to threat modeling, covering:

- Key Concepts:
  - Identifying Assets and Threats: Figuring out what you need to protect and what could go wrong.
  - Attack Surface: Looking at where your system might be vulnerable to attacks.
  - Thinking Like an Attacker: Getting into the mindset of a hacker to find weaknesses before they do.

- Data Flow Diagrams (DFDs):
  - Helps to see how data moves through a system.
  - Helps to identify potential vulnerabilities.

- Iterative Process: Emphasizes that threat modeling isn’t a one-time thing; it needs to keep evolving as things change.

Question: What tools or strategies can help keep Data Flow Diagrams up to date in fast-changing environments?

### 3. OWASP CheatSheets Series Team 2021: Threat Modeling Cheat Sheet

The OWASP Cheat Sheet is a handy guide for practical threat modeling. The cheat sheet emphasizes starting simple, using tools to streamline the process, and making threat modeling a regular activity. It covers:

- Steps in the Process:
  - Identifying Assets: Figuring out what we need to protect.
  - Creating an Architecture Overview: Mapping out the system components and how the data flows between them.
  - Decomposing the Application: Breaking down the system to see where the control points are.
  - Identifying Threats: Using methods like STRIDE to spot and rank risks.
  - Mitigating Threats: Coming up with ways to reduce or get rid of the risks.

- Best Practices:
  - Start Simple: We need to focus on the most important parts first.
  - Use Tools: It’ll be easier if we use automated tools.
  - Regularity: We need to keep updating our threat model as the system changes.

Question: How can any organization ensure that threat modeling is done consistently and effectively across all different teams?

## Infosec Scene: Darknet Diaries Podcast Episode Summary

### Episode Chosen: Episode 119 - "The Lazarus Heist"

- Overview:
  - This episode talks about a series of cryptocurrency heists pulled off by the Lazarus Group, a North Korean cybercrime organization. Investigative journalist Geoff White explains how these hackers have been stealing huge amounts of digital assets from exchanges around the world.
  
- Key Points:
  - The Lazarus Group used phishing to get access to Bitcoin wallet keys, stealing about $75 million.
  - They laundered the stolen crypto using complex methods like peel chains and mixing services, making it tough for investigators to trace.
  - The episode also covers other big heists, including the KuCoin hack ($275 million) and the Ronin Network attack ($625 million).
  - They didn’t just hack, they also used social engineering, like faking job applications to infiltrate companies.

- Lessons Learned:
  - North Korea is getting really good at these big cyber heists, using advanced techniques to steal and launder cryptocurrency.
  - There’s a strong need to beef up defenses against phishing and social engineering, especially for crypto companies.

Idea: Given how the Lazarus Group keeps changing their tactics, what more can cryptocurrency exchanges do to stay safe, and how will the attackers evolve in the future?

## a) Security Hygiene

### Basic Security Practices for Everyone:
- Use strong, unique passwords and a password manager to keep them safe.
- Turn on Two-Factor Authentication (2FA) for extra security.
- Keep your software updated to fix vulnerabilities.
- Be careful with emails – don’t click on suspicious links or attachments.
- Regularly back up your important data securely.
- Secure your home network with a strong router password and WPA3 encryption.

### Security Practices for Companies:
- Segment the network to keep sensitive data safe.
- Train employees regularly on security best practices.
- Run security audits and penetration tests regularly to find and fix weaknesses.
- Have an incident response plan ready and test it regularly.
- Limit user access to just what they need.
- Encrypt sensitive data, whether it’s stored or being sent.
- Monitor network activity to spot any suspicious behavior early.
- Use antivirus, anti-malware, and endpoint security tools on all devices.

Key Takeaway: It’s important to do basic security hygiene before getting into more complex threat modeling. These practices help prevent common attacks and make systems tougher against threats.

## b) Make-Believe Boogie-Man: A Threat Model for EduSecure Company

### Company Overview:
- Company Name: EduSecure Company
- Industry: Tech Education and Traditional Education
- Business Model: EduSecure Company helps universities with on-campus and online learning, focusing on protecting student data, keeping educational services up and running, and securing both physical and virtual infrastructures of the university.

### Threat Model Based on the Four Key Questions:

#### 1. What Are We Working On?
- Key Assets:
  - Student Information System (SIS): Central repository for sensitive student records. This is the crown jewel.
  - Learning Management System (LMS) and Virtual Learning Environment (VLE): Essential for delivering courses and keeping academic activities going.
  - Campus Network: Provides internet access and secures university resources.
  - Access Control Systems: Manages physical security on campus.
  - Online Exams System: Ensures the security of online exams.
  - Cloud-Based Storage: Secures all university data, including teacher-student records and course materials.

- Prioritization:
  - Top Priority: SIS due to its sensitive data.
  - High Priority: LMS and VLE for academic continuity.
  - Medium Priority: Campus Network System for daily operations.
  - Lower Priority: Online Exams data.

#### 2. What Can Go Wrong?
- Examples of Identified Risks:
  - Spoofing: Phishing attacks trick teacher/student into giving up their credentials, leading to unauthorized access – high priority.
  - Tampering: Someone changes student grades or records without permission, leading to academic fraud – high priority.
  - Repudiation: Users deny actions like accessing or changing data – medium priority.
  - Information Disclosure: Someone unauthorized gets access to student records, exposing personal and financial info – high priority.
  - Denial of Service: A DDoS attack might disrupt online classes and exams on the LMS or VLE – medium priority.

- Targeted Threat Actors: Hackers, activists, insiders with bad intentions, and threats specific to the region.
- Business Continuity: It’s important to protect data and keep educational resources available to maintain trust and the university’s reputation.

#### 3. What Are We Going to Do About It?

Risk Mitigation Strategies:
- Reduce Attack Surface: Break up the network into smaller, secure segments.
- Limit Entry Points: Use Multi-Factor Authentication (MFA) to secure logins.
- Mitigate: Encrypt data, keep software up to date, and regularly train everyone on security.
- Eliminate: Get rid of outdated systems that aren’t secure.
- Transfer: Get cyber insurance to cover potential losses from attacks.
- Accept: Allow minor disruptions that won’t affect critical operations.

#### 4. Did We Do a Good Enough Job?

Continuous Evaluation: Regularly check security with audits, penetration testing, and ongoing threat modeling. Always work on improving the incident response plans and keep the threat model current.

## References:
1. Braiterman, E., Baca, M., et al. (2020). Threat Modeling Manifesto: https://www.threatmodelingmanifesto.org/ (Accessed 24 Aug. 2024).
2. Shostack, A. (2022). Welcome to the World’s Shortest Threat Modeling Course. YouTube Playlist: https://www.youtube.com/playlist?list=PLCVhBqLDKoOOZqKt74QI4pbDUnXSQo0nf (Accessed 24 Aug. 2024).
3. OWASP CheatSheets Series Team (2021). Threat Modeling Cheat Sheet: https://cheatsheetseries.owasp.org/cheatsheets/Threat_Modeling_Cheat_Sheet.html (Accessed 24 Aug. 2024).
4. Rhysider, J. (2022). The Lazarus Heist. Darknet Diaries Podcast: https://darknetdiaries.com/episode/119/
5. Academia (2022). IT infrastructure of university based on cloud computing: https://www.academia.edu/78888554/IT_infrastructure_of_university_based_on_cloud_computing (Accessed 24 Aug. 2024)
6. OWASP (2021). OWASP Top 10 Security Practices: https://owasp.org/www-project-top-ten/ (Accessed 24 Aug. 
