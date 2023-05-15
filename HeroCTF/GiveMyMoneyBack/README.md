# GiveMyMoneyBack

### Category  
Reverse
#### Flag format
The flag corresponds to the email used for the exfiltration and the name of the last exfiltrated file, e.g. Hero{attacker@evil.com|passwords.txt}.

#### Write-up:- 
In this challenge, we are given a zipped file [GiveMyMoneyBack.zip](https://ctf.heroctf.fr/files/5648cb6528b0fa3ad3040b2fbcf8f580/GiveMyMoneyBack.zip?token=eyJ1c2VyX2lkIjoxMDkxLCJ0ZWFtX2lkIjo1NDUsImZpbGVfaWQiOjEwN30.ZGKYhA.OcNM3Y-aCsQydlFEn1LpwuZVciM)
Unzipping it, we get two files `description.txt` & `image.png.vbs`. 

While opening `image.png.vbs`, there is some obsfucated script written. Opening it in `sublime-text`,![Screenshot from 2023-05-16 03-13-41](https://github.com/Ayush-Sl4y3r/CTFs/assets/128846862/431f8754-681f-4e46-baac-c285e421283b)
We can replace complex variable names with simpler ones to make it more readable. Now we get, ![Screenshot from 2023-05-16 03-18-49](https://github.com/Ayush-Sl4y3r/CTFs/assets/128846862/f7074ed8-7a0d-48d5-a6bc-2b78bc124803)
Hence, we can easily understand the script.. string stored in `var_1` is to be split at `*` (from line 4) and then they are converted to char and concatenated. After this, we get-![Screenshot from 2023-05-16 03-31-14](https://github.com/Ayush-Sl4y3r/CTFs/assets/128846862/7f8a2db5-280e-4412-a6b4-e5bd83a04434)

So, we've got emailID -> `bmwqia84@mail.ru` & file name ->`default_wallet`. This is what we needed for our flag :)

#### Hero{bmwqia84@mail.ru|default_wallet}
###### Link to read about VBScript:- https://en.wikipedia.org/wiki/VBScript                              
###### https://infosecwriteups.com/fun-with-vbscript-malware-2f5bb0d107df

