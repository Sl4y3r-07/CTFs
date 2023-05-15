# PDF-mess
### Category 
Steganography

### Description
This file seems to be a simple copy and paste from wikipedia. It would be necessary to dig a little deeper...

Good luck!
### Write-up :- 
In this challenge, we are given a file [strange.pdf](https://ctf.heroctf.fr/files/83c1e6fec93fe625adacc115f0c50d6e/strange.pdf?token=eyJ1c2VyX2lkIjoxMDkxLCJ0ZWFtX2lkIjo1NDUsImZpbGVfaWQiOjg5fQ.ZGJwJw.FzE_z7d-vg_skA0tLmfYc8nIM-0). On opening this file, we find no hint so that we can reach to our flag. 
I parsed this pdf using an online tool. 
After unzipping the downloaded file, I tried looking for suspicious elements and in few searches, I found script in which there was a cipher encrypted by AES algorithm along with its key...decrypted it and got the flag.

#### Hero{M4L1C10U5_C0D3_1N_PDF}

###### Link to read about PDF-structure:- https://resources.infosecinstitute.com/topic/pdf-file-format-basic-structure/
