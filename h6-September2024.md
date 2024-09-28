# h6 September 2024!

## x) Read and Summarize
### Schneier 2015: Applied Cryptography: Sections 2.3 One-Way Functions and 2.4 One-Way Hash Functions

#### 2.3 One-Way Functions
- **Definition:** A one-way function is easy to compute in one direction (find f(x) from x) but extremely difficult to reverse (find x from f(x)).
- **Analogy:** Schneier compares this to breaking a plate—easy to smash, nearly impossible to piece back together.
- **Existence:** No formal proof that one-way functions exist, but many functions behave as if they are one-way (e.g., squaring is easy, but taking square roots is harder in certain cases).
- **Trapdoor One-Way Functions:** These are one-way functions with a "trapdoor" or secret information that allows easy reversal.
  - Example: Taking apart a watch—hard to reassemble without instructions (trapdoor), but easy with them.
  - Used extensively in public-key cryptography to allow secure communication.

#### 2.4 One-Way Hash Functions
- **Definition:** A one-way hash function takes an input (pre-image) and produces a fixed-length output (hash), making it easy to compute the hash but hard to reverse.
- **Collision Resistance:** It’s difficult to find two different inputs that produce the same hash.
- **Use Case:** Verifying file integrity or message authenticity by comparing hash values.
  - Even a small change in the input will drastically alter the hash output, making it easy to detect tampering.
- **Message Authentication Codes (MACs):** Combines hash functions with a secret key.
  - Ensures that only someone with the key can verify the integrity of a message.
  - Provides an extra layer of security to prevent unauthorized tampering.

---

## a) Install Hashcat
### Step-by-step process:

#### Install Hashcat:
First, I updated the package list and installed Hashcat along with the necessary tools.  

`$ sudo apt-get update  `

`$ sudo apt-get -y install hashid hashcat wget  `
![Screenshot_2024-09-28_04-53-13](https://github.com/user-attachments/assets/b23c8fd5-41a8-44a7-9d78-e6fbafba7ba9)

#### Create a working directory:
I then created a new directory to keep the files organized and moved into it.  

`$ mkdir hashed  `  

`$ cd hashed  `  
![Screenshot_2024-09-28_04-56-28](https://github.com/user-attachments/assets/80676dcd-a22f-4284-aed9-11084616dbe6)

#### Download a dictionary:
Next, I downloaded a popular password dictionary (RockYou) and extracted it for use in cracking the hash.  


`$ wget https://github.com/danielmiessler/SecLists/raw/master/Passwords/Leaked-Databases/rockyou.txt.tar.gz`  

`$ tar xf rockyou.txt.tar.gz`  

`$ rm rockyou.txt.tar.gz`  
![Screenshot_2024-09-28_04-57-29](https://github.com/user-attachments/assets/9f5754d8-dfa3-4982-9639-0c78f3ca3837)


## b) Crack this hash: d595b2086532422bbe654bc07ea030df
### Step-by-step process:  
#### Identify the hash type:
Before cracking the hash, I used hashid to identify the type of the hash. This is important to choose the correct mode for Hashcat.

`$ hashid -m d595b2086532422bbe654bc07ea030df ` 
![Screenshot_2024-09-28_05-15-42](https://github.com/user-attachments/assets/75313967-a15a-45b5-9447-a09385ea7fb7)

#### Run Hashcat to crack the hash:
After identifying the hash type as MD5, I ran Hashcat to crack the provided hash using the RockYou wordlist.

`$ hashcat -m 0 'd595b2086532422bbe654bc07ea030df' rockyou.txt -o solved`  

#### Check the result:
Once Hashcat finished running, I checked the "solved" file to see the cracked password.  

`$ cat solved  `  

The hash was successfully cracked, and the password is `d595b2086532422bbe654bc07ea030df:disobey`  

#### Verify the cracking process:
To ensure the process worked, I could also use the --show option to display the cracked hash directly in the terminal.   
`$ hashcat -m 0 d595b2086532422bbe654bc07ea030df rockyou.txt --show`  

`d595b2086532422bbe654bc07ea030df:disobey`  
![Screenshot_2024-09-28_05-16-38](https://github.com/user-attachments/assets/f39a9fb3-74cd-4488-afd5-dc044efd7f34)

## References

- Karvinen, T. (2024). *Information Security: Course ICI002AS2AE-3005 - Early Autumn 2024*. Available at: [https://terokarvinen.com/information-security/](https://terokarvinen.com/information-security/) (Accessed 12 Sep, 2024).
- Schneier, B. (2015). *Applied Cryptography: Protocols, Algorithms, and Source Code in C (2nd ed.)*. Wiley. Available at: [https://learning.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/10_chap02.html#chap02-sec003](https://learning.oreilly.com/library/view/applied-cryptography-protocols/9781119096726/10_chap02.html#chap02-sec003) (Accessed 12 Sep, 2024).
- Karvinen, T. (2022). *Cracking Passwords with Hashcat*. Available at: [https://terokarvinen.com/2022/cracking-passwords-with-hashcat/](https://terokarvinen.com/2022/cracking-passwords-with-hashcat/) (Accessed 12 Sep, 2024).

