### Golden-Eye-CTF <br>
**Hi, We will solve 'Golden Eye' game. If you download this machine, you can click here --> https://www.vulnhub.com/entry/goldeneye-1,240/**<br>
__________________________________________________________________________________________________________________ <br><br>
1) I downloaded golden eye machine and installed. I connected it to the same network as my kali machine. And I ran both of them. <br>
2) I write some nmap command because we don't know golden eye's ip. <br>
`nmap 192.168.1.0/24`<br><br>
3) Now we know which ip is true. In that case, we should find open ports. Open ports is here --> <br> 
   ![Screenshot](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/scan%20for%20ports.png)<br><br>
4) We need number for pop3. For this, you can do it with this command --> <br>
   ![pop3](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/pop3.png) <br><br>
5) We have pop3 and web site. First, we can visit this web site. If you write golden eye's ip at the firefox search bar, you can visit golden eye web site. <br> ![web site](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/web%20site.png) <br><br>
6) Ok. We will login from /sev-home/ page. But we need any user name and password. Let's we look source. ![source](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/source.png) <br><br>
7) if we look carefully, this page have some 'script' to terminal.js. Let's look at this. I write (golden_eye_ip/terminal.js) to search bar. ![terminal](
https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/terminal.png) <br><br>
8) We should search carefully. We have some words.. Boris, Natalya and a random stuff. Maybe Natalya and Boris could be username. And this random think .. Actually it isn't random think, it's a chipher text. Let's we solve it. We can use 'BurpSuite's decode bar. I paste this text and decode it. As a result, I get 'InvincibleHack3r'. ![burp ssuite](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/burp%20suite.png) <br><br>
9) Everything is done. Now, let's visit /sev-home/ page. We found this page name. I write search bar again. The login screen comes up. I try for boris and InvincibleHack3r. It's try. ![sev-home](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/sev-home.png)
   ![page](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/page.png)<br><br>
10) I think it's not help me enought. So I chack source part. <br> ![source2](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/source2.png)<br> It's look like ok. Let's look for pop3.<br><br>
11) First we need pop3 password. So we need wordlist. My Linux have fasttrack wordlist, I use this one. If you don't know where this file, you write `locate fasttrack.txt` to terminal. My file with /usr/share/wordlists. I going to this file in my terminal. And we can use hydra with boris username. <br><br> ![wordlist termaina](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/wordlist%20terminal.png)<br>Result for Bors username ...
![boris result](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/boris%20result.png)<br><br><br>
12) We try again it for Natalya username <br> ![natalya result](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/natalya%20result.png) <br><br>
