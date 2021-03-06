# PwnedPasswordsChecker

### DISCLAIMER: 
**Running this script and actually using your own passwords results in these commands you're using (and your passwords) ending up in a history/log on your computer in plaintext, which is not great.**

**Use at your own risk, I don't necessarily recommend using this to check your own passwords, it's just a fun tool. Thanks to CK in the comments of the video linked below for pointing this out.**

---

## About

This project is a small Python script that uses the Have I Been Pwned API for safely checking whether a password has been pwned, without sharing it, or its hash. Instead, it sends the first 5 characters of the hash and the API sends back all hashes that start that way. This script then checks whether your hash is in the response.

In the [Computerphile video "Have You Been Pwned?"](https://www.youtube.com/watch?v=hhUb5iknVJs), Dr Mike Pound uses a script exactly like this one to check how many times certain passwords had leaked in a safe manner. He didn't release the source code (as I'm writing this) and many people wanted the script, so I made a quick implementation. The video: 

---

## Usage

* Use Python 3
* Before running the script, download the requests Python module by going into CMD and typing `pip install requests`
* Use the script by calling it either
    * with a file containing your password `python pwned.py -F password_file.txt`
    * or (not recommended) with your password in plaintext `python pwned.py -P password123` ('password123' being the password)

```console
python .\pwned.py -h
usage: pwned.py [-h] (-F FILE | -P PASSWORD)

optional arguments:
  -h, --help            show this help message and exit
  -F FILE, --file FILE  file to read password from (only the first line is read)
  -P PASSWORD, --password PASSWORD
                        provide password in plaintext (CAUTION: may appear in logs!)
```

    
