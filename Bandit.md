Host : bandit.labs.overthewire.org
Port : 2220
`ssh USER@bandit.labs.overthewire.org -p 2220`
### lvl 0
`cat, more, less, head, tail readme`
Pass : ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
### lvl 1
```
cat ./-
cat ./*
cat < -
more -
tr -d '' < -
echo $(<-)
rev - | rev
find . -name "-" -exec cat {} \;
find . -inum 557295 -exec cat {} \;
```
Pass : 263JGJPfgU6LtdEvgfWU1XP5yac29mFx
### lvl 2
```
cat spaces\ in\ this\ filename
cat 'spaces in this filename'
cat *
cat spaces*in*this*filename
find . -inum 123456 -exec cat {} \;
```
Pass : MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
### lvl 3
```
ls -a
cat ...Hiding-From-You
```
Pass : 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
### lvl 4
```
file ./*
cat ./-file00
```
Pass : 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
### lvl 5
```
find . -size 1033c 2>/dev/null
cat ./maybehere07/.file2
```
Pass : HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
### lvl 6
```
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
cat /var/lib/dpkg/info/bandit7.password
```
Pass : morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
### lvl 7
```
grep -i "millionth" data.txt
```
Pass : dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
### lvl 8
```
sort data.txt | uniq -u
```
Pass : 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
### lvl 9
```
strings data.txt | grep =
```
Pass : FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
### lvl 10
```
cat data.txt | base64 -d
```
Pass : dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr

