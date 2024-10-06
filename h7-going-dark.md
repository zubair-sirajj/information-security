# h7 Going Dark

## x) Read and Summarize

### Quintin 2014: 7 Things You Should Know About Tor

- **Tor still works**: Despite NSA efforts, Tor remains effective. Most attacks target browser vulnerabilities, not Tor itself. So despite some attacks, Tor remains a strong tool for online anonymity, mainly when used correctly.
- **Not just for criminals**: Journalists, activists, and regular people use Tor for privacy and protection, not just criminals.
- **No military backdoor**: Even though the US Navy funded its development, Tor’s open-source code has been verified to be secure and without backdoors. Experts have confirmed it’s secure.
- **Running a Tor relay is legal in the US**: People in the US can run a relay without legal trouble. However, exit relays may attract law enforcement attention.
- **Easy to use**: Tor is simple to install and use through the Tor Browser Bundle or Tails, making it easy for anyone to get started.
- **Faster than before**: Tor is slower than normal internet browsing but has improved. More relays help make it faster.
- **Not foolproof**: You can still lose your anonymity if you use Tor improperly, so it's important to follow best practices like keeping the software updated.

### Shavers & Bair 2016: Hiding Behind the Keyboard: The Tor Browser €

1. **Introduction**  
   Tor, short for "The Onion Router," is a modified Firefox browser that hides users' IP addresses, allowing anonymous communication. Its simple interface makes it accessible to non-technical users, offering strong anonymity with ease of use.

2. **History and Intended Use of The Onion Router**  
   Originally developed by the U.S. Navy in 2002 for secure communication, Tor is now widely used for anonymous browsing. While intended for legitimate purposes like protecting privacy, it can also be exploited for illicit activities. Tor is open-source and maintained by privacy advocates worldwide.

3. **How The Onion Router Works**  
   Tor routes internet traffic through several encrypted relays, each stripping off a layer of encryption until the final destination is reached. This process is analogous to peeling an onion, hence the name "Onion Router." This multi-step encryption makes it difficult to trace a user's original location or data.

4. **Tracking Criminals Using TOR**  
   Despite Tor's strong anonymity, law enforcement agencies have had some success in tracking criminals by exploiting user errors or browser vulnerabilities, such as in the case of Freedom Hosting. However, breaking Tor itself is extremely challenging without advanced resources, and most cases are solved through human mistakes, like improper use of the tool.

---

## a) Install TOR browser and access TOR network 
I began the process by installing the TOR browser on my Debian system via the terminal. Here’s the detailed process:

- **Extracting the File**:  
   I navigated to the `Downloads` folder where I had the TOR browser `.tar.xz` file and ran the following command:  
   `tar -xvJf tor-browser-linux-x86_64-13.5.6.tar.xz`  
This successfully extracted the contents into a folder named tor-browser_en-US.

- **Navigating to the Extracted Folder:**  
I moved into the newly created folder:   
`cd tor-browser_en-US/  `  
- **Running the TOR Browser:**  
I launched the TOR browser by executing:  
`./start-tor-browser.desktop`  

## b) Browse TOR network  

### Onion search engines
I used Ahmia to explore different .onion sites. It’s a search engine built for TOR and focuses entirely on indexing onion sites. I found various categories of sites using it. I searched for some meme and also some legal tor sites.  

![1](https://github.com/user-attachments/assets/413ea3b4-6697-4e4e-a368-1a54013fb2c2)  
![2](https://github.com/user-attachments/assets/f82dde37-5f16-416b-82a9-9241fce8cc36)  
![3](https://github.com/user-attachments/assets/7c0c1a87-1c25-41ca-9f47-92fc1101fd91)  
![4](https://github.com/user-attachments/assets/f0e552f5-f67b-4ddd-b11c-5428c3204787)    

Comment: Ahmia was easy to use and made finding onion sites simple. It sticks to safe and legitimate content, which was perfect for my needs.

### Visiting a Marketplace
Through Ahmia, I came across Black Ops Market. It seemed to deal with digital services but had some questionable listings.   
![5](https://github.com/user-attachments/assets/31ff5d51-dcf8-44c3-bee8-c408cc5427cc)  
![6](https://github.com/user-attachments/assets/90199c4a-d8db-496b-b8b0-7b1aa108cb65)    

Comment: Marketplaces on TOR show both sides—some legal, some not. The anonymity on TOR makes it a space for all kinds of commerce, so it's important to be cautious.

### Exploring a Forum
I checked out Dread, which is a popular forum on TOR. It's like Reddit but focuses a lot on privacy and security. People discuss topics like encryption, staying anonymous online, and related tech.  

![7](https://github.com/user-attachments/assets/d2610210-ace3-495e-a3fe-6ab9ecd7100d)   
![8](https://github.com/user-attachments/assets/9af5fabc-ec0c-49de-9d3d-170e4aeb2944)  

Comment: Dread is a good place to learn about privacy and tech-related issues on TOR, and it provides a space for free, anonymous exchange of ideas.

### Accessing a Well-Known Organization’s Site  
After several attempts to load different .onion sites, I successfully accessed the BBC’s TOR mirror, which provides access to its news platform. The BBC offers this mirror to ensure that users in countries with restricted internet access can still access unbiased news.  

The onion URL I used to access the site was: http://deepweb4epga7mkmlku53op47jinc3mzwudmruixr6gvra3xqqnlhwad.onion/catalog/bbcnewsd73hkzno2ini43t4gblxvycyac5aw4gnv7t2rccijh7745uqd.onion  

![9](https://github.com/user-attachments/assets/a1d5b9e6-2fe6-4109-9cf2-4bf2029cd0dc)  

BBC’s Physical Address: Broadcasting House, Portland Place, London W1A 1AA, United Kingdom  

Comment: The BBC’s TOR mirror is a great example of how legitimate organizations use TOR to provide free access to information in regions where traditional internet access is limited or censored. It highlights the positive use of TOR for journalism and information sharing.


## References

- Karvinen, T. (2024). Information Security: Course ICI002AS2AE-3005 - Early Autumn 2024. Available at: https://terokarvinen.com/information-security/ (Accessed 5 Oct, 2024).

- Quintin, C. (2014). 7 Things You Should Know About TOR. Available at: https://www.eff.org/deeplinks/2014/07/7-things-you-should-know-about-tor (Accessed 5 Oct, 2024).

- Shavers, R. & Bair, A. (2016). Hiding Behind the Keyboard: The Tor Browser. Available at: https://www.oreilly.com/library/view/hiding-behind-the/9780128033524/XHTML/B9780128033401000021/B9780128033401000021.xhtml#s0010 (Accessed 5 Oct, 2024).
