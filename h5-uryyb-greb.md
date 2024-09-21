# h5 Uryyb, Greb!

## x) Read and summarize

### € Schneier 2015: Applied Cryptography: Chapter 1: Foundations

In Chapter 1 of Schneier’s "Applied Cryptography", we get an introduction to the key concepts and terms used in cryptography. Here's a breakdown of what I learned:

- **Encryption and Decryption**:
  - Encryption turns a readable message (plaintext) into an unreadable format (ciphertext) to keep it secure.
  - Decryption reverses this process. This is the core of cryptography—making sure information stays confidential.

- **Cryptography vs. Cryptanalysis**:
  - Cryptography is about creating systems to protect data.
  - Cryptanalysis focuses on breaking those systems. Together, these make up the field of cryptology.

- **Symmetric vs. Public-Key Algorithms**:
  - Symmetric encryption uses the same key for both encryption and decryption (like in DES), which means both parties need to securely share the key.
  - Public-key encryption (used in RSA) has two different keys: a public one for encryption and a private one for decryption, which allows for secure communication without having to share the private key.

- **Other Roles of Cryptography**:
  - **Authentication**: Verifying who sent the message.
  - **Integrity**: Ensuring the message hasn’t been altered.
  - **Nonrepudiation**: Making sure the sender can’t deny they sent the message.

- **Types of Cryptanalytic Attacks**:
  - **Ciphertext-only attack**: The attacker only has access to the encrypted message.
  - **Known-plaintext attack**: The attacker has both the plaintext and its corresponding ciphertext.
  - **Chosen-plaintext attack**: The attacker can choose specific plaintexts to be encrypted to gather more information about the key.

The chapter emphasizes that the security of an encryption system should depend on the strength of the key, not on keeping the algorithm a secret.

- **Historical Ciphers**:
  - Before computers, people used substitution ciphers (replacing each letter with another) and transposition ciphers (shuffling the order of letters). These are the foundations of modern cryptography, which now works on bits instead of letters.

- **Steganography**:
  - This is the practice of hiding the fact that a message exists by embedding it in something else, like an image. It’s different from encryption, where the goal is to hide the content of the message.

- **One-Time Pad**:
  - This is a perfect encryption method, but it’s impractical for everyday use. The key must be as long as the message and can only be used once. While it’s unbreakable, managing the keys is the hard part.

- **Modern Algorithms**:
  - **DES** is a popular symmetric encryption algorithm.
  - **RSA** is widely used for public-key encryption and digital signatures.
  - **DSA** is another public-key algorithm, used for digital signatures but not encryption.


### Karvinen 2023: PGP - Send Encrypted and Signed Message - gpg

GNU privacy guard, 'gpg', is a popular way to encrypt and sign. In this article, we get to know how to use PGP encryption with the `gpg` tool to send secure, encrypted messages over the untrusted Internet.

The example uses two simulated users—Alice and Tero—to demonstrate PGP in action. Here’s how the process works:

- **Setting Up Trust**: The first step is to generate a keypair for each user, consisting of a public key (which can be shared) and a private key (which is kept secret). Alice needs Tero’s public key to send him an encrypted message, and Tero needs Alice’s public key to verify her signature. This key exchange only needs to happen once to establish trust.

- **Generating Keys**: Both Alice and Tero generate their keypairs using `gpg --gen-key`. Tero exports his public key so Alice can use it, and Alice does the same so that Tero can verify her messages.

- **Encrypting and Signing**: Once the keys are exchanged, Alice writes a message to Tero, encrypts it using Tero’s public key, and signs it with her private key with a command. The command ensures the message is encrypted for Tero’s eyes only and verifies that Alice sent it.

- **Decrypting and Verifying**: When Tero receives the encrypted message, he decrypts it using his private key. He also verifies Alice’s signature using her public key, confirming that the message was not altered and really came from her.

- **Trust Over Untrusted Channels**: One of the main points highlighted in the article is that public key encryption allows Alice and Tero to exchange messages securely, even over untrusted channels (like the Internet). The public keys can be sent over insecure networks, but as long as they verify the keys, the communication remains secure.

---

## a) Pretty Good indeed. Encrypt and decrypt a message with 'gnupg', using PGP public key cryptography.

To complete this part of the assignment, I successfully installed **GnuPG** and followed the steps for generating a keypair, encrypting, and decrypting a message.

1. **Installed gnupg**:  
   I ensured that **GnuPG** was installed on my system by running:
   
  `sudo apt-get update`
  `sudo apt-get install gnupg`
