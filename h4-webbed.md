# h4 Webbed
## x) Read and Summarize 
## OWASP: OWASP 10 2021
The Open Web Application Security Project (OWASP) Top 10 list is an essential framework for understanding the most critical security risks to web applications. Developers and security teams can significantly mitigate potential threats by addressing these vulnerabilities. 

### A01:2021 – Broken Access Control
This category has climbed up in priority from fifth to first, reflecting its increased prevalence in security breaches where improper access control mechanisms allow attackers to bypass authorization safeguards. Often, broken access control allows unauthorized users to access admin panels or APIs that should require higher privilege levels.

**Common Vulnerabilities**:
  - Elevation of privilege.
  - Users access data or perform actions outside of their permissions.
    
  **Strategies for Prevention**:
  - Enforce access controls in server-side logic.
  - Adopt a default-deny framework that only permits access to authorized functionalities.
  - Implement multi-factor authentication to minimize the risk of unauthorized access.

### A05:2021 – Security Misconfiguration
This risk stems from improper system configurations, often leading to unnecessary data exposure. This has also moved from the sixth position to the fifth. Misconfigurations such as leaving default settings unchanged or enabling unnecessary features and services can expose systems to attackers, as seen in numerous incidents where databases were left unprotected and publicly accessible on the internet.

**Typical Misconfigurations**:
  - Unprotected files and directories.
  - Default accounts with unchanged passwords.
  - Outdated software.
    
**Preventive Measures**:
  - Regular audits of security configurations and settings.
  - Removal of unused features, frameworks, accounts, and privileges.
  - Continuous updates and patches applied to all software components.

### A06:2021 – Vulnerable and Outdated Components
It was second in the Top 10 community survey/ Utilizing components with known vulnerabilities is a prevalent issue that often leads to severe data breaches or system takeovers. Using outdated libraries or frameworks can expose applications to vulnerabilities that attackers actively exploit, such as when the Heartbleed bug in OpenSSL allowed attackers to read sensitive information from memory on servers running the vulnerable version.

**Implications**: 
- Attacks facilitated by exploiting flaws in third-party components.
  
**Solutions**:
  - Maintain an up-to-date inventory of all components and their versions.
  - Use tools to continuously monitor for vulnerabilities within these components.
  - Obtain all components from reliable sources and keep them up-to-date.

### A03:2021 – Injection
Injection flaws occur when untrusted data is sent to an interpreter as part of a command or query. SQL injection remains one of the most prevalent methods of attack, where attackers input malicious SQL statements into forms or via URL parameters to manipulate database queries and gain unauthorized access to data.

**Types of Vulnerabilities**:
  - SQL injection.
  - NoSQL Injection.
  - Command injection.
  - LDAP injection.
    
**Defensive Strategies**:
  - Use of prepared statements (with parameterized queries) in SQL and NoSQL calls.
  - Escaping special characters using the specific escape syntax for that interpreter.
  - Implementing positive or "allowlist" input validation.

Addressing these vulnerabilities through understanding and implementing best practices is essential for protecting against the dynamic threats in the digital landscape.

## a) Goat. Install WebGoat 2023.4

- **Java Installation**: Ensured the Java Runtime Environment was up to date to support running WebGoat, with specific steps to install OpenJDK 17 on Debian-based systems.

- **Downloading WebGoat**: Acquired the latest version of WebGoat by downloading the JAR file from GitHub using `wget`.

- **Launching WebGoat**: Configured and initiated WebGoat on alternative ports to avoid conflicts with other services and to ensure accessibility.

- **Accessing the Application**: Opened WebGoat in a web browser using the specified address to begin the security training sessions.
![Screenshot_2024-09-12_21-46-49](https://github.com/user-attachments/assets/5b6e54ad-a95d-4614-9547-5c8abcd59003)

## b) F12. Solve WebGoat 2023.4: General: Developer Tools:

### Try It! Using the Console
Successfully executed the JavaScript function `webgoat.customjs.phoneHome()` using the console in the developer tools. Captured and pasted the randomly generated number as required. The response confirmed the lesson completion.
![Screenshot_2024-09-14_20-44-06](https://github.com/user-attachments/assets/36778bca-72b8-429e-9115-22f6308a676c)

### Try It! Working with the Network Tab
Identified and selected the correct HTTP request generated in the lesson, which contained a `networkNum` field. Extracted the randomized number from this field, entered it into the provided input field, and received confirmation of correctness.
![Screenshot_2024-09-14_20-50-11](https://github.com/user-attachments/assets/dab1dba8-5897-4166-b2c5-a90376d1ea4a)


## c) Not outdated:
I have updated the operating system and all applications.

## d) Sequel. Solve SQLZoo:
### 0 SELECT basics
Completed the initial exercises on SQLZoo under "SELECT basics." 
![Screenshot (253)](https://github.com/user-attachments/assets/44c401c0-099a-44ef-ab49-4b32dadb3596)

### 2 SELECT from World
Progressed to the new one and completed "SELECT from World" as well.
![Screenshot (254)](https://github.com/user-attachments/assets/6d5232ae-f017-411d-805e-11be617590e4)

## e) Johnny tables. Solve Portswigger Labs:



## References:
- Information Security: Course ICI002AS2AE-3005 - Early Autumn 2024: (https://terokarvinen.com/information-security/) (Accessed 12 Sep, 2024).
- OWASP (2021). A01:2021 – Broken Access Control: (https://owasp.org/Top10/A01_2021-Broken_Access_Control/) (Accessed 12 Sep, 2024).
- OWASP (2021). A05:2021 – Security Misconfiguration: (https://owasp.org/Top10/A05_2021-Security_Misconfiguration/) (Accessed 12 Sep, 2024).
- OWASP (2021). A06:2021 – Vulnerable and Outdated Components: (https://owasp.org/Top10/A06_2021-Vulnerable_and_Outdated_Components/) (Accessed 12 Sep, 2024).
- OWASP (2021). A03:2021 – Injection: (https://owasp.org/Top10/A03_2021-Injection/) (Accessed 12 Sep, 2024).
- SQLZoo. "SQL Tutorial." Available at: [SQLZoo SQL Tutorial](https://sqlzoo.net/wiki/SQL_Tutorial). (Accessed on 14 Sep, 2024).
- Portswigger. "SQL Injection Lab: Retrieve Hidden Data." Available at: [Portswigger SQL Injection Lab](https://portswigger.net/web-security/sql-injection/lab-retrieve-hidden-data). (Accessed on 14 Sep, 2024). 
