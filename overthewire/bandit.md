# Bandit - Unix/Linux basics

## Bandit 0 
### Level Goal
The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

- TIP: Create a file for notes and passwords on your local machine!
- Passwords for levels are not saved automatically. If you do not save them yourself, you will need to start over from bandit0.
- Passwords also occasionally change. It is recommended to take notes on how to solve each challenge. As levels get more challenging, detailed notes are useful to return to where you left off, reference for later problems, or help others after you’ve completed the challenge.

### Execution Log
```bash
┌──(incognito㉿kali)-[~]
└─$ ssh -p 2220 bandit0@bandit.labs.overthewire.org
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

backend: gibson-1
bandit0@bandit.labs.overthewire.org's password: 

      ,----..            ,----,          .---.
     /   /   \         ,/   .`|         /. ./|
    /   .     :      ,`   .'  :     .--'.  ' ;
   .   /   ;.  \   ;    ;     /    /__./ \ : |
  .   ;   /  ` ; .'___,/    ,' .--'.  '   \' .
  ;   |  ; \ ; | |    :     | /___/ \ |    ' '
  |   :  | ; | ' ;    |.';  ; ;   \  \;      :
  .   |  ' ' ' : `----'  |  |  \   ;  `      |
  '   ;  \; /  |     '   :  ;   .   \    .\  ;
   \   \  ',  /      |   |  '    \   \   ' \ |
    ;   :    /       '   :  |     :   '  |--"
     \   \ .'        ;   |.'       \   \ ;
  www. `---` ver     '---' he       '---" ire.org


Welcome to OverTheWire!

If you find any problems, please report them to the #wargames channel on
discord or IRC.

--[ Playing the games ]--

  This machine might hold several wargames.
  If you are playing "somegame", then:

    * USERNAMES are somegame0, somegame1, ...
    * Most LEVELS are stored in /somegame/.
    * PASSWORDS for each level are stored in /etc/somegame_pass/.

  Write-access to homedirectories is disabled. It is advised to create a
  working directory with a hard-to-guess name in /tmp/.  You can use the
  command "mktemp -d" in order to generate a random and hard to guess
  directory in /tmp/.  Read-access to both /tmp/ is disabled and to /proc
  restricted so that users cannot snoop on eachother. Files and directories
  with easily guessable or short names will be periodically deleted! The /tmp
  directory is regularly wiped.
  Please play nice:

    * don't leave orphan processes running
    * don't leave exploit-files laying around
    * don't annoy other players
    * don't post passwords or spoilers
    * again, DONT POST SPOILERS!
      This includes writeups of your solution on your blog or website!

--[ Tips ]--

  This machine has a 64bit processor and many security-features enabled
  by default, although ASLR has been switched off.  The following
  compiler flags might be interesting:

    -m32                    compile for 32bit
    -fno-stack-protector    disable ProPolice
    -Wl,-z,norelro          disable relro

  In addition, the execstack tool can be used to flag the stack as
  executable on ELF binaries.

  Finally, network-access is limited for most levels by a local
  firewall.

--[ Tools ]--

 For your convenience we have installed a few useful tools which you can find
 in the following locations:

    * gef (https://github.com/hugsy/gef) in /opt/gef/
    * pwndbg (https://github.com/pwndbg/pwndbg) in /opt/pwndbg/
    * gdbinit (https://github.com/gdbinit/Gdbinit) in /opt/gdbinit/
    * pwntools (https://github.com/Gallopsled/pwntools)
    * radare2 (http://www.radare.org/)

--[ More information ]--

  For more information regarding individual wargames, visit
  http://www.overthewire.org/wargames/

  For support, questions or comments, contact us on discord or IRC.

  Enjoy your stay!

bandit0@bandit:~$ ls
readme
bandit0@bandit:~$ cat readme
Congratulations on your first steps into the bandit game!!
Please make sure you have read the rules at https://overthewire.org/rules/
If you are following a course, workshop, walkthrough or other educational activity,
please inform the instructor about the rules as well and encourage them to
contribute to the OverTheWire community so we can keep these games free!

The password you are looking for is: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If

bandit0@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.
```

### Commands used to solve this level
#### ssh
```bash
ssh -p 2220 bandit0@bandit.labs.overthewire.org
```
The ssh command is used to establish a secure remote connection to the Bandit server via port 2220 using the username bandit0 and host bandit.labs.overthewire.org, allowing access to the challenge environment.

#### cat
```bash
cat readme
``` 
The cat command is executed to display the contents of the readme file, which contains the information required to proceed to the next level.

---


## Bandit 1
### Level Goal
The password for the next level is stored in a file called - located in the home directory

### Execution Log 
```bash
┌──(incognito㉿kali)-[~]
└─$ ssh -p 2220 bandit1@bandit.labs.overthewire.org
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

backend: gibson-1
bandit1@bandit.labs.overthewire.org's password: 

      ,----..            ,----,          .---.
     /   /   \         ,/   .`|         /. ./|
    /   .     :      ,`   .'  :     .--'.  ' ;
   .   /   ;.  \   ;    ;     /    /__./ \ : |
  .   ;   /  ` ; .'___,/    ,' .--'.  '   \' .
  ;   |  ; \ ; | |    :     | /___/ \ |    ' '
  |   :  | ; | ' ;    |.';  ; ;   \  \;      :
  .   |  ' ' ' : `----'  |  |  \   ;  `      |
  '   ;  \; /  |     '   :  ;   .   \    .\  ;
   \   \  ',  /      |   |  '    \   \   ' \ |
    ;   :    /       '   :  |     :   '  |--"
     \   \ .'        ;   |.'       \   \ ;
  www. `---` ver     '---' he       '---" ire.org


Welcome to OverTheWire!

If you find any problems, please report them to the #wargames channel on
discord or IRC.

--[ Playing the games ]--

  This machine might hold several wargames.
  If you are playing "somegame", then:

    * USERNAMES are somegame0, somegame1, ...
    * Most LEVELS are stored in /somegame/.
    * PASSWORDS for each level are stored in /etc/somegame_pass/.

  Write-access to homedirectories is disabled. It is advised to create a
  working directory with a hard-to-guess name in /tmp/.  You can use the
  command "mktemp -d" in order to generate a random and hard to guess
  directory in /tmp/.  Read-access to both /tmp/ is disabled and to /proc
  restricted so that users cannot snoop on eachother. Files and directories
  with easily guessable or short names will be periodically deleted! The /tmp
  directory is regularly wiped.
  Please play nice:

    * don't leave orphan processes running
    * don't leave exploit-files laying around
    * don't annoy other players
    * don't post passwords or spoilers
    * again, DONT POST SPOILERS!
      This includes writeups of your solution on your blog or website!

--[ Tips ]--

  This machine has a 64bit processor and many security-features enabled
  by default, although ASLR has been switched off.  The following
  compiler flags might be interesting:

    -m32                    compile for 32bit
    -fno-stack-protector    disable ProPolice
    -Wl,-z,norelro          disable relro

  In addition, the execstack tool can be used to flag the stack as
  executable on ELF binaries.

  Finally, network-access is limited for most levels by a local
  firewall.

--[ Tools ]--

 For your convenience we have installed a few useful tools which you can find
 in the following locations:

    * gef (https://github.com/hugsy/gef) in /opt/gef/
    * pwndbg (https://github.com/pwndbg/pwndbg) in /opt/pwndbg/
    * gdbinit (https://github.com/gdbinit/Gdbinit) in /opt/gdbinit/
    * pwntools (https://github.com/Gallopsled/pwntools)
    * radare2 (http://www.radare.org/)

--[ More information ]--

  For more information regarding individual wargames, visit
  http://www.overthewire.org/wargames/

  For support, questions or comments, contact us on discord or IRC.

  Enjoy your stay!

bandit1@bandit:~$ ls
-
bandit1@bandit:~$ cat ./-
263JGJPfgU6LtdEvgfWU1XP5yac29mFx
bandit1@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.
```

### Commands used to solve this level
#### Use `cat ./-` instead of `cat -`
```bash
cat ./-
```

### Note: 
If using `cat -`, in Linux/Unix, `-` is interpreted as standard input rather than a filename, so `cat -` reads from the keyboard or a pipe. However, using `cat ./-`, where `./` is referring to the current directory and explicitly tells the system to to access a file located in the current working directory.

---


## Bandit 2
### Level Goal
The password for the next level is stored in a file called --spaces in this filename-- located in the home directory