![Screenshot_2024-09-22_00-26-50](https://github.com/user-attachments/assets/93a6e9f6-04e5-4233-ab7b-28dd4e73a28b)

2. **Generated a Keypair:**
Using the command below, I generated my PGP keypair:

`gpg --full-generate-key`  

3. **Exported My Public Key:**  
After generating the keypair, I exported my public key to a file for sharing with others:  

`gpg --export --armor --output mypublickey.asc fmzubair.siraj@gmail.com`
![Screenshot_2024-09-22_00-36-12](https://github.com/user-attachments/assets/e01df428-d445-4559-80d8-0710a0a22a43)

4. **Encrypted a Message:**
I created a simple text message:  
`echo "Secret Message!" > message.txt`  

Then, I encrypted the message using my public key:  
`gpg --encrypt --recipient fmzubair.siraj@gmail.com --armor message.txt`

This produced the encrypted file message.txt.asc.

5. **Decrypted the Message:**
To test the decryption process, I used the following command to decrypt the encrypted message:  

`gpg --decrypt message.txt.asc`  

I successfully decrypted the message, confirming that the encryption and decryption process worked.

6. **Exported My Private Key:**
For backup purposes, I exported my private key and saved it securely:

`gpg --export-secret-keys --armor --output myprivatekey.asc fmzubair.siraj@gmail.com`  

I selected RSA and RSA for the key type, set the key size to 4096 bits, and provided my name and email address for identification.  
![Screenshot_2024-09-22_00-08-58](https://github.com/user-attachments/assets/c9db1fa8-ff21-4fff-b106-c58f87e72b61)

This completed the task of encrypting and decrypting a message using PGP public key cryptography with gnupg.



---
## b) Password manager, open and cloudless

For this part of the assignment, I needed to choose a password manager that is:
- Cloudless (does not store data on the cloud).
- Open-source (the code is publicly available and can be verified by anyone).
- Free.

After considering various options, I decided to go with KeePassXC. It is a well-known, open-source password manager that stores passwords locally in an encrypted database, ensuring no data is ever stored in the cloud. This meets all the assignment’s criteria perfectly.

### Step 1: Installing KeePassXC
I started by downloading KeePassXC from the official website. After downloading the Windows installer, I ran the installation and followed the simple setup process. The tool was installed and ready for use within minutes.

### Step 2: Setting Up the Database
Once KeePassXC was installed, I created a new password database by selecting the "Create New Database" option. I chose a secure location on my local machine to store the database file and then set a master password to protect it. The master password is the only password I need to remember, and it encrypts all other passwords stored in the database.

### Step 3: Storing Passwords
I added a few test entries by selecting “New Entry” and entering the following information:
- **Title** (the name of the website or service).
- **Username**.
- **Password** (I used KeePassXC’s built-in generator to create strong, random passwords).
- **Notes** (optional, for additional details like URLs).

This process was simple and allowed me to organize my passwords securely.

### Step 4: Using KeePassXC
Whenever I need to log in to a website or service, I simply open KeePassXC, search for the entry, and copy the password to paste into the login form. KeePassXC stores all my passwords locally in an encrypted database, meaning there’s no reliance on the cloud for password management, ensuring full control over my data.

### Why a Password Manager is Needed
A password manager like KeePassXC helps protect against:
- **Brute force attacks**: It generates and stores strong, unique passwords for each account.
- **Phishing attacks**: It ensures I use the correct password for the correct site, minimizing the risk of entering my credentials on fake sites.
- **Credential stuffing**: Since each account has a unique password, even if one account is compromised, others remain safe.

KeePassXC provides the perfect solution for securely storing my passwords offline, meeting all the requirements of the assignment for being cloudless, free, and open-source.

## References:

- Schneier, B. (2015). Applied Cryptography: Chapter 1: Foundations. Available at: (https://learning.oreilly.com/library/view/applied-cryptography-protocols/9780471117094/09_chapter01.html#ch1-sec020) (Accessed 18 Sep, 2024).
- Karvinen, T. (2023). PGP - Send Encrypted and Signed Message - gpg. Available at: (https://terokarvinen.com/2023/pgp-encrypt-sign-verify/) (Accessed 18 Sep, 2024).
- KeePassXC. (2024). KeePassXC - Cross-Platform Password Manager. Available at: (https://keepassxc.org/download/) (Accessed 18 Sep, 2024).