### lvl 11
```
cat data.txt | tr "$(echo {A..Z} {a..z} | tr -d ' ')" "$(echo {N..Z} {A..M} {n..z} {a..m}| tr -d ' ')"
-----
ROT13 Decoder
```
Pass : 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
### lvl 12
```
cd $(mktemp -d)                           (Create a temp dir and navigate there)
cp ~/data.txt .                       (Copy the data.txt file to the current dir)
xxd -r data.txt data                      (Reverse the hex content to ASCII)
file data                                 (gzip compressed data)
mv data data.gz                           (gzip -> .gz)
gzip -d data.gz                           (Decompress the file)
file data                                 (bzip2 compressed data)
mv data data.bz2                          (bzip2 -> .bz2)
bzip2 -d data.bz2                         (Decompress the file)
etc...
```
Pass : FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
### lvl 13
```
ssh bandit14@bandit.labs.overthewire.org -p 2220 -i sshkey.private
```
Pass :  None
### lvl 14
```
cat /etc/bandit_pass/bandit14         : MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
echo 'MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS' | nc localhost 30000
-------
telnet localhost 30000                :Correct!  8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
```
Pass : 8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
### lvl 15
```
echo 'Current_lvl_pass' | ncat --ssl localhost 30001
-------
echo 'Current_lvl_pass' | socat - OPENSSL:localhost:30001,verify=0
-------
openssl s_client -connect localhost:30001
Current_lvl_pass
```
Pass : kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx
### lvl 16
```
nmap localhost -p 31000-32000
nmap localhost -p 31046,31518,31691,31790,31960 -sV 
31518 ssl/echo , 31790 ssl/unknown        (Two ssl One is correct let's try both)

echo 'Current_lvl_pass' | ncat --ssl localhost 31790                   (Correct!)
-------
echo 'Current_lvl_pass' | socat - OPENSSL:localhost:31790,verify=0     (Correct!)

*Copy the RSA Key into a file and change it perm to 600, then ssh with it*
```
Pass : None
### lvl 17
```
diff passwords.old passwords.new
```
Pass : x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO
### lvl 18
```
ssh bandit18@bandit.labs.overthewire.org -p 2220 'cat readme'
Current_lvl_pass
```
Pass : cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8
### lvl 19
```
./bandit20-do cat /etc/bandit_pass/bandit20
```
Pass : 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
### lvl 20
```
./suconnect

On 1st shell:
echo 'Current_lvl_pass' | nc -lv 4444

On 2nd shell:
./suconnect 4444
Read: 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
Password matches, sending next password

On 1st shell:
Connection received on localhost 46516
EeoULMCra2q0dSkYj561DX7s1CpBuOBt
```
Pass :  EeoULMCra2q0dSkYj561DX7s1CpBuOBt
### lvl 21
```
cd  /etc/cron.d
cat cronjob_bandit22            (/usr/bin/cronjob_bandit22.sh)
cat /usr/bin/cronjob_bandit22.sh
cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
```
Pass : tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q
### lvl 22
```
Same as the pervious challenge:

cat /usr/bin/cronjob_bandit23.sh
The password in this file /tmp/$mytarget
$mytarget = $(echo I am user $myname | md5sum | cut -d ' ' -f 1)
$myname = $(whoami) = bandit23
cat /tmp/$(echo I am user bandit23 | md5sum | cut -d ' ' -f 1)
```
Pass : 0Zf11ioIjMVN551jX3CmStKLYqjk54Ga
### lvl 23
```
Same as the pervious challenges:

cat cat /usr/bin/cronjob_bandit24.sh

touch /tmp/password.txt ; chmod o+w /tmp/password.txt
echo 'cat /etc/bandit_pass/bandit24 > /tmp/password.txt' > sc.sh
chmod +x sc.sh

Wait a minut...

cat /tmp/password.txt
```
Pass : gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8
### lvl 24
```
#!/usr/bin/env python3
import socket, sys

HOST, PORT = "localhost", 30002
PREFIX = "gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8"

for i in range(10000):
    code = f"{i:04d}"
    try:
        # Open and connect socket
        s = socket.create_connection((HOST, PORT))
        # Briefly set a short timeout to grab any initial banner
        s.settimeout(0.1)
        try:
            s.recv(4096)  # discard whatever the server sends first
        except socket.timeout:
            pass
        finally:
            s.settimeout(None)

        # Send our payload and read the post‐payload response
        s.sendall(f"{PREFIX} {code}\n".encode())
        resp = s.recv(4096).decode(errors="ignore")
        s.close()
    except Exception:
        continue

    if "wrong" not in resp.lower():
        print(f"Success! Code={code}\nResponse: {resp.strip()}")
        sys.exit(0)

print("No valid code found.")
sys.exit(1)

python3 script.py    (Success! Code=2219, Response: Correct!)
```
Pass : iCi86ttT4KSNe1armKiwbQNmB3YJP3q4
### lvl 25
```
*The shell for user bandit26 is not /bin/bash*

ssh bandit26@bandit.labs.overthewire.org -p 2220 -i bandit26.sshkey
"Connection to bandit.labs.overthewire.org closed."

grep bandit26 /etc/passwd  (The shell : /usr/bin/showtext)
cat /usr/bin/showtext
----------
#!/bin/sh

export TERM=linux

exec more ~/text.txt
exit 0
----------
it uses more which is paging through text *one screenful* at a time.
We need to get to more's buffer.

Resize the terminal to show one or two line
ssh bandit26@bandit.labs.overthewire.org -p 2220 -i bandit26.sshkey
Type v to get into `Vim`

1st way:  (Will retrieve the password)
:r /etc/bandit_pass/bandit26
--------
2nd way:  (Will open a /bin/bash shell for bandit26)
:set shell=/bin/bash
:shell
cat /etc/bandit_pass/bandit26
```
Pass : None
### lvl 26
```
./bandit27-do cat /etc/bandit_pass/bandit27
```
Pass : upsNCc7vzaRDx6oZC6GiR6ERwe1MowGB
### lvl 27
```
cd $(mktemp -d)
GIT_SSH_COMMAND='ssh -p 2220' git clone ssh://bandit27-git@localhost/home/bandit27-git/repo

cd repo/.git
git show
+The password to the next level is: Yz9IpL0sBcCeuG7m9uQFt8ZNpS4HZRcN
```
Pass : Yz9IpL0sBcCeuG7m9uQFt8ZNpS4HZRcN
### lvl 28
```
Same as the previouse challenge:

git show
 - username: bandit29
-- password: 4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7
+- password: xxxxxxxxxx
```
Pass : 4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7
### lvl 29
```
Same as the previouse challenges:

git show-ref
git show refs/remotes/origin/dev
 - username: bandit30
-- password: <no passwords in production!>
+- password: qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL
```
Pass : qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL
### lvl 30
```
Same as the previouse challenges:

git show-ref
git show refs/tags/secret       (fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy)
```
Pass : fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy
### lvl 31
```
Same as the previouse challenges:

git show
+This time your task is to push a file to the remote repository.
+
+Details:
+    File name: key.txt
+    Content: 'May I come in?'
+    Branch: master

cd ..          (Navigate one step back to the work tree "repo")

echo 'May I come in?' > key.txt
git add -f key.txt
git commit -m "Give me the fucking password"
GIT_SSH_COMMAND='ssh -p 2220' git push origin master

remote: Well done! Here is the password for the next level:
remote: 3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K
```
Pass : 3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K
### lvl 32
```
1st way:
$0
cat /etc/bandit_pass/bandit33

2nd way:
/*/?[!0-9]??64 /*/???????????/??????33    (/bin/base64 /etc/bandit_pass/bandit33)
echo 'dFFkdGJzNUQ1aTJ2SndrTzhtRXlZRXlUTDhpem9lSjAK' | base64 -d
```
Pass : tQdtbs5D5i2vJwkO8mEyYEyTL8izoeJ0