### Execution Log
```bash
┌──(incognito㉿kali)-[~]
└─$ ssh -p 2220 bandit2@bandit.labs.overthewire.org
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

backend: gibson-1
bandit2@bandit.labs.overthewire.org's password: 

      ,----..            ,----,          .---.
     /   /   \         ,/   .`|         /. ./|
    /   .     :      ,`   .'  :     .--'.  ' ;
   .   /   ;.  \   ;    ;     /    /__./ \ : |
  .   ;   /  ` ; .'___,/    ,' .--'.  '   \' .
  ;   |  ; \ ; | |    :     | /___/ \ |    ' '
  |   :  | ; | ' ;    |.';  ; ;   \  \;      :
  .   |  ' ' ' : `----'  |  |  \   ;  `      |
  '   ;  \; /  |     '   :  ;   .   \    .\  ;
   \   \  ',  /      |   |  '    \   \   ' \ |
    ;   :    /       '   :  |     :   '  |--"
     \   \ .'        ;   |.'       \   \ ;
  www. `---` ver     '---' he       '---" ire.org


Welcome to OverTheWire!

If you find any problems, please report them to the #wargames channel on
discord or IRC.

--[ Playing the games ]--

  This machine might hold several wargames.
  If you are playing "somegame", then:

    * USERNAMES are somegame0, somegame1, ...
    * Most LEVELS are stored in /somegame/.
    * PASSWORDS for each level are stored in /etc/somegame_pass/.

  Write-access to homedirectories is disabled. It is advised to create a
  working directory with a hard-to-guess name in /tmp/.  You can use the
  command "mktemp -d" in order to generate a random and hard to guess
  directory in /tmp/.  Read-access to both /tmp/ is disabled and to /proc
  restricted so that users cannot snoop on eachother. Files and directories
  with easily guessable or short names will be periodically deleted! The /tmp
  directory is regularly wiped.
  Please play nice:

    * don't leave orphan processes running
    * don't leave exploit-files laying around
    * don't annoy other players
    * don't post passwords or spoilers
    * again, DONT POST SPOILERS!
      This includes writeups of your solution on your blog or website!

--[ Tips ]--

  This machine has a 64bit processor and many security-features enabled
  by default, although ASLR has been switched off.  The following
  compiler flags might be interesting:

    -m32                    compile for 32bit
    -fno-stack-protector    disable ProPolice
    -Wl,-z,norelro          disable relro

  In addition, the execstack tool can be used to flag the stack as
  executable on ELF binaries.

  Finally, network-access is limited for most levels by a local
  firewall.

--[ Tools ]--

 For your convenience we have installed a few useful tools which you can find
 in the following locations:

    * gef (https://github.com/hugsy/gef) in /opt/gef/
    * pwndbg (https://github.com/pwndbg/pwndbg) in /opt/pwndbg/
    * gdbinit (https://github.com/gdbinit/Gdbinit) in /opt/gdbinit/
    * pwntools (https://github.com/Gallopsled/pwntools)
    * radare2 (http://www.radare.org/)

--[ More information ]--

  For more information regarding individual wargames, visit
  http://www.overthewire.org/wargames/

  For support, questions or comments, contact us on discord or IRC.

  Enjoy your stay!

bandit2@bandit:~$ ls
--spaces in this filename--
bandit2@bandit:~$ cat ./--spaces\ in\ this\ filename-- 
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
```

### Commands used to solve this level
```bash
cat ./--spaces\ in\ this\ filename-- 
```

### Note: 
The filename contains spaces, which the shell interprets as separate arguments, so backslashes `\` are used to escape each space, allowing the full filename to be correctly recognized as a single file when executing the cat command. If the command `cat ./-- spaces in this filename--` is used without escape characters, the shell will treat each space-separated word as a separate argument, causing the command to fail because it cannot locate the intended file.

---


## Bandit 3
### Level Goal
The password for the next level is stored in a hidden file in the inhere directory.

### Execution Log
```bash
┌──(incognito㉿kali)-[~]
└─$ ssh -p 2220 bandit3@bandit.labs.overthewire.org
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

backend: gibson-1
bandit3@bandit.labs.overthewire.org's password: 

      ,----..            ,----,          .---.
     /   /   \         ,/   .`|         /. ./|
    /   .     :      ,`   .'  :     .--'.  ' ;
   .   /   ;.  \   ;    ;     /    /__./ \ : |
  .   ;   /  ` ; .'___,/    ,' .--'.  '   \' .
  ;   |  ; \ ; | |    :     | /___/ \ |    ' '
  |   :  | ; | ' ;    |.';  ; ;   \  \;      :
  .   |  ' ' ' : `----'  |  |  \   ;  `      |
  '   ;  \; /  |     '   :  ;   .   \    .\  ;
   \   \  ',  /      |   |  '    \   \   ' \ |
    ;   :    /       '   :  |     :   '  |--"
     \   \ .'        ;   |.'       \   \ ;
  www. `---` ver     '---' he       '---" ire.org


Welcome to OverTheWire!

If you find any problems, please report them to the #wargames channel on
discord or IRC.

--[ Playing the games ]--

  This machine might hold several wargames.
  If you are playing "somegame", then:

    * USERNAMES are somegame0, somegame1, ...
    * Most LEVELS are stored in /somegame/.
    * PASSWORDS for each level are stored in /etc/somegame_pass/.

  Write-access to homedirectories is disabled. It is advised to create a
  working directory with a hard-to-guess name in /tmp/.  You can use the
  command "mktemp -d" in order to generate a random and hard to guess
  directory in /tmp/.  Read-access to both /tmp/ is disabled and to /proc
  restricted so that users cannot snoop on eachother. Files and directories
  with easily guessable or short names will be periodically deleted! The /tmp
  directory is regularly wiped.
  Please play nice:

    * don't leave orphan processes running
    * don't leave exploit-files laying around
    * don't annoy other players
    * don't post passwords or spoilers
    * again, DONT POST SPOILERS!
      This includes writeups of your solution on your blog or website!

--[ Tips ]--

  This machine has a 64bit processor and many security-features enabled
  by default, although ASLR has been switched off.  The following
  compiler flags might be interesting:

    -m32                    compile for 32bit
    -fno-stack-protector    disable ProPolice
    -Wl,-z,norelro          disable relro

  In addition, the execstack tool can be used to flag the stack as
  executable on ELF binaries.

  Finally, network-access is limited for most levels by a local
  firewall.

