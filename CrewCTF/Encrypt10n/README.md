# Encrypt10n
#### Category- Forensics

## Part-1

### Description
 We made a memory dump on the criminal machine after entering the crime scene. Our investigator thought he was using encryption software to hide the secret. can you help me to detect it?
 
 Q1 : crew{password}

 ### Write-Up
 Given this memory dump, we will proceed with **Volatility**. To view the profile, we do `volatility -f dump.raw imageinfo`
 
![Screenshot from 2023-07-11 12-46-31](https://github.com/Ayush-Sl4y3r/CTFs/assets/128846862/f912a614-7ef5-42b4-a785-5a1c527994c1)

Let's check processes list, do 
```volatility -f dump.raw --profile=Win7SP1x86_23418 pslist```

![Screenshot from 2023-07-11 12-49-58](https://github.com/Ayush-Sl4y3r/CTFs/assets/128846862/641e7912-3045-4c40-80e1-3ab508a1e2b7)

Here, we see `TrueCrypt.exe` a interesting process, and also it seems related to challenge name- "Encrypt10n" as well.
In this part, we need to look for password. I did some googling related to TrueCrypt and found some commands in volatility.
Like- `truecryptpassphrase`, `truecryptsummary`, `truecryptmaster` 

I did `volatility -f dump.raw --profile=Win7SP1x86_23418 truecryptsummary` and found this:- ![Screenshot from 2023-07-11 13-26-04](https://github.com/Ayush-Sl4y3r/CTFs/assets/128846862/5d784e2d-e1f2-4fcf-9363-c800e82e743a)


Great, so we got the password here :- `Strooooong_Passwword`
#### Flag is crew{Strooooong_Passwword}

_____

## Part-2

### Description 
Congrats Investigator for finding the first part can you use it to get the secret message?

### Write-Up
Now we have to use the password which we found in part-1 to clear our part-2. But How ??
Again I googled about TrueCrypt software and on wikipedia I got this:-  
![Screenshot from 2023-07-11 13-38-58](https://github.com/Ayush-Sl4y3r/CTFs/assets/128846862/14ec0df1-6fe3-4e4f-a5d3-f17a21a09da6) 

So, I went ahead with `VeraCrypt` and installed it.  
I open the **flag** file provided in the challenge itself and opened with the __password__ 

![Screenshot from 2023-07-11 13-42-19](https://github.com/Ayush-Sl4y3r/CTFs/assets/128846862/ce1a42e5-0ff6-47cf-8a82-3ca6fc38ea4b)


And we got another file encoded multiple times in `base64`. 

After decoding it, we get the flag.

#### Flag is crew{Tru33333_Crypt_w1th_V014t1l1ty!}
