### Golden-Eye-CTF <br>
**Hi, We will solve 'Golden Eye' game. If you download this machine, you can click here --> https://www.vulnhub.com/entry/goldeneye-1,240/**<br>
__________________________________________________________________________________________________________________ <br><br>
1) I downloaded golden eye machine and installed. I connected it to the same network as my kali machine. And I ran both of them. <br><br>
2) I write some nmap command because we don't know golden eye's ip. <br><br>
`nmap 192.168.1.0/24`<br><br>
3) Now we know which ip is true. In that case, we should find open ports. Open ports is here --> <br> 
   ![Screenshot](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/scan%20for%20ports.png)<br><br>
4) We need number for pop3. For this, you can do it with this command --> <br>
   ![pop3](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/pop3.png) <br><br>
5) We have pop3 and web site. First, we can visit this web site. If you write golden eye's ip at the firefox search bar, you can visit golden eye web site. <br> ![web site](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/web%20site.png) <br><br>
6) Ok. We will login from /sev-home/ page. But we need any user name and password. Let's we look source.<br> ![source](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/source.png) <br><br>
7) if we look carefully, this page have some 'script' to terminal.js. Let's look at this. I write (golden_eye_ip/terminal.js) to search bar. ![terminal](
https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/terminal.png) <br><br>
8) We should search carefully. We have some words.. Boris, Natalya and a random stuff. Maybe Natalya and Boris could be username. And this random think .. Actually it isn't random think, it's a chipher text. Let's we solve it. We can use 'BurpSuite's decode bar. I paste this text and decode it. As a result, I get 'InvincibleHack3r'.<br> ![burp ssuite](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/burp%20suite.png) <br><br>
9) Everything is done. Now, let's visit /sev-home/ page. We found this page name. I write search bar again. The login screen comes up. I try for boris and InvincibleHack3r. It's try.<br> ![sev-home](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/sev-home.png)<br><br>
   ![page](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/page.png)<br><br>
10) I think it's not help me enought. So I chack source part. <br> ![source2](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/source2.png)<br> It's look like ok. Let's look for pop3.<br><br>
11) First we need pop3 password. So we need wordlist. My Linux have fasttrack wordlist, I use this one. If you don't know where this file, you write `locate fasttrack.txt` to terminal. My file with /usr/share/wordlists. I going to this file in my terminal. And we can use hydra with boris username. <br><br> ![wordlist termaina](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/wordlist%20terminal.png)<br><br>Result for Bors username ...<br><br>
![boris result](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/boris%20result.png)<br><br><br>
12) We try again it for Natalya username <br> ![natalya result](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/natalya%20result.png) <br><br>
13) Now we know usernames and passwords. Let's run this pop3. We must write this line to terminal. <br> `nc (golden eye's ip') 5507` <br><br> First, I use this command for Boris.<br><br> ![Boris nc](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/boris%20nc.png) <br> ![boris nc 2](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/boris%20nc%202.png) <br><br> We can read  messages. But they doesn't help too much. So I try for Natalya. <br><br>
14) ![Natalya nc](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/natalya%20nc.png) <br><br> Did you see? We have new username and password. But I should to edit for host. For this, I'm going to etc file and write `nano hosts` to terminal. After that, should add line for golden eye like this --> <br><br> ![host line](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/host.png)<br><br><br> And Let's write web-site addres to search bar.<br><br><br>
15) ![pop3](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/pop3%20web%20site.png) <br> I login for Xenia.<br> ![xenia](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/xeania.png)<br><br> We're inside. <br><br><br>
16) I searched around a little bit. And I founded this.<br> ![dr. doak](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/dr%20doak.png)<br> I think we can found dr. doak's password. For this, I use hydra like before.<br><br> ![dr.doak password](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/dr%20doak%20password.png) <br><br><br>
17) According to hydra result, goat is true password.<br> ![dr doak result](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/dr%20doak%20hydra%20password.png) <br><br> Firstly, we can look messages.<br><br> ![dr doak messages](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/dr%20doak%20messages.png) <br><br> We found password. Now we can login to page. <br><br><br>
18) ![dr doak page](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/dr%20doak%20page.png) <br><br> Again, I searched around and I found this file.. <br><br> ![file](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/file.png) <br><br> ![secret file](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/file%202.png) <br><br> ![file inside](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/file%20inside.png) <br><br> We have a picture. I download it from search bar.<br><br> ![picture](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/picture.png) <br><br> Let's look at the features. <br><br> ![features](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/picture%202.png) <br><br> Yes, Again golden eye gave cipher text to us. I decode it at burp suite. <br><br> ![burp suite 2](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/burp%20suite%202.png) <br><br><br> We , just don't have the admin's pass, do we? I checked. And yes, it's working.<br> ![admin page](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/admin%20login.png) <br><br><br>
19) Admin page checked for spell at path to aspell section. <br> And I changed something about this. Do you know reverse shell ? I give python code fir this. <br><br> ![reverse shell](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/reverse%20shell.png) I pasted this line to path to aspell section. <br><br> ![path to aspell](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/aspell.png) <br><br> Don't forget change ip address. we must write our Linux ip. <br><br><br> After that, we should change one more thing to spell engine. We should to arrange it from PSpellShell. <br><br> ![PSpellShell](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/spell%20shell.png) <br><br><br>
20) Now, we can listen this page. <br><br> ![listen](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/listen.png)<br><br><br>
21) For binding, I write random message at admin account and check it. <br><br> ![check](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/check.png) <br><br> When we press to abc spell button, connection start.  <br><br><br> ![connection start](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/connection.png) <br><br><br>
22) For information about machine, I write uname -a command to terminal.<br> ![uname -a](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/uname%20-a.png) <br><br><br>
23) We must be root. So I search any exploit for this ubuntu machine and I dowload exploit file according to search result. <br><br> ![exploit searching](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/exploit%20searching.png) <br><br><br>
24) My exploit file wrote with c programming. I must use gcc but I can't. So I arranged this file for cc. After that we can run exploit file. <br><br> ![cc](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/cc.png) <br><br> ![cc run](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/run%20cc.png) <br><br><br>
25) It seems to be working. Let's check it. <br><br> ![root](https://github.com/SeymaAtmaca/Golden-Eye---CTF-/blob/main/golden%20eye%20-%20pictures/root.png) <br><br><br>
 ______________________________________________________________________________
 <br><br>
 <i><h3> Yess, finish. We're root. </h3></i>
 <br><br><br>