--[ Tools ]--

 For your convenience we have installed a few useful tools which you can find
 in the following locations:

    * gef (https://github.com/hugsy/gef) in /opt/gef/
    * pwndbg (https://github.com/pwndbg/pwndbg) in /opt/pwndbg/
    * gdbinit (https://github.com/gdbinit/Gdbinit) in /opt/gdbinit/
    * pwntools (https://github.com/Gallopsled/pwntools)
    * radare2 (http://www.radare.org/)

--[ More information ]--

  For more information regarding individual wargames, visit
  http://www.overthewire.org/wargames/

  For support, questions or comments, contact us on discord or IRC.

  Enjoy your stay!

bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cd inhere
bandit3@bandit:~/inhere$ ls
bandit3@bandit:~/inhere$ ls -lia
total 12
332223 drwxr-xr-x 2 root    root    4096 Apr  3 15:17 .
331898 drwxr-xr-x 3 root    root    4096 Apr  3 15:17 ..
332225 -rw-r----- 1 bandit4 bandit3   33 Apr  3 15:17 ...Hiding-From-You
bandit3@bandit:~/inhere$ cat ./...Hiding-From-You
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
bandit3@bandit:~/inhere$ exit
logout
Connection to bandit.labs.overthewire.org closed.
```

### Commands used to solve this level
```bash
ls -lia
```

### Note: 
The challenge is solved by navigating into the inhere directory, using `ls -la` to reveal hidden files, and then reading the hidden file `...Hiding-From-You` with the cat command to obtain the required password. The default ls command is not sufficient to discover the hidden file because it does not display files that begin with a dot `.`, causing files like `...Hiding-From-You` to remain unseen. Therefore, the `ls -lia` command is used, where `-a` reveals all files including hidden ones, `-l` provides detailed information such as permissions and ownership, and `-i` displays inode numbers, allowing the hidden file to be identified and accessed.


---


## Bandit 4
### Level Goal
The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.

### Execution Log 
```bash
┌──(incognito㉿kali)-[~]
└─$ ssh -p 2220 bandit4@bandit.labs.overthewire.org
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

backend: gibson-1
bandit4@bandit.labs.overthewire.org's password: 

      ,----..            ,----,          .---.
     /   /   \         ,/   .`|         /. ./|
    /   .     :      ,`   .'  :     .--'.  ' ;
   .   /   ;.  \   ;    ;     /    /__./ \ : |
  .   ;   /  ` ; .'___,/    ,' .--'.  '   \' .
  ;   |  ; \ ; | |    :     | /___/ \ |    ' '
  |   :  | ; | ' ;    |.';  ; ;   \  \;      :
  .   |  ' ' ' : `----'  |  |  \   ;  `      |
  '   ;  \; /  |     '   :  ;   .   \    .\  ;
   \   \  ',  /      |   |  '    \   \   ' \ |
    ;   :    /       '   :  |     :   '  |--"
     \   \ .'        ;   |.'       \   \ ;
  www. `---` ver     '---' he       '---" ire.org


Welcome to OverTheWire!

If you find any problems, please report them to the #wargames channel on
discord or IRC.

--[ Playing the games ]--

  This machine might hold several wargames.
  If you are playing "somegame", then:

    * USERNAMES are somegame0, somegame1, ...
    * Most LEVELS are stored in /somegame/.
    * PASSWORDS for each level are stored in /etc/somegame_pass/.

  Write-access to homedirectories is disabled. It is advised to create a
  working directory with a hard-to-guess name in /tmp/.  You can use the
  command "mktemp -d" in order to generate a random and hard to guess
  directory in /tmp/.  Read-access to both /tmp/ is disabled and to /proc
  restricted so that users cannot snoop on eachother. Files and directories
  with easily guessable or short names will be periodically deleted! The /tmp
  directory is regularly wiped.
  Please play nice:

    * don't leave orphan processes running
    * don't leave exploit-files laying around
    * don't annoy other players
    * don't post passwords or spoilers
    * again, DONT POST SPOILERS!
      This includes writeups of your solution on your blog or website!

--[ Tips ]--

  This machine has a 64bit processor and many security-features enabled
  by default, although ASLR has been switched off.  The following
  compiler flags might be interesting:

    -m32                    compile for 32bit
    -fno-stack-protector    disable ProPolice
    -Wl,-z,norelro          disable relro

  In addition, the execstack tool can be used to flag the stack as
  executable on ELF binaries.

  Finally, network-access is limited for most levels by a local
  firewall.

--[ Tools ]--

 For your convenience we have installed a few useful tools which you can find
 in the following locations:

    * gef (https://github.com/hugsy/gef) in /opt/gef/
    * pwndbg (https://github.com/pwndbg/pwndbg) in /opt/pwndbg/
    * gdbinit (https://github.com/gdbinit/Gdbinit) in /opt/gdbinit/
    * pwntools (https://github.com/Gallopsled/pwntools)
    * radare2 (http://www.radare.org/)

--[ More information ]--

  For more information regarding individual wargames, visit
  http://www.overthewire.org/wargames/

  For support, questions or comments, contact us on discord or IRC.

  Enjoy your stay!

bandit4@bandit:~$ ls
inhere
bandit4@bandit:~$ cd inhere
bandit4@bandit:~/inhere$ ls
-file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09
bandit4@bandit:~/inhere$ file *
file: Cannot open `ile00' (No such file or directory)
file: Cannot open `ile01' (No such file or directory)
file: Cannot open `ile02' (No such file or directory)
file: Cannot open `ile03' (No such file or directory)
file: Cannot open `ile04' (No such file or directory)
file: Cannot open `ile05' (No such file or directory)
file: Cannot open `ile06' (No such file or directory)
file: Cannot open `ile07' (No such file or directory)
file: Cannot open `ile08' (No such file or directory)
file: Cannot open `ile09' (No such file or directory)
bandit4@bandit:~/inhere$ file ./-file*
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: data
bandit4@bandit:~/inhere$ cat ./-file07
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
bandit4@bandit:~/inhere$ cat ./-file00
d%�h�U��N?CN�qy�▒������B��g4V�bandit4@bandit:~/inhere$ cat ./-file01
i�,��%?�mҶ�Q��3�Z����A�)�bandit4@bandit:~/inhere$ cat ./-file02
/��^����,��G�V�����J�
�PTE�bandit4@bandit:~/inhere$ cat ./-file03
��k����;;Nϱ��m�R]Y�����Ӭ�N�Imbandit4@bandit:~/inhere$ cat ./-file04
X���-�t�i�$�ʥ��Ev���v�qi�1�HE)bandit4@bandit:~/inhere$ cat ./-file05
>���7���vl��Q�nk��,�0K��V��XHbandit4@bandit:~/inhere$ cat ./-file06
�c��W$�g�����l(�2�Y
�]�L��]vr�bandit4@bandit:~/inhere$ cat ./-file07
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
bandit4@bandit:~/inhere$ cat ./-file08
KU����  g���
��jD\�9�hx�!���o�bandit4@bandit:~/inhere$ cat ./-file09
8'�bandit4@bandit:~/inhere$ exit
logout
Connection to bandit.labs.overthewire.org closed.
```

### Commands used to solve this level
```bash
file ./-file*
```

### Note: 
The `file ./-file*` command is used to determine the type of each file in the directory, allowing the identification of the only human-readable file `ASCII text` among multiple binary files. Using `file *` fails in this case because filenames beginning with `-` are interpreted by the shell as command options rather than actual filenames, causing errors, whereas prefixing them with `./` explicitly indicates that they are files in the current directory, ensuring they are correctly processed by the file command.

---


## Bandit 5
### Level Goal
The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:
- human-readable
- 1033 bytes in size
- not executable

### Execution Log 
```bash
┌──(incognito㉿kali)-[~]
└─$ ssh -p 2220 bandit5@bandit.labs.overthewire.org
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

backend: gibson-1
bandit5@bandit.labs.overthewire.org's password: 

      ,----..            ,----,          .---.
     /   /   \         ,/   .`|         /. ./|
    /   .     :      ,`   .'  :     .--'.  ' ;
   .   /   ;.  \   ;    ;     /    /__./ \ : |
  .   ;   /  ` ; .'___,/    ,' .--'.  '   \' .
  ;   |  ; \ ; | |    :     | /___/ \ |    ' '
  |   :  | ; | ' ;    |.';  ; ;   \  \;      :
  .   |  ' ' ' : `----'  |  |  \   ;  `      |
  '   ;  \; /  |     '   :  ;   .   \    .\  ;
   \   \  ',  /      |   |  '    \   \   ' \ |
    ;   :    /       '   :  |     :   '  |--"
     \   \ .'        ;   |.'       \   \ ;
  www. `---` ver     '---' he       '---" ire.org


Welcome to OverTheWire!

If you find any problems, please report them to the #wargames channel on
discord or IRC.

--[ Playing the games ]--

  This machine might hold several wargames.
  If you are playing "somegame", then:

    * USERNAMES are somegame0, somegame1, ...
    * Most LEVELS are stored in /somegame/.
    * PASSWORDS for each level are stored in /etc/somegame_pass/.

  Write-access to homedirectories is disabled. It is advised to create a
  working directory with a hard-to-guess name in /tmp/.  You can use the
  command "mktemp -d" in order to generate a random and hard to guess
  directory in /tmp/.  Read-access to both /tmp/ is disabled and to /proc
  restricted so that users cannot snoop on eachother. Files and directories
  with easily guessable or short names will be periodically deleted! The /tmp
  directory is regularly wiped.
  Please play nice:

    * don't leave orphan processes running
    * don't leave exploit-files laying around
    * don't annoy other players
    * don't post passwords or spoilers
    * again, DONT POST SPOILERS!
      This includes writeups of your solution on your blog or website!

--[ Tips ]--

  This machine has a 64bit processor and many security-features enabled
  by default, although ASLR has been switched off.  The following
  compiler flags might be interesting:

    -m32                    compile for 32bit
    -fno-stack-protector    disable ProPolice
    -Wl,-z,norelro          disable relro

  In addition, the execstack tool can be used to flag the stack as
  executable on ELF binaries.

  Finally, network-access is limited for most levels by a local
  firewall.

--[ Tools ]--

 For your convenience we have installed a few useful tools which you can find
 in the following locations:

    * gef (https://github.com/hugsy/gef) in /opt/gef/
    * pwndbg (https://github.com/pwndbg/pwndbg) in /opt/pwndbg/
    * gdbinit (https://github.com/gdbinit/Gdbinit) in /opt/gdbinit/
    * pwntools (https://github.com/Gallopsled/pwntools)
    * radare2 (http://www.radare.org/)

--[ More information ]--

  For more information regarding individual wargames, visit
  http://www.overthewire.org/wargames/

  For support, questions or comments, contact us on discord or IRC.

  Enjoy your stay!

bandit5@bandit:~$ ls
inhere
bandit5@bandit:~$ cd inhere
bandit5@bandit:~/inhere$ ls -lia
total 88
332275 drwxr-x--- 22 root bandit5 4096 Apr  3 15:17 .
331928 drwxr-xr-x  3 root root    4096 Apr  3 15:17 ..
332276 drwxr-x---  2 root bandit5 4096 Apr  3 15:17 maybehere00
332286 drwxr-x---  2 root bandit5 4096 Apr  3 15:17 maybehere01
332297 drwxr-x---  2 root bandit5 4096 Apr  3 15:17 maybehere02
332316 drwxr-x---  2 root bandit5 4096 Apr  3 15:17 maybehere03
332326 drwxr-x---  2 root bandit5 4096 Apr  3 15:17 maybehere04
332336 drwxr-x---  2 root bandit5 4096 Apr  3 15:17 maybehere05
332346 drwxr-x---  2 root bandit5 4096 Apr  3 15:17 maybehere06
332356 drwxr-x---  2 root bandit5 4096 Apr  3 15:17 maybehere07
332366 drwxr-x---  2 root bandit5 4096 Apr  3 15:17 maybehere08
332376 drwxr-x---  2 root bandit5 4096 Apr  3 15:17 maybehere09
332386 drwxr-x---  2 root bandit5 4096 Apr  3 15:17 maybehere10
332396 drwxr-x---  2 root bandit5 4096 Apr  3 15:17 maybehere11
332406 drwxr-x---  2 root bandit5 4096 Apr  3 15:17 maybehere12
332416 drwxr-x---  2 root bandit5 4096 Apr  3 15:17 maybehere13
332426 drwxr-x---  2 root bandit5 4096 Apr  3 15:17 maybehere14
332436 drwxr-x---  2 root bandit5 4096 Apr  3 15:17 maybehere15
332446 drwxr-x---  2 root bandit5 4096 Apr  3 15:17 maybehere16
332456 drwxr-x---  2 root bandit5 4096 Apr  3 15:17 maybehere17
332466 drwxr-x---  2 root bandit5 4096 Apr  3 15:17 maybehere18
332476 drwxr-x---  2 root bandit5 4096 Apr  3 15:17 maybehere19
bandit5@bandit:~/inhere$ find . -type f -size 1033c ! -executable
./maybehere07/.file2
bandit5@bandit:~$ cat ./inhere/maybehere07/.file2
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        bandit5@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.
```

### Commands used to solve this level
```bash
find . -type f -size 1033c ! -executable
```

### Note: 
Since manually using `cat` to open every file would be inefficient and time-consuming, the `find` command is used to quickly locate the correct file by filtering based on the given requirements, specifically searching for files that are exactly 1033 bytes in size `-size 1033c`, are regular files `-type f`, and are not executable `! -executable`; this targeted approach significantly narrows down the search and allows the correct file to be identified efficiently without unnecessary manual inspection.


---


## Bandit 6
### Level Goal
The password for the next level is stored somewhere on the server and has all of the following properties:
- owned by user bandit7
- owned by group bandit6
- 33 bytes in size

### Execution Log 
```bash
┌──(incognito㉿kali)-[~]
└─$ ssh -p 2220 bandit6@bandit.labs.overthewire.org
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

backend: gibson-1
bandit6@bandit.labs.overthewire.org's password: 

      ,----..            ,----,          .---.
     /   /   \         ,/   .`|         /. ./|
    /   .     :      ,`   .'  :     .--'.  ' ;
   .   /   ;.  \   ;    ;     /    /__./ \ : |
  .   ;   /  ` ; .'___,/    ,' .--'.  '   \' .
  ;   |  ; \ ; | |    :     | /___/ \ |    ' '
  |   :  | ; | ' ;    |.';  ; ;   \  \;      :
  .   |  ' ' ' : `----'  |  |  \   ;  `      |
  '   ;  \; /  |     '   :  ;   .   \    .\  ;
   \   \  ',  /      |   |  '    \   \   ' \ |
    ;   :    /       '   :  |     :   '  |--"
     \   \ .'        ;   |.'       \   \ ;
  www. `---` ver     '---' he       '---" ire.org


Welcome to OverTheWire!

If you find any problems, please report them to the #wargames channel on
discord or IRC.

--[ Playing the games ]--

  This machine might hold several wargames.
  If you are playing "somegame", then:

    * USERNAMES are somegame0, somegame1, ...
    * Most LEVELS are stored in /somegame/.
    * PASSWORDS for each level are stored in /etc/somegame_pass/.

  Write-access to homedirectories is disabled. It is advised to create a
  working directory with a hard-to-guess name in /tmp/.  You can use the
  command "mktemp -d" in order to generate a random and hard to guess
  directory in /tmp/.  Read-access to both /tmp/ is disabled and to /proc
  restricted so that users cannot snoop on eachother. Files and directories
  with easily guessable or short names will be periodically deleted! The /tmp
  directory is regularly wiped.
  Please play nice:

    * don't leave orphan processes running
    * don't leave exploit-files laying around
    * don't annoy other players
    * don't post passwords or spoilers
    * again, DONT POST SPOILERS!
      This includes writeups of your solution on your blog or website!

--[ Tips ]--

  This machine has a 64bit processor and many security-features enabled
  by default, although ASLR has been switched off.  The following
  compiler flags might be interesting:

    -m32                    compile for 32bit
    -fno-stack-protector    disable ProPolice
    -Wl,-z,norelro          disable relro

  In addition, the execstack tool can be used to flag the stack as
  executable on ELF binaries.

  Finally, network-access is limited for most levels by a local
  firewall.

--[ Tools ]--

 For your convenience we have installed a few useful tools which you can find
 in the following locations:

    * gef (https://github.com/hugsy/gef) in /opt/gef/
    * pwndbg (https://github.com/pwndbg/pwndbg) in /opt/pwndbg/
    * gdbinit (https://github.com/gdbinit/Gdbinit) in /opt/gdbinit/
    * pwntools (https://github.com/Gallopsled/pwntools)
    * radare2 (http://www.radare.org/)

--[ More information ]--

  For more information regarding individual wargames, visit
  http://www.overthewire.org/wargames/

  For support, questions or comments, contact us on discord or IRC.

  Enjoy your stay!

bandit6@bandit:~$ find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
bandit6@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.
```

### Commands used to solve this level
```bash
find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
```

### Note: 
The `find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null` command is used to search the entire filesystem starting from the root directory `/` for a file that matches all the given criteria, specifically a regular file `-type f` owned by user bandit7 `-user bandit7`, belonging to group bandit6 `-group bandit6`, and exactly 33 bytes in size `-size 33c`. Additionally, `2>/dev/null` is used to suppress permission denied errors that occur when accessing restricted directories, allowing the search results to display cleanly and making it easier to identify the correct file, which is then read using the `cat` command to obtain the password.

---


## Bandit 7
### Level Goal
The password for the next level is stored in the file data.txt next to the word millionth

### Execution Log 
```bash
┌──(incognito㉿kali)-[~]
└─$ ssh -p 2220 bandit7@bandit.labs.overthewire.org
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

backend: gibson-1
bandit7@bandit.labs.overthewire.org's password: 

      ,----..            ,----,          .---.
     /   /   \         ,/   .`|         /. ./|
    /   .     :      ,`   .'  :     .--'.  ' ;
   .   /   ;.  \   ;    ;     /    /__./ \ : |
  .   ;   /  ` ; .'___,/    ,' .--'.  '   \' .
  ;   |  ; \ ; | |    :     | /___/ \ |    ' '
  |   :  | ; | ' ;    |.';  ; ;   \  \;      :
  .   |  ' ' ' : `----'  |  |  \   ;  `      |
  '   ;  \; /  |     '   :  ;   .   \    .\  ;
   \   \  ',  /      |   |  '    \   \   ' \ |
    ;   :    /       '   :  |     :   '  |--"
     \   \ .'        ;   |.'       \   \ ;
  www. `---` ver     '---' he       '---" ire.org


Welcome to OverTheWire!

If you find any problems, please report them to the #wargames channel on
discord or IRC.

--[ Playing the games ]--

  This machine might hold several wargames.
  If you are playing "somegame", then:

    * USERNAMES are somegame0, somegame1, ...
    * Most LEVELS are stored in /somegame/.
    * PASSWORDS for each level are stored in /etc/somegame_pass/.

  Write-access to homedirectories is disabled. It is advised to create a
  working directory with a hard-to-guess name in /tmp/.  You can use the
  command "mktemp -d" in order to generate a random and hard to guess
  directory in /tmp/.  Read-access to both /tmp/ is disabled and to /proc
  restricted so that users cannot snoop on eachother. Files and directories
  with easily guessable or short names will be periodically deleted! The /tmp
  directory is regularly wiped.
  Please play nice:

    * don't leave orphan processes running
    * don't leave exploit-files laying around
    * don't annoy other players
    * don't post passwords or spoilers
    * again, DONT POST SPOILERS!
      This includes writeups of your solution on your blog or website!

--[ Tips ]--

  This machine has a 64bit processor and many security-features enabled
  by default, although ASLR has been switched off.  The following
  compiler flags might be interesting:

    -m32                    compile for 32bit
    -fno-stack-protector    disable ProPolice
    -Wl,-z,norelro          disable relro

  In addition, the execstack tool can be used to flag the stack as
  executable on ELF binaries.

  Finally, network-access is limited for most levels by a local
  firewall.

--[ Tools ]--

 For your convenience we have installed a few useful tools which you can find
 in the following locations:

    * gef (https://github.com/hugsy/gef) in /opt/gef/
    * pwndbg (https://github.com/pwndbg/pwndbg) in /opt/pwndbg/
    * gdbinit (https://github.com/gdbinit/Gdbinit) in /opt/gdbinit/
    * pwntools (https://github.com/Gallopsled/pwntools)
    * radare2 (http://www.radare.org/)

--[ More information ]--

  For more information regarding individual wargames, visit
  http://www.overthewire.org/wargames/

  For support, questions or comments, contact us on discord or IRC.

  Enjoy your stay!

bandit7@bandit:~$ ls
data.txt
bandit7@bandit:~$ grep millionth data.txt
millionth       dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
bandit7@bandit:~$ cat data.txt | grep millionth
millionth       dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
bandit7@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.
```

### Commands used to solve this level
```bash
grep millionth data.txt
cat data.txt | grep millionth
```

### Note: 
The solution can be achieved using the `grep` command, which searches for a specific keyword within a file. In this case, `grep millionth data.txt` directly scans the file and returns the line containing the word “millionth” along with the associated password, making it a quick and efficient way to locate the required information without manually reading the entire file.

Alternatively, the command `cat data.txt | grep millionth` uses a pipe (|) to first output the contents of the file with `cat` and then pass it to `grep` for filtering, producing the same result. However, this method is slightly less efficient since it involves an extra step, while both approaches demonstrate how text processing and command chaining can be used to extract specific data from large files.

---


## Bandit 8
### Level Goal
The password for the next level is stored in the file data.txt and is the only line of text that occurs only once

### Execution Log 
```bash
┌──(incognito㉿kali)-[~]
└─$ ssh -p 2220 bandit8@bandit.labs.overthewire.org
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

backend: gibson-1
bandit8@bandit.labs.overthewire.org's password: 

      ,----..            ,----,          .---.
     /   /   \         ,/   .`|         /. ./|
    /   .     :      ,`   .'  :     .--'.  ' ;
   .   /   ;.  \   ;    ;     /    /__./ \ : |
  .   ;   /  ` ; .'___,/    ,' .--'.  '   \' .
  ;   |  ; \ ; | |    :     | /___/ \ |    ' '
  |   :  | ; | ' ;    |.';  ; ;   \  \;      :
  .   |  ' ' ' : `----'  |  |  \   ;  `      |
  '   ;  \; /  |     '   :  ;   .   \    .\  ;
   \   \  ',  /      |   |  '    \   \   ' \ |
    ;   :    /       '   :  |     :   '  |--"
     \   \ .'        ;   |.'       \   \ ;
  www. `---` ver     '---' he       '---" ire.org


Welcome to OverTheWire!

If you find any problems, please report them to the #wargames channel on
discord or IRC.

--[ Playing the games ]--

  This machine might hold several wargames.
  If you are playing "somegame", then:

    * USERNAMES are somegame0, somegame1, ...
    * Most LEVELS are stored in /somegame/.
    * PASSWORDS for each level are stored in /etc/somegame_pass/.

  Write-access to homedirectories is disabled. It is advised to create a
  working directory with a hard-to-guess name in /tmp/.  You can use the
  command "mktemp -d" in order to generate a random and hard to guess
  directory in /tmp/.  Read-access to both /tmp/ is disabled and to /proc
  restricted so that users cannot snoop on eachother. Files and directories
  with easily guessable or short names will be periodically deleted! The /tmp
  directory is regularly wiped.
  Please play nice:

    * don't leave orphan processes running
    * don't leave exploit-files laying around
    * don't annoy other players
    * don't post passwords or spoilers
    * again, DONT POST SPOILERS!
      This includes writeups of your solution on your blog or website!

--[ Tips ]--

  This machine has a 64bit processor and many security-features enabled
  by default, although ASLR has been switched off.  The following
  compiler flags might be interesting:

    -m32                    compile for 32bit
    -fno-stack-protector    disable ProPolice
    -Wl,-z,norelro          disable relro

  In addition, the execstack tool can be used to flag the stack as
  executable on ELF binaries.

  Finally, network-access is limited for most levels by a local
  firewall.

--[ Tools ]--

 For your convenience we have installed a few useful tools which you can find
 in the following locations:

    * gef (https://github.com/hugsy/gef) in /opt/gef/
    * pwndbg (https://github.com/pwndbg/pwndbg) in /opt/pwndbg/
    * gdbinit (https://github.com/gdbinit/Gdbinit) in /opt/gdbinit/
    * pwntools (https://github.com/Gallopsled/pwntools)
    * radare2 (http://www.radare.org/)

--[ More information ]--

  For more information regarding individual wargames, visit
  http://www.overthewire.org/wargames/

  For support, questions or comments, contact us on discord or IRC.

  Enjoy your stay!

bandit8@bandit:~$ ls
data.txt
bandit8@bandit:~$ sort data.txt | uniq -u
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
bandit8@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.
```

### Commands used to solve this level
```bash
sort data.txt | uniq -u
```

### Note: 
The problem is solved by using `sort` and `uniq -u` together, where `sort data.txt` first arranges all lines so that identical entries are placed next to each other, allowing `uniq -u` to correctly identify and display only the line that appears once. The `uniq -u` cannot be used directly on the unsorted file because it only compares adjacent lines, meaning non-consecutive duplicates would not be detected and could lead to incorrect results, hence the need for sorting as a preprocessing step.

Other useful options for the `uniq` command include `-d`, which displays only the lines that are duplicated and appear more than once, `-c`, which shows a count of how many times each line occurs, and `-i`, which ignores case differences so that lines like "Hello" and "hello" are treated as identical, allowing for flexible filtering and analysis of repeated or unique lines in text data.

---


## Bandit 9
### Level Goal
The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

### Execution Log
```bash
┌──(incognito㉿kali)-[~]
└─$ ssh -p 2220 bandit9@bandit.labs.overthewire.org
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

backend: gibson-1
bandit9@bandit.labs.overthewire.org's password: 

      ,----..            ,----,          .---.
     /   /   \         ,/   .`|         /. ./|
    /   .     :      ,`   .'  :     .--'.  ' ;
   .   /   ;.  \   ;    ;     /    /__./ \ : |
  .   ;   /  ` ; .'___,/    ,' .--'.  '   \' .
  ;   |  ; \ ; | |    :     | /___/ \ |    ' '
  |   :  | ; | ' ;    |.';  ; ;   \  \;      :
  .   |  ' ' ' : `----'  |  |  \   ;  `      |
  '   ;  \; /  |     '   :  ;   .   \    .\  ;
   \   \  ',  /      |   |  '    \   \   ' \ |
    ;   :    /       '   :  |     :   '  |--"
     \   \ .'        ;   |.'       \   \ ;
  www. `---` ver     '---' he       '---" ire.org


Welcome to OverTheWire!

If you find any problems, please report them to the #wargames channel on
discord or IRC.

--[ Playing the games ]--

  This machine might hold several wargames.
  If you are playing "somegame", then:

    * USERNAMES are somegame0, somegame1, ...
    * Most LEVELS are stored in /somegame/.
    * PASSWORDS for each level are stored in /etc/somegame_pass/.

  Write-access to homedirectories is disabled. It is advised to create a
  working directory with a hard-to-guess name in /tmp/.  You can use the
  command "mktemp -d" in order to generate a random and hard to guess
  directory in /tmp/.  Read-access to both /tmp/ is disabled and to /proc
  restricted so that users cannot snoop on eachother. Files and directories
  with easily guessable or short names will be periodically deleted! The /tmp
  directory is regularly wiped.
  Please play nice:

    * don't leave orphan processes running
    * don't leave exploit-files laying around
    * don't annoy other players
    * don't post passwords or spoilers
    * again, DONT POST SPOILERS!
      This includes writeups of your solution on your blog or website!

--[ Tips ]--

  This machine has a 64bit processor and many security-features enabled
  by default, although ASLR has been switched off.  The following
  compiler flags might be interesting:

    -m32                    compile for 32bit
    -fno-stack-protector    disable ProPolice
    -Wl,-z,norelro          disable relro

  In addition, the execstack tool can be used to flag the stack as
  executable on ELF binaries.

  Finally, network-access is limited for most levels by a local
  firewall.

--[ Tools ]--

 For your convenience we have installed a few useful tools which you can find
 in the following locations:

    * gef (https://github.com/hugsy/gef) in /opt/gef/
    * pwndbg (https://github.com/pwndbg/pwndbg) in /opt/pwndbg/
    * gdbinit (https://github.com/gdbinit/Gdbinit) in /opt/gdbinit/
    * pwntools (https://github.com/Gallopsled/pwntools)
    * radare2 (http://www.radare.org/)

--[ More information ]--

  For more information regarding individual wargames, visit
  http://www.overthewire.org/wargames/

  For support, questions or comments, contact us on discord or IRC.

  Enjoy your stay!

bandit9@bandit:~$ ls
data.txt
bandit9@bandit:~$ strings data.txt | grep "="
,U=\[
========== the
=>XO
Qe=B
2========== password
=5J"
========== is
=oFt2
9=Dc
Yh6=o
=d\!#d=
H/=Q
========== FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
bWG=cE>
s=>5j
[xxhr=*
bandit9@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.
```

### Commands used to solve this level
```bash
strings data.txt | grep "="
```

### Note: 
The challenge is solved by using the `strings` command to extract all human-readable text from the binary or mixed-content file `data.txt`, and then piping the output to `grep "="` to filter only the lines containing the `=` character. This approach quickly isolates the readable string preceded by multiple `=` characters, allowing the password to be identified without manually inspecting the entire file.

Directly using `grep "=" data.txt` does not work in this case because `data.txt` contains mostly binary or non-printable characters, and `grep` is designed to search text files. As a result, it may fail to display the human-readable strings or produce garbled output, whereas `strings` extracts only the readable text from the file first, ensuring that grep can reliably filter for lines containing the `=` character.

---


## Bandit 10
### Level Goal
The password for the next level is stored in the file data.txt, which contains base64 encoded data

### Execution Log 
```bash
┌──(incognito㉿kali)-[~]
└─$ ssh -p 2220 bandit10@bandit.labs.overthewire.org
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

backend: gibson-1
bandit10@bandit.labs.overthewire.org's password: 

      ,----..            ,----,          .---.
     /   /   \         ,/   .`|         /. ./|
    /   .     :      ,`   .'  :     .--'.  ' ;
   .   /   ;.  \   ;    ;     /    /__./ \ : |
  .   ;   /  ` ; .'___,/    ,' .--'.  '   \' .
  ;   |  ; \ ; | |    :     | /___/ \ |    ' '
  |   :  | ; | ' ;    |.';  ; ;   \  \;      :
  .   |  ' ' ' : `----'  |  |  \   ;  `      |
  '   ;  \; /  |     '   :  ;   .   \    .\  ;
   \   \  ',  /      |   |  '    \   \   ' \ |
    ;   :    /       '   :  |     :   '  |--"
     \   \ .'        ;   |.'       \   \ ;
  www. `---` ver     '---' he       '---" ire.org


Welcome to OverTheWire!

If you find any problems, please report them to the #wargames channel on
discord or IRC.

--[ Playing the games ]--

  This machine might hold several wargames.
  If you are playing "somegame", then:

    * USERNAMES are somegame0, somegame1, ...
    * Most LEVELS are stored in /somegame/.
    * PASSWORDS for each level are stored in /etc/somegame_pass/.

  Write-access to homedirectories is disabled. It is advised to create a
  working directory with a hard-to-guess name in /tmp/.  You can use the
  command "mktemp -d" in order to generate a random and hard to guess
  directory in /tmp/.  Read-access to both /tmp/ is disabled and to /proc
  restricted so that users cannot snoop on eachother. Files and directories
  with easily guessable or short names will be periodically deleted! The /tmp
  directory is regularly wiped.
  Please play nice:

    * don't leave orphan processes running
    * don't leave exploit-files laying around
    * don't annoy other players
    * don't post passwords or spoilers
    * again, DONT POST SPOILERS!
      This includes writeups of your solution on your blog or website!

--[ Tips ]--

  This machine has a 64bit processor and many security-features enabled
  by default, although ASLR has been switched off.  The following
  compiler flags might be interesting:

    -m32                    compile for 32bit
    -fno-stack-protector    disable ProPolice
    -Wl,-z,norelro          disable relro

  In addition, the execstack tool can be used to flag the stack as
  executable on ELF binaries.

  Finally, network-access is limited for most levels by a local
  firewall.

--[ Tools ]--

 For your convenience we have installed a few useful tools which you can find
 in the following locations:

    * gef (https://github.com/hugsy/gef) in /opt/gef/
    * pwndbg (https://github.com/pwndbg/pwndbg) in /opt/pwndbg/
    * gdbinit (https://github.com/gdbinit/Gdbinit) in /opt/gdbinit/
    * pwntools (https://github.com/Gallopsled/pwntools)
    * radare2 (http://www.radare.org/)

--[ More information ]--

  For more information regarding individual wargames, visit
  http://www.overthewire.org/wargames/

  For support, questions or comments, contact us on discord or IRC.

  Enjoy your stay!

bandit10@bandit:~$ ls
data.txt
bandit10@bandit:~$ base64 -d data.txt
The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
bandit10@bandit:~$ base64 -d data.txt | cat
The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
bandit10@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.
```

### Commands used to solve this level
```bash
base64 -d data.txt
base64 -d data.txt | cat
```

### Note: 
The challenge is solved by using the `base64 -d data.txt` command to decode the contents of `data.txt` from base64 into human-readable text. Decode is what the `-d` parameter stands for, instructing the command to transform the encoded data back to its original form. Displaying the output with `cat` is optional and simply shows the decoded content in the terminal. Other useful options for the base64 command include `-w` to wrap encoded lines at a specified width, `-i` to ignore non-alphabet characters during decoding, and `-e` to explicitly encode data, rather than relying on the default behavior, giving flexibility when working with different base64 formats.

---


## Bandit 11
```bash
┌──(incognito㉿kali)-[~]
└─$ ssh -p 2220 bandit11@bandit.labs.overthewire.org
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

backend: gibson-1
bandit11@bandit.labs.overthewire.org's password: 

      ,----..            ,----,          .---.
     /   /   \         ,/   .`|         /. ./|
    /   .     :      ,`   .'  :     .--'.  ' ;
   .   /   ;.  \   ;    ;     /    /__./ \ : |
  .   ;   /  ` ; .'___,/    ,' .--'.  '   \' .
  ;   |  ; \ ; | |    :     | /___/ \ |    ' '
  |   :  | ; | ' ;    |.';  ; ;   \  \;      :
  .   |  ' ' ' : `----'  |  |  \   ;  `      |
  '   ;  \; /  |     '   :  ;   .   \    .\  ;
   \   \  ',  /      |   |  '    \   \   ' \ |
    ;   :    /       '   :  |     :   '  |--"
     \   \ .'        ;   |.'       \   \ ;
  www. `---` ver     '---' he       '---" ire.org


Welcome to OverTheWire!

If you find any problems, please report them to the #wargames channel on
discord or IRC.

--[ Playing the games ]--

  This machine might hold several wargames.
  If you are playing "somegame", then:

    * USERNAMES are somegame0, somegame1, ...
    * Most LEVELS are stored in /somegame/.
    * PASSWORDS for each level are stored in /etc/somegame_pass/.

  Write-access to homedirectories is disabled. It is advised to create a
  working directory with a hard-to-guess name in /tmp/.  You can use the
  command "mktemp -d" in order to generate a random and hard to guess
  directory in /tmp/.  Read-access to both /tmp/ is disabled and to /proc
  restricted so that users cannot snoop on eachother. Files and directories
  with easily guessable or short names will be periodically deleted! The /tmp
  directory is regularly wiped.
  Please play nice:

    * don't leave orphan processes running
    * don't leave exploit-files laying around
    * don't annoy other players
    * don't post passwords or spoilers
    * again, DONT POST SPOILERS!
      This includes writeups of your solution on your blog or website!

--[ Tips ]--

  This machine has a 64bit processor and many security-features enabled
  by default, although ASLR has been switched off.  The following
  compiler flags might be interesting:

    -m32                    compile for 32bit
    -fno-stack-protector    disable ProPolice
    -Wl,-z,norelro          disable relro

  In addition, the execstack tool can be used to flag the stack as
  executable on ELF binaries.

  Finally, network-access is limited for most levels by a local
  firewall.

--[ Tools ]--

 For your convenience we have installed a few useful tools which you can find
 in the following locations:

    * gef (https://github.com/hugsy/gef) in /opt/gef/
    * pwndbg (https://github.com/pwndbg/pwndbg) in /opt/pwndbg/
    * gdbinit (https://github.com/gdbinit/Gdbinit) in /opt/gdbinit/
    * pwntools (https://github.com/Gallopsled/pwntools)
    * radare2 (http://www.radare.org/)

--[ More information ]--

  For more information regarding individual wargames, visit
  http://www.overthewire.org/wargames/

  For support, questions or comments, contact us on discord or IRC.

  Enjoy your stay!

bandit11@bandit:~$ ls
data.txt
bandit11@bandit:~$ cat data.txt 
Gur cnffjbeq vf 7k16JArUVv5LxVuJfsSVdbbtaHGlw9D4
bandit11@bandit:~$ cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
The password is 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
bandit11@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.
```

---


## Bandit 12
```bash
┌──(incognito㉿kali)-[~]
└─$ ssh -p 2220 bandit12@bandit.labs.overthewire.org
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

backend: gibson-1
bandit12@bandit.labs.overthewire.org's password: 

      ,----..            ,----,          .---.
     /   /   \         ,/   .`|         /. ./|
    /   .     :      ,`   .'  :     .--'.  ' ;
   .   /   ;.  \   ;    ;     /    /__./ \ : |
  .   ;   /  ` ; .'___,/    ,' .--'.  '   \' .
  ;   |  ; \ ; | |    :     | /___/ \ |    ' '
  |   :  | ; | ' ;    |.';  ; ;   \  \;      :
  .   |  ' ' ' : `----'  |  |  \   ;  `      |
  '   ;  \; /  |     '   :  ;   .   \    .\  ;
   \   \  ',  /      |   |  '    \   \   ' \ |
    ;   :    /       '   :  |     :   '  |--"
     \   \ .'        ;   |.'       \   \ ;
  www. `---` ver     '---' he       '---" ire.org


Welcome to OverTheWire!

If you find any problems, please report them to the #wargames channel on
discord or IRC.

--[ Playing the games ]--

  This machine might hold several wargames.
  If you are playing "somegame", then:

    * USERNAMES are somegame0, somegame1, ...
    * Most LEVELS are stored in /somegame/.
    * PASSWORDS for each level are stored in /etc/somegame_pass/.

  Write-access to homedirectories is disabled. It is advised to create a
  working directory with a hard-to-guess name in /tmp/.  You can use the
  command "mktemp -d" in order to generate a random and hard to guess
  directory in /tmp/.  Read-access to both /tmp/ is disabled and to /proc
  restricted so that users cannot snoop on eachother. Files and directories
  with easily guessable or short names will be periodically deleted! The /tmp
  directory is regularly wiped.
  Please play nice:

    * don't leave orphan processes running
    * don't leave exploit-files laying around
    * don't annoy other players
    * don't post passwords or spoilers
    * again, DONT POST SPOILERS!
      This includes writeups of your solution on your blog or website!

--[ Tips ]--

  This machine has a 64bit processor and many security-features enabled
  by default, although ASLR has been switched off.  The following
  compiler flags might be interesting:

    -m32                    compile for 32bit
    -fno-stack-protector    disable ProPolice
    -Wl,-z,norelro          disable relro

  In addition, the execstack tool can be used to flag the stack as
  executable on ELF binaries.

  Finally, network-access is limited for most levels by a local
  firewall.

--[ Tools ]--

 For your convenience we have installed a few useful tools which you can find
 in the following locations:

    * gef (https://github.com/hugsy/gef) in /opt/gef/
    * pwndbg (https://github.com/pwndbg/pwndbg) in /opt/pwndbg/
    * gdbinit (https://github.com/gdbinit/Gdbinit) in /opt/gdbinit/
    * pwntools (https://github.com/Gallopsled/pwntools)
    * radare2 (http://www.radare.org/)

--[ More information ]--

  For more information regarding individual wargames, visit
  http://www.overthewire.org/wargames/

  For support, questions or comments, contact us on discord or IRC.

  Enjoy your stay!

bandit12@bandit:~$ ls
data.txt
bandit12@bandit:~$ file data.txt 
data.txt: ASCII text
bandit12@bandit:~$ cat data.txt
00000000: 1f8b 0808 00da cf69 0203 6461 7461 322e  .......i..data2.
00000010: 6269 6e00 0136 02c9 fd42 5a68 3931 4159  bin..6...BZh91AY
00000020: 2653 5978 ae89 f600 001c 7fff db7d bfef  &SYx.........}..
00000030: 8ff7 f7ff ffc2 ffcd 7cbd 2ee4 dff9 aff3  ........|.......
00000040: ef7b d577 e9f7 adbd dfbb fbff b001 3b30  .{.w..........;0
00000050: 63a0 6806 8326 400d 0031 0000 00d1 a313  c.h..&@..1......
00000060: 2000 001a 034d 1a19 0000 0032 0681 89a6   ....M.....2....
00000070: 9a32 0da9 934c 6847 9220 0034 0346 9a00  .2...LhG. .4.F..
00000080: d340 3462 0006 d4d3 d41a 064d 0308 6868  .@4b.......M..hh
00000090: 0340 1a19 3264 321b 50f5 00c8 01ea 0d00  .@..2d2.P.......
000000a0: 7a80 d00d 030e 9ea1 a3d2 6231 0346 20c4  z.........b1.F .
000000b0: c801 a068 c200 d188 687a 9a00 0340 0000  ...h....hz...@..
000000c0: 0034 0d34 d034 c8c2 34c8 0c9a 3400 0013  .4.4.4..4...4...
000000d0: 6006 9600 30e0 6902 600b 990b ffd0 6e9e  `...0.i.`.....n.
000000e0: a8fc 1813 42c5 2e19 2331 c580 7009 1956  ....B...#1..p..V
000000f0: 3156 0e5f 2ff4 d9a9 12f3 f97c 4c4b 0127  1V._/......|LK.'
00000100: 5a43 cdd9 3ec3 c4e5 eedb 7357 7d5a 3054  ZC..>.....sW}Z0T
00000110: 1d24 7fc5 562f 1a86 8ac8 5a19 7890 125c  .$..V/....Z.x..\
00000120: 103b 6d80 fbf1 fdec 2d7e 1838 e1ed 3dae  .;m.....-~.8..=.
00000130: 47d8 5023 073f 3a1b 2c10 6784 9c90 b67d  G.P#.?:.,.g....}
00000140: 3ba5 3515 9a10 7002 2eca c60c 38c7 3ccd  ;.5...p.....8.<.
00000150: e3fd 7af3 a647 086c 5e7f 5bd0 d526 128f  ..z..G.l^.[..&..
00000160: ace4 2bd0 d744 e9cf 5182 8886 4a26 a938  ..+..D..Q...J&.8
00000170: f860 c668 c5ad 8444 98e4 cbd8 ca6f c22b  .`.h...D.....o.+
00000180: afa2 3cdc c540 03b2 387b 4309 c9a0 913a  ..<..@..8{C....:
00000190: a9c5 0d39 dab7 9544 b83b dca3 9466 5020  ...9...D.;...fP 
000001a0: 2a3f 3bc8 552d 426f e422 7a99 2cd0 ed62  *?;.U-Bo."z.,..b
000001b0: ac90 0bac 1a3e fbb2 a3e3 5a34 a0c8 785f  .....>....Z4..x_
000001c0: d2a9 3a57 a554 35a8 76df 18da f622 21f6  ..:W.T5.v...."!.
000001d0: b3f0 56ab 68ad 6825 3926 9491 60a1 f979  ..V.h.h%9&..`..y
000001e0: 6203 ad30 0482 1684 d9f3 c0cf 68ac 63b9  b..0........h.c.
000001f0: ed20 ea11 7fb6 78ad 4366 f218 2549 d2b8  . ....x.Cf..%I..
00000200: 0268 5f2b 0678 85de 283b 3807 9aba 6e2c  .h_+.x..(;8...n,
00000210: 1061 04c0 0007 85f4 511e e974 bcc6 cfc8  .a......Q..t....
00000220: 3889 3265 ff28 c2f9 2f2a d163 290b bb90  8.2e.(../*.c)...
00000230: 5274 43e0 0054 86d7 cce2 5933 7dd3 1e95  RtC..T....Y3}...
00000240: 4fb8 4103 fe2e e48a 70a1 20f1 5d13 ecd3  O.A.....p. .]...
00000250: 2afd bb36 0200 00                        *..6...
bandit12@bandit:~$ xxd -r data.txt > data
-bash: data: Permission denied
bandit12@bandit:~$ tempdir=$(mktemp -d)
bandit12@bandit:~$ echo "Working in $tempdir"
Working in /tmp/tmp.wKhwLRyQc9
bandit12@bandit:~$ cp data.txt "$tempdir/"
bandit12@bandit:~$ cd "$tempdir"
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ ls
data.txt
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ xxd -r data.txt > data
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ ls
data  data.txt
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ file data
data: gzip compressed data, was "data2.bin", last modified: Fri Apr  3 15:17:20 2026, max compression, from Unix, original size modulo 2^32 566
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ cp data data.gz
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ rm data
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ ls
data.gz  data.txt
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ gunzip data.gz 
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ ls
data  data.txt
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ file data
data: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ cp data data.bz2
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ rm data
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ ls
data.bz2  data.txt
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ bunzip2 data.bz2 
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ ls
data  data.txt
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ file data
data: gzip compressed data, was "data4.bin", last modified: Fri Apr  3 15:17:20 2026, max compression, from Unix, original size modulo 2^32 20480
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ cp data data.gz
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ rm data
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ ls
data.gz  data.txt
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ gunzip data.gz 
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ ls
data  data.txt
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ file data
data: POSIX tar archive (GNU)
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ cp data data.tar
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ rm data
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ ls
data.tar  data.txt
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ tar xf data.tar 
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ ls
data5.bin  data.tar  data.txt
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ file data5.bin 
data5.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ cp data5.bin data5.tar
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ rm data5.bin 
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ rm data.tar
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ ls
data5.tar  data.txt
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ tar xf data5.tar 
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ ls
data5.tar  data6.bin  data.txt
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ file data6.bin 
data6.bin: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ cp data6.bin data6.bz2
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ rm data5.tar 
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ rm data6.bin 
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ ls
data6.bz2  data.txt
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ bunzip2 data6.bz2 
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ ls
data6  data.txt
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ file data6
data6: POSIX tar archive (GNU)
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ cp data6 data6.tar
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ rm data6
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ ls
data6.tar  data.txt
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ tar xf data6.tar 
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ ls
data6.tar  data8.bin  data.txt
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ file data8.bin 
data8.bin: gzip compressed data, was "data9.bin", last modified: Fri Apr  3 15:17:20 2026, max compression, from Unix, original size modulo 2^32 49
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ cp data8.bin data8.gz
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ rm data6.tar 
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ rm data8.bin 
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ ls
data8.gz  data.txt
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ gunzip data8.gz 
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ ls
data8  data.txt
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ file data8
data8: ASCII text
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ cat data8
The password is FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ rm -r "$tempdir"
bandit12@bandit:/tmp/tmp.wKhwLRyQc9$ cd
bandit12@bandit:~$ ls
data.txt
bandit12@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.
```

---


## Bandit 13
```bash
┌──(incognito㉿kali)-[~]
└─$ ssh -p 2220 bandit13@bandit.labs.overthewire.org                 
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

backend: gibson-1
bandit13@bandit.labs.overthewire.org's password: 

      ,----..            ,----,          .---.
     /   /   \         ,/   .`|         /. ./|
    /   .     :      ,`   .'  :     .--'.  ' ;
   .   /   ;.  \   ;    ;     /    /__./ \ : |
  .   ;   /  ` ; .'___,/    ,' .--'.  '   \' .
  ;   |  ; \ ; | |    :     | /___/ \ |    ' '
  |   :  | ; | ' ;    |.';  ; ;   \  \;      :
  .   |  ' ' ' : `----'  |  |  \   ;  `      |
  '   ;  \; /  |     '   :  ;   .   \    .\  ;
   \   \  ',  /      |   |  '    \   \   ' \ |
    ;   :    /       '   :  |     :   '  |--"
     \   \ .'        ;   |.'       \   \ ;
  www. `---` ver     '---' he       '---" ire.org


Welcome to OverTheWire!

If you find any problems, please report them to the #wargames channel on
discord or IRC.

--[ Playing the games ]--

  This machine might hold several wargames.
  If you are playing "somegame", then:

    * USERNAMES are somegame0, somegame1, ...
    * Most LEVELS are stored in /somegame/.
    * PASSWORDS for each level are stored in /etc/somegame_pass/.

  Write-access to homedirectories is disabled. It is advised to create a
  working directory with a hard-to-guess name in /tmp/.  You can use the
  command "mktemp -d" in order to generate a random and hard to guess
  directory in /tmp/.  Read-access to both /tmp/ is disabled and to /proc
  restricted so that users cannot snoop on eachother. Files and directories
  with easily guessable or short names will be periodically deleted! The /tmp
  directory is regularly wiped.
  Please play nice:

    * don't leave orphan processes running
    * don't leave exploit-files laying around
    * don't annoy other players
    * don't post passwords or spoilers
    * again, DONT POST SPOILERS!
      This includes writeups of your solution on your blog or website!

--[ Tips ]--

  This machine has a 64bit processor and many security-features enabled
  by default, although ASLR has been switched off.  The following
  compiler flags might be interesting:

    -m32                    compile for 32bit
    -fno-stack-protector    disable ProPolice
    -Wl,-z,norelro          disable relro

  In addition, the execstack tool can be used to flag the stack as
  executable on ELF binaries.

  Finally, network-access is limited for most levels by a local
  firewall.

--[ Tools ]--

 For your convenience we have installed a few useful tools which you can find
 in the following locations:

    * gef (https://github.com/hugsy/gef) in /opt/gef/
    * pwndbg (https://github.com/pwndbg/pwndbg) in /opt/pwndbg/
    * gdbinit (https://github.com/gdbinit/Gdbinit) in /opt/gdbinit/
    * pwntools (https://github.com/Gallopsled/pwntools)
    * radare2 (http://www.radare.org/)

--[ More information ]--

  For more information regarding individual wargames, visit
  http://www.overthewire.org/wargames/

  For support, questions or comments, contact us on discord or IRC.

  Enjoy your stay!

bandit13@bandit:~$ ls
HINT  sshkey.private
bandit13@bandit:~$ cat HINT 
If you have trouble with this level, note the following:

1) As for all other levels, this level has a website with information:
   https://overthewire.org/wargames/bandit/bandit14.html
2) No, the level is not broken. To verify, see:
   https://status.overthewire.org/
3) The current version of OverTheWire prevents logging in from one
   level to another via localhost. Log out, and see 1)
4) If you get errors, read the error message on your screen.
   We mean it!
bandit13@bandit:~$ cat sshkey.private 
-----BEGIN RSA PRIVATE KEY-----
(***private key content***)
-----END RSA PRIVATE KEY-----
bandit13@bandit:~$ cat /etc/bandit_pass/bandit14
cat: /etc/bandit_pass/bandit14: Permission denied
bandit13@bandit:~$ ls -lia /etc/bandit_pass/bandit14
331817 -r-------- 1 bandit14 bandit14 33 Apr  3 15:17 /etc/bandit_pass/bandit14
bandit13@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.
                                                                                                                                                                       
┌──(incognito㉿kali)-[~]
└─$ mkdir otw_test
                                                                                                                                                                       
┌──(incognito㉿kali)-[~]
└─$ cd otw_test
                                                                                                                                                                       
┌──(incognito㉿kali)-[~/otw_test]
└─$ vi sshkey.private
                                                                                                                                                                       
┌──(incognito㉿kali)-[~/otw_test]
└─$ cat sshkey.private
-----BEGIN RSA PRIVATE KEY-----
(***private key content***)
-----END RSA PRIVATE KEY-----
                                                                                                                                                                       
┌──(incognito㉿kali)-[~/otw_test]
└─$ ssh -p 2220 bandit14@bandit.labs.overthewire.org -i sshkey.private

                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

backend: gibson-1
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@         WARNING: UNPROTECTED PRIVATE KEY FILE!          @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
Permissions 0664 for 'sshkey.private' are too open.
It is required that your private key files are NOT accessible by others.
This private key will be ignored.
Load key "sshkey.private": bad permissions
bandit14@bandit.labs.overthewire.org's password: 

                                                                                                                                                                       
┌──(incognito㉿kali)-[~/otw_test]
└─$ chmod 600 sshkey.private
                                                                                                                                                                       
┌──(incognito㉿kali)-[~/otw_test]
└─$ ssh -p 2220 bandit14@bandit.labs.overthewire.org -i sshkey.private
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

backend: gibson-1

      ,----..            ,----,          .---.
     /   /   \         ,/   .`|         /. ./|
    /   .     :      ,`   .'  :     .--'.  ' ;
   .   /   ;.  \   ;    ;     /    /__./ \ : |
  .   ;   /  ` ; .'___,/    ,' .--'.  '   \' .
  ;   |  ; \ ; | |    :     | /___/ \ |    ' '
  |   :  | ; | ' ;    |.';  ; ;   \  \;      :
  .   |  ' ' ' : `----'  |  |  \   ;  `      |
  '   ;  \; /  |     '   :  ;   .   \    .\  ;
   \   \  ',  /      |   |  '    \   \   ' \ |
    ;   :    /       '   :  |     :   '  |--"
     \   \ .'        ;   |.'       \   \ ;
  www. `---` ver     '---' he       '---" ire.org


Welcome to OverTheWire!

If you find any problems, please report them to the #wargames channel on
discord or IRC.

--[ Playing the games ]--

  This machine might hold several wargames.
  If you are playing "somegame", then:

    * USERNAMES are somegame0, somegame1, ...
    * Most LEVELS are stored in /somegame/.
    * PASSWORDS for each level are stored in /etc/somegame_pass/.

  Write-access to homedirectories is disabled. It is advised to create a
  working directory with a hard-to-guess name in /tmp/.  You can use the
  command "mktemp -d" in order to generate a random and hard to guess
  directory in /tmp/.  Read-access to both /tmp/ is disabled and to /proc
  restricted so that users cannot snoop on eachother. Files and directories
  with easily guessable or short names will be periodically deleted! The /tmp
  directory is regularly wiped.
  Please play nice:

    * don't leave orphan processes running
    * don't leave exploit-files laying around
    * don't annoy other players
    * don't post passwords or spoilers
    * again, DONT POST SPOILERS!
      This includes writeups of your solution on your blog or website!

--[ Tips ]--

  This machine has a 64bit processor and many security-features enabled
  by default, although ASLR has been switched off.  The following
  compiler flags might be interesting:

    -m32                    compile for 32bit
    -fno-stack-protector    disable ProPolice
    -Wl,-z,norelro          disable relro

  In addition, the execstack tool can be used to flag the stack as
  executable on ELF binaries.

  Finally, network-access is limited for most levels by a local
  firewall.

--[ Tools ]--

 For your convenience we have installed a few useful tools which you can find
 in the following locations:

    * gef (https://github.com/hugsy/gef) in /opt/gef/
    * pwndbg (https://github.com/pwndbg/pwndbg) in /opt/pwndbg/
    * gdbinit (https://github.com/gdbinit/Gdbinit) in /opt/gdbinit/
    * pwntools (https://github.com/Gallopsled/pwntools)
    * radare2 (http://www.radare.org/)

--[ More information ]--

  For more information regarding individual wargames, visit
  http://www.overthewire.org/wargames/

  For support, questions or comments, contact us on discord or IRC.

  Enjoy your stay!

bandit14@bandit:~$ ls
bandit14@bandit:~$ cat /etc/bandit_pass/bandit14
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
```
(continue to the Bandit 14 task ...)


---


## Bandit 14
```bash
bandit14@bandit:~$ nc localhost 30000
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
Correct!
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo

^C
bandit14@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.
```

---


## Bandit 15
```bash

```

---


## Bandit 16
```bash

```

---


## Bandit 17
```bash

```

---


## Bandit 18
```bash

```

---


## Bandit 19 
```bash

```

---


## Bandit 20
```bash

```

---


## Bandit 21
```bash

```

---


## Bandit 22
```bash

```

---


## Bandit 23
```bash

```

---


## Bandit 24
```bash

```

---


## Bandit 25
```bash

```

---


## Bandit 26
```bash

```

---


## Bandit 27
```bash

```

---


## Bandit 28
```bash

```

---


## Bandit 29 
```bash

```

---


## Bandit 30
```bash

```

---

