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

To determine if content is base64 encoded, first check if it contains only the valid base64 characters, which include uppercase and lowercase letters, numbers, + and /, and possibly = at the end as padding, and ensure the total length is a multiple of four characters. Decode it with `base64 -d` to see if it produces readable text or valid binary data, since failed decoding often indicates it is not base64. Base64 (unlike ROT13 or other simple ciphers) does not alter the character set outside these allowed symbols, so text containing unusual symbols or letters beyond the base64 range is likely not base64, making character set and successful decoding reliable ways to differentiate between base64 and other encodings.

---


## Bandit 11
### Level Goal
The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

### Execution Log
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

### Commands used to solve this level
```bash
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```

### Note: 
The challenge is solved using a ROT13 cipher, which shifts each letter 13 positions in the alphabet while leaving numbers and symbols unchanged. The command `cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'` reads the contents of `data.txt` and passes it to the `tr` command, which translates all uppercase and lowercase letters according to the ROT13 mapping, effectively decoding the text to reveal the password. This approach quickly converts the encoded message back into human-readable form without altering any non-letter characters.

---


## Bandit 12
### Level Goal
The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work. Use mkdir with a hard to guess directory name. Or better, use the command “mktemp -d”. Then copy the datafile using cp, and rename it using mv (read the manpages!)

### Execution Log 
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

### Commands used to solve this level
```bash
tempdir=$(mktemp -d)
echo "Working in $tempdir"
cp data.txt "$tempdir/"
cd "$tempdir"
xxd -r data.txt > data

file data
gzip → gunzip data.gz
bzip2 → bunzip2 data.bz2
tar archive → tar xf data.tar
zip archive → unzip data.zip

rm -r "$tempdir"
```

### Note: 
This challenge is solved by first creating a temporary working directory using `mktemp -d`, which allows files to be manipulated safely without running into permission issues. The original data.txt contains a hexdump of a repeatedly compressed file, so `xxd -r` is used to convert the hexadecimal representation back into binary format that can be processed by standard compression and archive tools. The `file` command is then applied at each stage to identify the type of compression or archive, guiding the use of the correct decompression tool, such as `gunzip` for gzip files, `bunzip2` for bzip2 files, and `tar xf` for tar archives. This process is repeated iteratively, switching between gzip, bzip2, and tar as needed, until the final file is plain ASCII text containing the password. After retrieving the password, the temporary directory is removed with `rm -r` to clean up all intermediate files.

A hexdump is a textual representation of a file’s raw binary data in hexadecimal format, often with an ASCII column for readability. You can usually identify a hexdump by looking for sequences of hexadecimal digits (0–9, a–f) alongside offsets when viewing the file with commands like `cat` or in a text editor. It is necessary to convert a hexdump back into binary using `xxd -r` because compression and archive tools require the actual binary data, not the textual hexadecimal form.

Common compression and archive formats encountered in this challenge include gzip files (.gz), bzip2 files (.bz2), tar archives (.tar), and zip files (.zip). Each format requires its corresponding tool to decompress correctly, so using the wrong tool on a mismatched extension, such as attempting `gunzip` on a `.tar` file, will fail. The `rm -r` command is used to remove directories and all of their contents recursively, where the `-r` option stands for “recursive,” ensuring that every file and subdirectory inside the specified directory is deleted along with the directory itself.


---


## Bandit 13
### Level Goal
The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Look at the commands that logged you into previous bandit levels, and find out how to use the key for this level.

### Execution Log 
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
bandit14@bandit:~$ 
```
(continue to the Bandit 14 task ...)

### Commands used to solve this level
`ls` – to list files in the current directory.
`cat HINT` – to read the hint provided for the level.
`cat sshkey.private` – to view the content of the private SSH key.
`cat /etc/bandit_pass/bandit14` – attempted to read the next level’s password, which fails due to permissions.
`ls -lia /etc/bandit_pass/bandit14` – to check ownership and permissions of the password file.
`mkdir otw_test and cd otw_test` – to create and move into a local working directory for the key.
`vi sshkey.private` – to create or save the SSH private key file locally.
`ssh -p 2220 bandit14@bandit.labs.overthewire.org -i sshkey.private` – to attempt logging in using the private key.
`chmod 600 sshkey.private` – to fix permissions of the private key so SSH will accept it.
`ssh -p 2220 bandit14@bandit.labs.overthewire.org -i sshkey.private` – successfully log in with the key.
`cat /etc/bandit_pass/bandit14` – to read the password for the next level.

### Note: 
This challenge is solved by recognizing that the next level’s password is inaccessible directly due to file permissions and that a private SSH key is provided instead. First, you save the private key locally in a safe directory and check its contents. SSH refuses to use the key if it has overly permissive file permissions, so `chmod 600` is applied to make it readable only by the owner. Then, use SSH with the `-i` option to specify the private key and `-p 2220` for the non-standard port to log in as the user bandit14. Once logged in, the password for bandit14 can be read from `/etc/bandit_pass/bandit14`, completing the challenge.

This approach demonstrates how private SSH keys allow secure login to accounts without knowing the password, while also highlighting the importance of correct file permissions for security.

---


## Bandit 14
### Level Goal
The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.

### Execution Log 
(continue from Bandit 13 task)
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

### Commands used to solve this level
```bash
nc localhost 30000
```

### Note: 
This challenge is solved by understanding that the next level’s password is provided by a service running `locally` on the Bandit server on `port 30000`. You first log in as `bandit14` and use the `nc` (netcat) command to connect to localhost at that port: `nc localhost 30000`. Netcat establishes a simple TCP connection to the service, allowing you to submit the password of the current level directly into the session. The service then responds with “Correct!” followed by the password for the next level. This works because the service is designed to authenticate the current password and return the next one, and using netcat is a straightforward way to interact with such TCP-based services locally without needing a browser or complex client.

Netcat is a versatile command-line networking tool that can read and write data across TCP or UDP connections, making it a “Swiss Army knife” for network communication. It can test connections, transfer files, listen on ports, or act as a simple server. Sometimes, `ncat` is used instead of `nc`. `ncat` is part of the Nmap suite and is a modernized version with extra features like SSL support, IPv6, and better security defaults. For simple tasks like connecting to a port and sending text, `nc` and `ncat` function almost identically, and people choose one or the other based on availability or additional features needed.


---


## Bandit 15
### Level Goal
The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL/TLS encryption.
Helpful note: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage.

### Execution Log 
```bash
┌──(incognito㉿kali)-[~]
└─$ ssh -p 2220 bandit15@bandit.labs.overthewire.org                  
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

backend: gibson-0
bandit15@bandit.labs.overthewire.org's password: 


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

bandit15@bandit:~$ echo "8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo" | openssl s_client -connect localhost:30001 -ign_eof
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = SnakeOil
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = SnakeOil
verify return:1
---
Certificate chain
 0 s:CN = SnakeOil
   i:CN = SnakeOil
   a:PKEY: rsaEncryption, 4096 (bit); sigalg: RSA-SHA256
   v:NotBefore: Jun 10 03:59:50 2024 GMT; NotAfter: Jun  8 03:59:50 2034 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIFBzCCAu+gAwIBAgIUBLz7DBxA0IfojaL/WaJzE6Sbz7cwDQYJKoZIhvcNAQEL
BQAwEzERMA8GA1UEAwwIU25ha2VPaWwwHhcNMjQwNjEwMDM1OTUwWhcNMzQwNjA4
MDM1OTUwWjATMREwDwYDVQQDDAhTbmFrZU9pbDCCAiIwDQYJKoZIhvcNAQEBBQAD
ggIPADCCAgoCggIBANI+P5QXm9Bj21FIPsQqbqZRb5XmSZZJYaam7EIJ16Fxedf+
jXAv4d/FVqiEM4BuSNsNMeBMx2Gq0lAfN33h+RMTjRoMb8yBsZsC063MLfXCk4p+
09gtGP7BS6Iy5XdmfY/fPHvA3JDEScdlDDmd6Lsbdwhv93Q8M6POVO9sv4HuS4t/
jEjr+NhE+Bjr/wDbyg7GL71BP1WPZpQnRE4OzoSrt5+bZVLvODWUFwinB0fLaGRk
GmI0r5EUOUd7HpYyoIQbiNlePGfPpHRKnmdXTTEZEoxeWWAaM1VhPGqfrB/Pnca+
vAJX7iBOb3kHinmfVOScsG/YAUR94wSELeY+UlEWJaELVUntrJ5HeRDiTChiVQ++
wnnjNbepaW6shopybUF3XXfhIb4NvwLWpvoKFXVtcVjlOujF0snVvpE+MRT0wacy
tHtjZs7Ao7GYxDz6H8AdBLKJW67uQon37a4MI260ADFMS+2vEAbNSFP+f6ii5mrB
18cY64ZaF6oU8bjGK7BArDx56bRc3WFyuBIGWAFHEuB948BcshXY7baf5jjzPmgz
mq1zdRthQB31MOM2ii6vuTkheAvKfFf+llH4M9SnES4NSF2hj9NnHga9V08wfhYc
x0W6qu+S8HUdVF+V23yTvUNgz4Q+UoGs4sHSDEsIBFqNvInnpUmtNgcR2L5PAgMB
AAGjUzBRMB0GA1UdDgQWBBTPo8kfze4P9EgxNuyk7+xDGFtAYzAfBgNVHSMEGDAW
gBTPo8kfze4P9EgxNuyk7+xDGFtAYzAPBgNVHRMBAf8EBTADAQH/MA0GCSqGSIb3
DQEBCwUAA4ICAQAKHomtmcGqyiLnhziLe97Mq2+Sul5QgYVwfx/KYOXxv2T8ZmcR
Ae9XFhZT4jsAOUDK1OXx9aZgDGJHJLNEVTe9zWv1ONFfNxEBxQgP7hhmDBWdtj6d
taqEW/Jp06X+08BtnYK9NZsvDg2YRcvOHConeMjwvEL7tQK0m+GVyQfLYg6jnrhx
egH+abucTKxabFcWSE+Vk0uJYMqcbXvB4WNKz9vj4V5Hn7/DN4xIjFko+nREw6Oa
/AUFjNnO/FPjap+d68H1LdzMH3PSs+yjGid+6Zx9FCnt9qZydW13Miqg3nDnODXw
+Z682mQFjVlGPCA5ZOQbyMKY4tNazG2n8qy2famQT3+jF8Lb6a4NGbnpeWnLMkIu
jWLWIkA9MlbdNXuajiPNVyYIK9gdoBzbfaKwoOfSsLxEqlf8rio1GGcEV5Hlz5S2
txwI0xdW9MWeGWoiLbZSbRJH4TIBFFtoBG0LoEJi0C+UPwS8CDngJB4TyrZqEld3
rH87W+Et1t/Nepoc/Eoaux9PFp5VPXP+qwQGmhir/hv7OsgBhrkYuhkjxZ8+1uk7
tUWC/XM0mpLoxsq6vVl3AJaJe1ivdA9xLytsuG4iv02Juc593HXYR8yOpow0Eq2T
U5EyeuFg5RXYwAPi7ykw1PW7zAPL4MlonEVz+QXOSx6eyhimp1VZC11SCg==
-----END CERTIFICATE-----
subject=CN = SnakeOil
issuer=CN = SnakeOil
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 2103 bytes and written 373 bytes
Verification error: self-signed certificate
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 4096 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 18 (self-signed certificate)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 8DFC4FD42AF43DA418C6B4152ED4A900F41C058980372B675C94D72A52D08BDB
    Session-ID-ctx: 
    Resumption PSK: 6F600788E27B40BA52456F98FE424E4714A9AE6EB303B4A64A04EAF81AD32047D81006AC1A446E30FFBFFC4DF2A23345
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 300 (seconds)
    TLS session ticket:
    0000 - 56 c8 74 c7 4e 15 76 27-f6 8a 4a d4 f1 9c d6 e1   V.t.N.v'..J.....
    0010 - ca 64 9e 6c c9 b6 12 ec-1c 94 d9 86 79 b4 5a 88   .d.l........y.Z.
    0020 - 29 12 bb 7f 02 cb f8 a6-08 a6 1a 88 d4 b0 be 92   )...............
    0030 - 8d b1 e4 72 81 2b 12 a4-2d 06 66 db 79 52 9b 3f   ...r.+..-.f.yR.?
    0040 - e0 cd 1f c6 39 f0 51 26-8e 62 88 9c 67 50 38 e2   ....9.Q&.b..gP8.
    0050 - bc 10 7d 96 9d c2 2a 75-36 d1 5f af 10 69 88 4f   ..}...*u6._..i.O
    0060 - 2a 54 06 bb 99 01 7a 45-44 1b 11 d7 38 35 6f 8c   *T....zED...85o.
    0070 - 01 26 0f 37 51 ca cd c2-8d 36 f6 9f 12 2b 53 9e   .&.7Q....6...+S.
    0080 - 17 b4 85 6a 7f 35 8d e5-c8 c0 82 09 fe 9d 52 2b   ...j.5........R+
    0090 - 5c ca fa 7a 90 87 ee 0f-f3 4b 6c ec b8 ac 19 96   \..z.....Kl.....
    00a0 - 41 27 b3 67 87 54 8b d3-69 ce dc ec ed 08 df 0c   A'.g.T..i.......
    00b0 - 10 90 9c 67 e4 31 b8 49-1b d3 a6 df 8d 1f 5b df   ...g.1.I......[.
    00c0 - 40 d5 30 bb 26 aa 3f 9b-e2 44 a4 f6 c1 06 4c 40   @.0.&.?..D....L@
    00d0 - eb da 13 ca 74 13 69 c2-dd d3 02 8c ae 4f e3 87   ....t.i......O..

    Start Time: 1775744340
    Timeout   : 7200 (sec)
    Verify return code: 18 (self-signed certificate)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: FE84E241B606BBA970E5354691DD90F1EF5589EB4BA1032A52F71B087E2117C1
    Session-ID-ctx: 
    Resumption PSK: E54B0B2E69ABDC17E702998A21F37F455B8466E099F82A9803D165E2FA72CE538D96398E94F2ACAB6AEE3C7BA3E9F2FE
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 300 (seconds)
    TLS session ticket:
    0000 - 56 c8 74 c7 4e 15 76 27-f6 8a 4a d4 f1 9c d6 e1   V.t.N.v'..J.....
    0010 - 05 70 2c 93 1e e7 f9 11-7f a9 54 65 4f 0f 92 e9   .p,.......TeO...
    0020 - 5d c9 2b bc 2d 2e ff 1a-a7 c5 df 5d 19 d7 16 28   ].+.-......]...(
    0030 - 0b 3d f8 8e 28 0b 67 b9-0a ed f7 b4 b1 ab dd cf   .=..(.g.........
    0040 - 0e f1 60 5d 15 3f 7d 43-fb 31 3e a5 b4 f6 d9 c7   ..`].?}C.1>.....
    0050 - 91 48 de 66 c9 87 b2 43-7e 9b 45 7f bd b3 4e a6   .H.f...C~.E...N.
    0060 - 8b d5 fd 27 58 3e 69 0a-4c 4a a8 70 b3 db b1 18   ...'X>i.LJ.p....
    0070 - e9 73 ee 4c bf d9 5e eb-61 f0 a0 0d ed 7a 66 01   .s.L..^.a....zf.
    0080 - 9b 21 11 39 32 05 c6 d5-24 7d 57 e5 3b be 3e b2   .!.92...$}W.;.>.
    0090 - 1d fd b7 f6 d0 df 5e d8-b6 92 58 4c 94 63 cc 8c   ......^...XL.c..
    00a0 - b9 e3 31 2e 60 52 08 a2-f2 7d 67 9a e6 7a dc b4   ..1.`R...}g..z..
    00b0 - df cf de fd 39 58 22 8b-c4 0c f9 31 81 be ca 76   ....9X"....1...v
    00c0 - 2c 8a 61 01 a6 59 98 23-4d 11 7d cf 64 f9 cc c4   ,.a..Y.#M.}.d...
    00d0 - 77 e2 20 1e 49 79 eb 6d-5c a3 af 66 fc 0a ea 14   w. .Iy.m\..f....

    Start Time: 1775744340
    Timeout   : 7200 (sec)
    Verify return code: 18 (self-signed certificate)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
Correct!
kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx

closed
bandit15@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.
```

### Commands used to solve this level
`echo "8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo"` – This simply prints the current level password (or the input string) to standard output.
The pipe (|) then sends this string as input to the next command.
`openssl s_client` – This is a tool from OpenSSL used to establish SSL/TLS connections to a server. It’s often used to test or interact with encrypted services over TCP.
`-connect localhost:30001` – This tells s_client to connect to the service running on your local machine (localhost) at port 30001.
`-ign_eof` – This is crucial. By default, s_client closes the connection when it receives an EOF (End Of File) signal from standard input. Without -ign_eof, s_client would terminate immediately after sending the password, potentially before the server sends its full response, resulting in truncated output. Using -ign_eof keeps the connection open until the server actually closes it, ensuring you receive the complete response.

### Note: 
This command sends the password to a local service running on port 30001 over a TLS/SSL connection and ensures that the server’s full response is received by preventing openssl s_client from prematurely closing on EOF. Without -ign_eof, you might see an incomplete password or message because the client would disconnect too early.

---


## Bandit 16
### Level Goal
The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL/TLS and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.
Helpful note: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage.

### Execution Log 
```bash
┌──(incognito㉿kali)-[~]
└─$ ssh -p 2220 bandit16@bandit.labs.overthewire.org
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

backend: gibson-0
bandit16@bandit.labs.overthewire.org's password: 

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

bandit16@bandit:~$ nmap localhost -p31000-32000
Starting Nmap 7.94SVN ( https://nmap.org ) at 2026-04-09 14:29 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00018s latency).
Not shown: 996 closed tcp ports (conn-refused)
PORT      STATE SERVICE
31046/tcp open  unknown
31518/tcp open  unknown
31691/tcp open  unknown
31790/tcp open  unknown
31960/tcp open  unknown

Nmap done: 1 IP address (1 host up) scanned in 0.11 seconds
bandit16@bandit:~$ echo "kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx" | openssl s_client -connect localhost:31046 -ign_eof
CONNECTED(00000003)
4067F0F7FF7F0000:error:0A0000F4:SSL routines:ossl_statem_client_read_transition:unexpected message:../ssl/statem/statem_clnt.c:398:
---
no peer certificate available
---
No client certificate CA names sent
---
SSL handshake has read 293 bytes and written 300 bytes
Verification: OK
---
New, (NONE), Cipher is (NONE)
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 0 (ok)
---
bandit16@bandit:~$ echo "kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx" | openssl s_client -connect localhost:31518 -ign_eof
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = SnakeOil
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = SnakeOil
verify return:1
---
Certificate chain
 0 s:CN = SnakeOil
   i:CN = SnakeOil
   a:PKEY: rsaEncryption, 4096 (bit); sigalg: RSA-SHA256
   v:NotBefore: Jun 10 03:59:50 2024 GMT; NotAfter: Jun  8 03:59:50 2034 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIFBzCCAu+gAwIBAgIUBLz7DBxA0IfojaL/WaJzE6Sbz7cwDQYJKoZIhvcNAQEL
BQAwEzERMA8GA1UEAwwIU25ha2VPaWwwHhcNMjQwNjEwMDM1OTUwWhcNMzQwNjA4
MDM1OTUwWjATMREwDwYDVQQDDAhTbmFrZU9pbDCCAiIwDQYJKoZIhvcNAQEBBQAD
ggIPADCCAgoCggIBANI+P5QXm9Bj21FIPsQqbqZRb5XmSZZJYaam7EIJ16Fxedf+
jXAv4d/FVqiEM4BuSNsNMeBMx2Gq0lAfN33h+RMTjRoMb8yBsZsC063MLfXCk4p+
09gtGP7BS6Iy5XdmfY/fPHvA3JDEScdlDDmd6Lsbdwhv93Q8M6POVO9sv4HuS4t/
jEjr+NhE+Bjr/wDbyg7GL71BP1WPZpQnRE4OzoSrt5+bZVLvODWUFwinB0fLaGRk
GmI0r5EUOUd7HpYyoIQbiNlePGfPpHRKnmdXTTEZEoxeWWAaM1VhPGqfrB/Pnca+
vAJX7iBOb3kHinmfVOScsG/YAUR94wSELeY+UlEWJaELVUntrJ5HeRDiTChiVQ++
wnnjNbepaW6shopybUF3XXfhIb4NvwLWpvoKFXVtcVjlOujF0snVvpE+MRT0wacy
tHtjZs7Ao7GYxDz6H8AdBLKJW67uQon37a4MI260ADFMS+2vEAbNSFP+f6ii5mrB
18cY64ZaF6oU8bjGK7BArDx56bRc3WFyuBIGWAFHEuB948BcshXY7baf5jjzPmgz
mq1zdRthQB31MOM2ii6vuTkheAvKfFf+llH4M9SnES4NSF2hj9NnHga9V08wfhYc
x0W6qu+S8HUdVF+V23yTvUNgz4Q+UoGs4sHSDEsIBFqNvInnpUmtNgcR2L5PAgMB
AAGjUzBRMB0GA1UdDgQWBBTPo8kfze4P9EgxNuyk7+xDGFtAYzAfBgNVHSMEGDAW
gBTPo8kfze4P9EgxNuyk7+xDGFtAYzAPBgNVHRMBAf8EBTADAQH/MA0GCSqGSIb3
DQEBCwUAA4ICAQAKHomtmcGqyiLnhziLe97Mq2+Sul5QgYVwfx/KYOXxv2T8ZmcR
Ae9XFhZT4jsAOUDK1OXx9aZgDGJHJLNEVTe9zWv1ONFfNxEBxQgP7hhmDBWdtj6d
taqEW/Jp06X+08BtnYK9NZsvDg2YRcvOHConeMjwvEL7tQK0m+GVyQfLYg6jnrhx
egH+abucTKxabFcWSE+Vk0uJYMqcbXvB4WNKz9vj4V5Hn7/DN4xIjFko+nREw6Oa
/AUFjNnO/FPjap+d68H1LdzMH3PSs+yjGid+6Zx9FCnt9qZydW13Miqg3nDnODXw
+Z682mQFjVlGPCA5ZOQbyMKY4tNazG2n8qy2famQT3+jF8Lb6a4NGbnpeWnLMkIu
jWLWIkA9MlbdNXuajiPNVyYIK9gdoBzbfaKwoOfSsLxEqlf8rio1GGcEV5Hlz5S2
txwI0xdW9MWeGWoiLbZSbRJH4TIBFFtoBG0LoEJi0C+UPwS8CDngJB4TyrZqEld3
rH87W+Et1t/Nepoc/Eoaux9PFp5VPXP+qwQGmhir/hv7OsgBhrkYuhkjxZ8+1uk7
tUWC/XM0mpLoxsq6vVl3AJaJe1ivdA9xLytsuG4iv02Juc593HXYR8yOpow0Eq2T
U5EyeuFg5RXYwAPi7ykw1PW7zAPL4MlonEVz+QXOSx6eyhimp1VZC11SCg==
-----END CERTIFICATE-----
subject=CN = SnakeOil
issuer=CN = SnakeOil
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 2103 bytes and written 373 bytes
Verification error: self-signed certificate
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 4096 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 18 (self-signed certificate)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: AACFCC11D029DBB2EDA9F15E1C70A12D9A2D5E24363178154CA60076F47A5E4E
    Session-ID-ctx: 
    Resumption PSK: 5EC261F37AC19896CEAE4372392F93003E155A1A526B6C1E3E6D4744B9C346D262548F0E05A3D1EC58D6475180A04D73
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 300 (seconds)
    TLS session ticket:
    0000 - 68 13 9b 72 7d 9a 61 41-77 f8 ea f1 51 42 4f 6f   h..r}.aAw...QBOo
    0010 - 95 69 bb 62 d9 b7 9f 14-3c e5 7a fe 4f 5d 1e e0   .i.b....<.z.O]..
    0020 - b7 a5 55 67 9d 1f ff df-ee 0c 8a 20 4a 71 4a 06   ..Ug....... JqJ.
    0030 - d9 03 75 5e 7c 44 de 99-d3 91 9f f4 a5 7b b5 67   ..u^|D.......{.g
    0040 - 7a c8 d1 8d 2b ad b1 c0-bd 5e 9a 4b e2 9f 54 33   z...+....^.K..T3
    0050 - 97 6f 2e 38 92 ea 25 a9-6a f9 f1 06 47 79 5d 97   .o.8..%.j...Gy].
    0060 - 85 8b be 9b 0e 01 32 ed-23 ec d3 3f 6e 37 a1 8c   ......2.#..?n7..
    0070 - 92 96 97 f2 79 9f 73 a4-2f 44 3d 4b b2 e2 9e 18   ....y.s./D=K....
    0080 - e7 97 86 1e 3b b1 3d 9c-b7 2b ba a4 0f ed 7a 39   ....;.=..+....z9
    0090 - af 7c dc 92 19 57 68 46-a6 a2 b3 b3 11 28 22 2e   .|...WhF.....(".
    00a0 - 51 7c 0e d0 79 78 df fc-ef 4d e4 50 a9 8b 83 0b   Q|..yx...M.P....
    00b0 - 3b c0 c0 e9 3b 19 e2 04-bb f1 70 d3 9f 48 24 a9   ;...;.....p..H$.
    00c0 - 40 ac 3d 0b 75 1a 3a c9-eb 09 98 77 03 2b fc 49   @.=.u.:....w.+.I
    00d0 - ee df a4 1e 86 e0 ec c9-75 b5 3d 97 47 ac 05 46   ........u.=.G..F

    Start Time: 1775745253
    Timeout   : 7200 (sec)
    Verify return code: 18 (self-signed certificate)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: F8EC7127241FE54BC5B5BA6D975405534205E78339DB3373860FFCD89A30EF2F
    Session-ID-ctx: 
    Resumption PSK: DD14017819DEFB17F1E2B8E9AD1D8F5293297FA229F79B18108FBCE7E7965CB213A1691ECCB73386893CCC5F8EEC8EB3
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 300 (seconds)
    TLS session ticket:
    0000 - 68 13 9b 72 7d 9a 61 41-77 f8 ea f1 51 42 4f 6f   h..r}.aAw...QBOo
    0010 - a2 94 5a 7d 44 96 d8 0a-e4 1b 46 e8 e2 7f 7c 0c   ..Z}D.....F...|.
    0020 - 80 f4 82 03 4a df fc d0-3f d4 12 f6 f3 59 76 f0   ....J...?....Yv.
    0030 - aa b0 20 a9 10 80 32 e2-5e 51 78 be f9 f4 f5 1e   .. ...2.^Qx.....
    0040 - 8e 1d b4 e8 45 e6 5b 0e-3b f7 bf a1 b0 2a 25 2f   ....E.[.;....*%/
    0050 - 96 05 4d 35 eb e4 ab 87-77 89 39 87 32 9f 30 a5   ..M5....w.9.2.0.
    0060 - 03 a9 ca 96 94 c9 00 06-69 80 2a f1 bb fe 32 a1   ........i.*...2.
    0070 - f9 df a6 e6 02 69 8d 18-7a 5e d2 8e 84 3b 50 7a   .....i..z^...;Pz
    0080 - ea 14 fe c4 1d 97 78 54-0a 30 83 37 fd 10 7d 65   ......xT.0.7..}e
    0090 - 67 22 dc 7d d2 e5 81 0f-6b 2d 19 da 27 ff 4b 5e   g".}....k-..'.K^
    00a0 - 58 7b d0 45 26 b7 e9 99-35 fd ea 5e ae ea 78 c1   X{.E&...5..^..x.
    00b0 - 3c 41 7d 3e 79 cc b3 4e-d0 f5 36 ca e7 d1 3a 1f   <A}>y..N..6...:.
    00c0 - 00 dd 0d 03 58 69 9e fd-23 ab f3 78 01 cb 49 64   ....Xi..#..x..Id
    00d0 - bd 69 1a 32 7f c1 5f f2-be e1 2f 53 4e d3 76 04   .i.2.._.../SN.v.

    Start Time: 1775745253
    Timeout   : 7200 (sec)
    Verify return code: 18 (self-signed certificate)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx
closed
bandit16@bandit:~$ echo "kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx" | openssl s_client -connect localhost:31691 -ign_eof
CONNECTED(00000003)
4067F0F7FF7F0000:error:0A0000F4:SSL routines:ossl_statem_client_read_transition:unexpected message:../ssl/statem/statem_clnt.c:398:
---
no peer certificate available
---
No client certificate CA names sent
---
SSL handshake has read 293 bytes and written 300 bytes
Verification: OK
---
New, (NONE), Cipher is (NONE)
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 0 (ok)
---
bandit16@bandit:~$ echo "kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx" | openssl s_client -connect localhost:31790 -ign_eof
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = SnakeOil
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = SnakeOil
verify return:1
---
Certificate chain
 0 s:CN = SnakeOil
   i:CN = SnakeOil
   a:PKEY: rsaEncryption, 4096 (bit); sigalg: RSA-SHA256
   v:NotBefore: Jun 10 03:59:50 2024 GMT; NotAfter: Jun  8 03:59:50 2034 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIFBzCCAu+gAwIBAgIUBLz7DBxA0IfojaL/WaJzE6Sbz7cwDQYJKoZIhvcNAQEL
BQAwEzERMA8GA1UEAwwIU25ha2VPaWwwHhcNMjQwNjEwMDM1OTUwWhcNMzQwNjA4
MDM1OTUwWjATMREwDwYDVQQDDAhTbmFrZU9pbDCCAiIwDQYJKoZIhvcNAQEBBQAD
ggIPADCCAgoCggIBANI+P5QXm9Bj21FIPsQqbqZRb5XmSZZJYaam7EIJ16Fxedf+
jXAv4d/FVqiEM4BuSNsNMeBMx2Gq0lAfN33h+RMTjRoMb8yBsZsC063MLfXCk4p+
09gtGP7BS6Iy5XdmfY/fPHvA3JDEScdlDDmd6Lsbdwhv93Q8M6POVO9sv4HuS4t/
jEjr+NhE+Bjr/wDbyg7GL71BP1WPZpQnRE4OzoSrt5+bZVLvODWUFwinB0fLaGRk
GmI0r5EUOUd7HpYyoIQbiNlePGfPpHRKnmdXTTEZEoxeWWAaM1VhPGqfrB/Pnca+
vAJX7iBOb3kHinmfVOScsG/YAUR94wSELeY+UlEWJaELVUntrJ5HeRDiTChiVQ++
wnnjNbepaW6shopybUF3XXfhIb4NvwLWpvoKFXVtcVjlOujF0snVvpE+MRT0wacy
tHtjZs7Ao7GYxDz6H8AdBLKJW67uQon37a4MI260ADFMS+2vEAbNSFP+f6ii5mrB
18cY64ZaF6oU8bjGK7BArDx56bRc3WFyuBIGWAFHEuB948BcshXY7baf5jjzPmgz
mq1zdRthQB31MOM2ii6vuTkheAvKfFf+llH4M9SnES4NSF2hj9NnHga9V08wfhYc
x0W6qu+S8HUdVF+V23yTvUNgz4Q+UoGs4sHSDEsIBFqNvInnpUmtNgcR2L5PAgMB
AAGjUzBRMB0GA1UdDgQWBBTPo8kfze4P9EgxNuyk7+xDGFtAYzAfBgNVHSMEGDAW
gBTPo8kfze4P9EgxNuyk7+xDGFtAYzAPBgNVHRMBAf8EBTADAQH/MA0GCSqGSIb3
DQEBCwUAA4ICAQAKHomtmcGqyiLnhziLe97Mq2+Sul5QgYVwfx/KYOXxv2T8ZmcR
Ae9XFhZT4jsAOUDK1OXx9aZgDGJHJLNEVTe9zWv1ONFfNxEBxQgP7hhmDBWdtj6d
taqEW/Jp06X+08BtnYK9NZsvDg2YRcvOHConeMjwvEL7tQK0m+GVyQfLYg6jnrhx
egH+abucTKxabFcWSE+Vk0uJYMqcbXvB4WNKz9vj4V5Hn7/DN4xIjFko+nREw6Oa
/AUFjNnO/FPjap+d68H1LdzMH3PSs+yjGid+6Zx9FCnt9qZydW13Miqg3nDnODXw
+Z682mQFjVlGPCA5ZOQbyMKY4tNazG2n8qy2famQT3+jF8Lb6a4NGbnpeWnLMkIu
jWLWIkA9MlbdNXuajiPNVyYIK9gdoBzbfaKwoOfSsLxEqlf8rio1GGcEV5Hlz5S2
txwI0xdW9MWeGWoiLbZSbRJH4TIBFFtoBG0LoEJi0C+UPwS8CDngJB4TyrZqEld3
rH87W+Et1t/Nepoc/Eoaux9PFp5VPXP+qwQGmhir/hv7OsgBhrkYuhkjxZ8+1uk7
tUWC/XM0mpLoxsq6vVl3AJaJe1ivdA9xLytsuG4iv02Juc593HXYR8yOpow0Eq2T
U5EyeuFg5RXYwAPi7ykw1PW7zAPL4MlonEVz+QXOSx6eyhimp1VZC11SCg==
-----END CERTIFICATE-----
subject=CN = SnakeOil
issuer=CN = SnakeOil
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 2103 bytes and written 373 bytes
Verification error: self-signed certificate
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 4096 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 18 (self-signed certificate)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 9A9A76FA146F6AA750B6C7659F160A7D7DFAEE89EC8987A557F99C001961B98A
    Session-ID-ctx: 
    Resumption PSK: 69BA40D18F11999C033F849B74A0AAC62FD52FE6423972FCDE717EA4FED92635867497FEE75F700C8EAE2C286FE2A9A7
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 300 (seconds)
    TLS session ticket:
    0000 - 5f 48 6b 1e f4 2f 61 c2-f7 de 09 f9 4c 8c 21 01   _Hk../a.....L.!.
    0010 - 71 ac 0f 9f 5f 0b c0 e3-df 6a 5d dd 7d 20 b0 05   q..._....j].} ..
    0020 - 3f 64 26 c6 e5 75 69 80-26 42 00 95 11 76 35 20   ?d&..ui.&B...v5 
    0030 - 03 43 c7 ae e0 4b 54 da-33 6f 49 60 bd 44 b9 61   .C...KT.3oI`.D.a
    0040 - 9d 3a ba 4c 2c d4 2f ff-ce a7 96 e4 5a 21 4c 3c   .:.L,./.....Z!L<
    0050 - e5 91 7b bd 9b 59 5c 29-94 d4 3d ae f1 b4 db a2   ..{..Y\)..=.....
    0060 - 3c b5 da 63 af af 93 15-1c e8 3d f0 0f 76 24 b5   <..c......=..v$.
    0070 - 22 85 b9 6d 75 7c c8 95-02 55 02 13 48 e6 42 68   "..mu|...U..H.Bh
    0080 - 25 9a b1 91 c4 49 ca 4b-8c c2 8b c8 8f 87 34 5a   %....I.K......4Z
    0090 - 3f 13 08 fd 24 4e ab 1d-8c cc 5e a9 c5 ee 9e 37   ?...$N....^....7
    00a0 - c6 a9 7e 58 cd 50 07 5a-ac 17 63 c1 df 7c cf 1c   ..~X.P.Z..c..|..
    00b0 - ab 01 75 31 14 95 01 52-aa a9 a9 87 32 98 cc 8a   ..u1...R....2...
    00c0 - 56 4c b7 6c fd 9f d7 21-f1 2d 59 90 74 17 7a f2   VL.l...!.-Y.t.z.
    00d0 - 7f c1 72 57 e8 f4 b8 33-27 f4 36 51 ef 62 a1 9f   ..rW...3'.6Q.b..

    Start Time: 1775745425
    Timeout   : 7200 (sec)
    Verify return code: 18 (self-signed certificate)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: D7EE9A379635B41FB034439005CE8C5AE48DB924B3F716393FD1D3A741BEF2D7
    Session-ID-ctx: 
    Resumption PSK: 1489B6DA11AF62D82DA34FE87FDD616F3E9D31F17E2F34B9325457CE93177F7A576BD0DC7D6A84533A68B63619DF9DE8
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 300 (seconds)
    TLS session ticket:
    0000 - 5f 48 6b 1e f4 2f 61 c2-f7 de 09 f9 4c 8c 21 01   _Hk../a.....L.!.
    0010 - b9 1a 81 5d f9 ef 77 93-65 52 d7 ba bd 4c c7 78   ...]..w.eR...L.x
    0020 - 27 67 04 51 2a a5 c2 3f-68 ca 4c 75 d3 1b e3 24   'g.Q*..?h.Lu...$
    0030 - 0e 23 d6 74 96 a3 ac d5-26 93 e1 72 bb 8c 41 63   .#.t....&..r..Ac
    0040 - 86 68 a4 96 ac 66 86 22-ef 0b 24 bb c3 72 c2 46   .h...f."..$..r.F
    0050 - b6 94 ef b7 53 de 15 90-90 ec e3 e4 ea df c5 35   ....S..........5
    0060 - 73 aa e7 73 38 51 13 49-c2 3e aa 74 16 b2 37 92   s..s8Q.I.>.t..7.
    0070 - 7e d3 d6 c2 47 3d 72 51-09 2c ac 95 fc 30 52 13   ~...G=rQ.,...0R.
    0080 - b5 9a 5d bb b7 2b b6 f8-7b ba a2 c1 5e 3a 86 51   ..]..+..{...^:.Q
    0090 - 82 4c 23 d1 6d 19 3b d1-fc b3 71 54 01 c2 1c 5b   .L#.m.;...qT...[
    00a0 - 28 a4 a0 e9 29 de 5a c1-19 d9 de 90 10 f0 19 18   (...).Z.........
    00b0 - d5 9c 43 cd 02 a1 5e ce-ff 34 b9 0e 1f 3f b3 f2   ..C...^..4...?..
    00c0 - 25 ea 60 90 b3 09 91 c8-86 38 0d 26 09 a5 18 dd   %.`......8.&....
    00d0 - dd 23 f7 7e fb 1a 78 dc-44 ef 66 54 00 a8 64 3e   .#.~..x.D.fT..d>

    Start Time: 1775745425
    Timeout   : 7200 (sec)
    Verify return code: 18 (self-signed certificate)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
Correct!
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----

closed
bandit16@bandit:~$ echo "kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx" | openssl s_client -connect localhost:31960 -ign_eof
CONNECTED(00000003)
4067F0F7FF7F0000:error:0A0000F4:SSL routines:ossl_statem_client_read_transition:unexpected message:../ssl/statem/statem_clnt.c:398:
---
no peer certificate available
---
No client certificate CA names sent
---
SSL handshake has read 293 bytes and written 300 bytes
Verification: OK
---
New, (NONE), Cipher is (NONE)
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 0 (ok)
---
bandit16@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.
```

### Commands used to solve this level
```bash
nmap localhost -p31000-32000
```

### Note: 
This challenge is solved by first identifying which ports in the given range are open and then determining which one is using SSL/TLS to return the correct credentials. The command `nmap localhost -p31000-32000` is used to scan all ports between 31000 and 32000 on the local machine, revealing a few open ports such as 31046, 31518, 31691, 31790, and 31960. After that, each open port is tested using `openssl s_client -connect localhost:<port> -ign_eof` while sending the current password through `echo`, which allows the interaction with SSL-enabled services. Some ports return errors like “unexpected message” because they do not use SSL, while others establish a proper TLS connection and display certificate information, indicating they support SSL. By testing each port, only one of them responds with “Correct!” followed by a private RSA key, which is the required credential for the next level. The `-ign_eof` option is important because it keeps the connection open long enough to receive the full response from the server, ensuring the output is not cut off prematurely.


---


## Bandit 17
### Level Goal
There are 2 files in the homedirectory: passwords.old and passwords.new. The password for the next level is in passwords.new and is the only line that has been changed between passwords.old and passwords.new
NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19

### Execution Log 
```bash
┌──(incognito㉿kali)-[~/otw_test]
└─$ ssh -p 2220 bandit17@bandit.labs.overthewire.org -i sshkey.private
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

backend: gibson-0

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

bandit17@bandit:~$ ls
passwords.new  passwords.old
bandit17@bandit:~$ cat passwords.new
4jfkt9w0OCD4u9WTwtP6He3oGj6nyRZW
ghqT03KUyKhuNoFFWBWuQHR8ooXaGOVR
f0mPuQfxqwfhHtmGDvvhUzNj3RXiMd64
WmCRTbBBhHweWDDFfPi6954SbHQ0paTm
6stNVmrQRZeq63uuenwCetL2xm2nPFAu
bNnD3BUNgnTDhFWwpyy5z7owX1rvFVd5
7knPNoWnTbclDcx8t6EwX2hHXPNnN4LK
fNPlp8qSdSDC4BXAYicP7Zkus99MwBpN
35O5OM6O0KxjAGzNuq3zwKEfYUb4Ighm
dO03ZYE1p55jUiUL8PnD47vkiLAWyzc5
kXaJu5aKqrL8NtiO9ZAx3afEpw2W3QPb
ZI3lzDYUjkGnxigo5rPI02tYTgA45WT3
Ck9nnIUqlWmDcG7PTCuoR37ePMu7whTe
vfATGSOGvnon1RqyBrfsYwRoJJk8xMJ2
JeY3KUzYwUE8xOsgZ0eQqAvur4Oxa5Wu
fHtyL7fgPFfEZmGDOTF08YCgLfIq6wJO
MaEdloWJYo5rjfgSXACUsN0Q7yurBtKh
0PIvCYFLMIdfnSoZgAh1q3G57p41JzBM
uctbsUQM5lHW1YRHeBfSoqCXOIpZC52z
R3FO96VhcSkea0k6hkrGABNw952Fdi1G
PeYCkgHUSvQWIwW86v3qSUg53jugT3lL
qSt0hfwN7h05A3tGqpV1tFvQAvKOEa9l
WxQtBtqGrq8mAeXpUBe3PBxKSzrq6f5C
kzMc9A7vX3CBmhRkqiqqx3BO1qdV78iL
bAn2ieFMRVHy5KAatPpHqjzGQsL7cSZu
35DcAfmhTMoIqBKe6JfozLGFCJ15ylYs
y8WhID6E7yEq5GzmMZUJA3jZts4gWgFJ
MhI2McTkzcwVJn7aQTsCK4Vu3cbI0173
juTtU15kqtMSoELqV2u0x4ZAHoCTGPtp
LiKFgjziWcpGlviOZVZhTvdGNxpKWEx6
O3wYckEzNAymrurGgJckO2JPQE5nttFj
MifV4D2ps0obPQTfMFduViuPxAnSYoK8
GbuqZnveJOoOiHQSStr8eGEwDtCRf2I5
RjnMfYv1rDxkPLYHkCJbK3iFRWu7OKR2
7djYQGyOiH0HTcXehusksqWXxG7Yu8VI
jvcLvLHhMDH3VYuzXhh38xBuiFLGoqSB
BJeZRntooggvwkDrf5RttspvrBLIVang
ZA8Jb6cdO0XLMIWKNv6V3VWAuiZWfC9l
GbeMalDIl63fw0N8bqzfCX87m7MHDDUK
HsCNp4XQst75r0n1xolac4J7Dd8QihaB
aFoOOJevxDDrih3wldX1AFtnB9xAiHBp
x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO
tZtZOCHaAOVbz1xgH0bNXydD9iMHMUk8
q2SDmQDVYZKDmqTS0nmz6SfNbAbxUpYq
cVGft1jxyTruNSPCLpOnHV4maGb5UgDd
9gleP8mmAiDCtrj4OEhUPUB8CB7alenY
5SLnZXa6tw40VznQONKL8ApXSa8AuxQb
6mSiysMKmpeXAfVo38GSsY1CNkFsRQ0X
4xkde2eh85sOrh1Nj9nO4q7yFIMlFOr8
pf8AAn9IgoZwU4PYdEQIz80lBUArJlEL
G5pSQ4N47hnDttLTCaP8a7Xfn3jtndG8
pqdehHrA4zWbrisgwSeHNH6gx8ANNrXi
FpioC18S5Yu5pNQbVEJiAdTtZzs1f1qV
Xi5paoFobo6h4FbinSQt4s7KXvrWUwOR
QFyBWfjHgjjqwk3Pm949SiOLmrm5wUiT
SZhlg1k8RI5pYwjciQEx5XmqwullAcac
g8p9JVqngXrl07eCxIgx6xBAn3vltu2c
MbPvrhbdAdRqbseYT4m69bfbU5G1YOWQ
xdgWwIZi7O4acN8YaayegtcygH5HSa4n
Wlt39PlbJbVFrcPudcsY5t9rPxRtVwjG
tMwDHLvdxKB93Fs21nHZU09RcmwbN4rT
F84EnjuMtnFumFaKiIp1CBtN9puBujcM
YHGy6QsnnJK9SR866TN5ZDjUbYedGqTc
J4jiPKo4SiU0GjqqYIdzKbYKqOMazv0t
7DDKWPlPzbFxjPU95OpT3ZLg1JFZC4dR
8vGHo4H2nFM3ZM5DVQ8eFimJDZfgPqzJ
yafmJpc70xudy64UZUZMCB1RMRAbTgT5
4MDzQWXer5OvvJkW0AGXDo8t42z7RetE
819dI094S306SeCQ91sjPQzkklETKFWm
eEZxNPQOo2iHcVJAOKVhkoCuDYOeBcsn
KEOFqYlYcYEHh2sDmB7DfjtNbfaPvH3t
hYIXTlKJC4Sh8Ac5rdWSk8mVdWLD31e5
v3TDt34RANKZA50NjGM97cnFAZ5KN3UD
zFMceMuhYip7818VCSCjQUHzvPEt6zoq
1OL5E3cbiTWyym0xjT9oG9JUT5m75sQ0
bOq97YoMp32AAtQBYZBaOry9TX1ONJJ0
8qntfQOEtlYXsmwYcTpdRees4Xs6yNIn
9byQYktAUVz4xceTyxCa5WxVHbVGEDEf
IOgFDu1iH0AmKciquZab3bvPF97I3hX6
XQrwAc4jBT1J6OKnK4UQXzjrE6lrs20w
McU44IhVLTPo4af9TYxeoW65NJqis70k
i8GMupvkcRzu0XxbeF4hW17ABBLi3ZXm
W5iROEAFHHtjtrmcUgwy3rI0vR37aaTr
3Ol5G4btDjwgw3S3laX7NoGTtEc9BJk9
XAKJpHiP5GLkV0CvPeHPUvzyoOSqW75M
yxtvFGP3YiLttvQwCF2QKmd5tkiBXU4V
A3WBgNT3vJli1ZpoUU1wsfeqq1FzUGDx
6tLDvt08yDkPHZfwBiNn3yOUC2JklWUp
NKhMwOcDoKAwX124LKZERst62warR9x4
DisNnVUTopciB3N6U9BMH906l6VEiItm
40rh4iL728VUL3vG5P1ArrvXuCpbRdje
OkADeAluSCwlX2ztyBBjtPzKAwRgNusd
3ubsTmweRKHpPizjz97kiZuHoId8W0Wb
dXqEMd2YzbNt95CduK3LcPGRUXmoI36O
nNpOIWCWUT3vyr5r6kFM6Ga1EAXXcjSg
To7nD1ayvaCXpyYTn8OSgnc413q4s8Wy
Saw6FbENJHddqaxCdqFxmkTzrDF95euf
0vGnNh42sbsPtBKJKQ4fmleNtWUGU7QH
TGWGxcZAiKTa9POhI0ZHJLM3FEgJXTGL
W4aWm9jDFaK7r3CEdBmiv40qB1qNBRbW
bandit17@bandit:~$ cat passwords.old 
4jfkt9w0OCD4u9WTwtP6He3oGj6nyRZW
ghqT03KUyKhuNoFFWBWuQHR8ooXaGOVR
f0mPuQfxqwfhHtmGDvvhUzNj3RXiMd64
WmCRTbBBhHweWDDFfPi6954SbHQ0paTm
6stNVmrQRZeq63uuenwCetL2xm2nPFAu
bNnD3BUNgnTDhFWwpyy5z7owX1rvFVd5
7knPNoWnTbclDcx8t6EwX2hHXPNnN4LK
fNPlp8qSdSDC4BXAYicP7Zkus99MwBpN
35O5OM6O0KxjAGzNuq3zwKEfYUb4Ighm
dO03ZYE1p55jUiUL8PnD47vkiLAWyzc5
kXaJu5aKqrL8NtiO9ZAx3afEpw2W3QPb
ZI3lzDYUjkGnxigo5rPI02tYTgA45WT3
Ck9nnIUqlWmDcG7PTCuoR37ePMu7whTe
vfATGSOGvnon1RqyBrfsYwRoJJk8xMJ2
JeY3KUzYwUE8xOsgZ0eQqAvur4Oxa5Wu
fHtyL7fgPFfEZmGDOTF08YCgLfIq6wJO
MaEdloWJYo5rjfgSXACUsN0Q7yurBtKh
0PIvCYFLMIdfnSoZgAh1q3G57p41JzBM
uctbsUQM5lHW1YRHeBfSoqCXOIpZC52z
R3FO96VhcSkea0k6hkrGABNw952Fdi1G
PeYCkgHUSvQWIwW86v3qSUg53jugT3lL
qSt0hfwN7h05A3tGqpV1tFvQAvKOEa9l
WxQtBtqGrq8mAeXpUBe3PBxKSzrq6f5C
kzMc9A7vX3CBmhRkqiqqx3BO1qdV78iL
bAn2ieFMRVHy5KAatPpHqjzGQsL7cSZu
35DcAfmhTMoIqBKe6JfozLGFCJ15ylYs
y8WhID6E7yEq5GzmMZUJA3jZts4gWgFJ
MhI2McTkzcwVJn7aQTsCK4Vu3cbI0173
juTtU15kqtMSoELqV2u0x4ZAHoCTGPtp
LiKFgjziWcpGlviOZVZhTvdGNxpKWEx6
O3wYckEzNAymrurGgJckO2JPQE5nttFj
MifV4D2ps0obPQTfMFduViuPxAnSYoK8
GbuqZnveJOoOiHQSStr8eGEwDtCRf2I5
RjnMfYv1rDxkPLYHkCJbK3iFRWu7OKR2
7djYQGyOiH0HTcXehusksqWXxG7Yu8VI
jvcLvLHhMDH3VYuzXhh38xBuiFLGoqSB
BJeZRntooggvwkDrf5RttspvrBLIVang
ZA8Jb6cdO0XLMIWKNv6V3VWAuiZWfC9l
GbeMalDIl63fw0N8bqzfCX87m7MHDDUK
HsCNp4XQst75r0n1xolac4J7Dd8QihaB
aFoOOJevxDDrih3wldX1AFtnB9xAiHBp
390zFj2NETFVZkqYw8UEFdN6h40oGVtT
tZtZOCHaAOVbz1xgH0bNXydD9iMHMUk8
q2SDmQDVYZKDmqTS0nmz6SfNbAbxUpYq
cVGft1jxyTruNSPCLpOnHV4maGb5UgDd
9gleP8mmAiDCtrj4OEhUPUB8CB7alenY
5SLnZXa6tw40VznQONKL8ApXSa8AuxQb
6mSiysMKmpeXAfVo38GSsY1CNkFsRQ0X
4xkde2eh85sOrh1Nj9nO4q7yFIMlFOr8
pf8AAn9IgoZwU4PYdEQIz80lBUArJlEL
G5pSQ4N47hnDttLTCaP8a7Xfn3jtndG8
pqdehHrA4zWbrisgwSeHNH6gx8ANNrXi
FpioC18S5Yu5pNQbVEJiAdTtZzs1f1qV
Xi5paoFobo6h4FbinSQt4s7KXvrWUwOR
QFyBWfjHgjjqwk3Pm949SiOLmrm5wUiT
SZhlg1k8RI5pYwjciQEx5XmqwullAcac
g8p9JVqngXrl07eCxIgx6xBAn3vltu2c
MbPvrhbdAdRqbseYT4m69bfbU5G1YOWQ
xdgWwIZi7O4acN8YaayegtcygH5HSa4n
Wlt39PlbJbVFrcPudcsY5t9rPxRtVwjG
tMwDHLvdxKB93Fs21nHZU09RcmwbN4rT
F84EnjuMtnFumFaKiIp1CBtN9puBujcM
YHGy6QsnnJK9SR866TN5ZDjUbYedGqTc
J4jiPKo4SiU0GjqqYIdzKbYKqOMazv0t
7DDKWPlPzbFxjPU95OpT3ZLg1JFZC4dR
8vGHo4H2nFM3ZM5DVQ8eFimJDZfgPqzJ
yafmJpc70xudy64UZUZMCB1RMRAbTgT5
4MDzQWXer5OvvJkW0AGXDo8t42z7RetE
819dI094S306SeCQ91sjPQzkklETKFWm
eEZxNPQOo2iHcVJAOKVhkoCuDYOeBcsn
KEOFqYlYcYEHh2sDmB7DfjtNbfaPvH3t
hYIXTlKJC4Sh8Ac5rdWSk8mVdWLD31e5
v3TDt34RANKZA50NjGM97cnFAZ5KN3UD
zFMceMuhYip7818VCSCjQUHzvPEt6zoq
1OL5E3cbiTWyym0xjT9oG9JUT5m75sQ0
bOq97YoMp32AAtQBYZBaOry9TX1ONJJ0
8qntfQOEtlYXsmwYcTpdRees4Xs6yNIn
9byQYktAUVz4xceTyxCa5WxVHbVGEDEf
IOgFDu1iH0AmKciquZab3bvPF97I3hX6
XQrwAc4jBT1J6OKnK4UQXzjrE6lrs20w
McU44IhVLTPo4af9TYxeoW65NJqis70k
i8GMupvkcRzu0XxbeF4hW17ABBLi3ZXm
W5iROEAFHHtjtrmcUgwy3rI0vR37aaTr
3Ol5G4btDjwgw3S3laX7NoGTtEc9BJk9
XAKJpHiP5GLkV0CvPeHPUvzyoOSqW75M
yxtvFGP3YiLttvQwCF2QKmd5tkiBXU4V
A3WBgNT3vJli1ZpoUU1wsfeqq1FzUGDx
6tLDvt08yDkPHZfwBiNn3yOUC2JklWUp
NKhMwOcDoKAwX124LKZERst62warR9x4
DisNnVUTopciB3N6U9BMH906l6VEiItm
40rh4iL728VUL3vG5P1ArrvXuCpbRdje
OkADeAluSCwlX2ztyBBjtPzKAwRgNusd
3ubsTmweRKHpPizjz97kiZuHoId8W0Wb
dXqEMd2YzbNt95CduK3LcPGRUXmoI36O
nNpOIWCWUT3vyr5r6kFM6Ga1EAXXcjSg
To7nD1ayvaCXpyYTn8OSgnc413q4s8Wy
Saw6FbENJHddqaxCdqFxmkTzrDF95euf
0vGnNh42sbsPtBKJKQ4fmleNtWUGU7QH
TGWGxcZAiKTa9POhI0ZHJLM3FEgJXTGL
W4aWm9jDFaK7r3CEdBmiv40qB1qNBRbW
bandit17@bandit:~$ diff passwords.new passwords.old 
42c42
< x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO
---
> 390zFj2NETFVZkqYw8UEFdN6h40oGVtT
bandit17@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.
```

### Commands used to solve this level
```bash
diff passwords.new passwords.old 
```

### Note: 
This level is solved by comparing the two files `passwords.old` and `passwords.new` to identify the single line that has changed. The `diff` command is used for this purpose, which highlights the lines that differ between the two files. In the example, `diff passwords.new passwords.old` shows that line 42 has changed: `passwords.new` contains `x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO`, while `passwords.old` has `390zFj2NETFVZkqYw8UEFdN6h40oGVtT`.


---


## Bandit 18
### Level Goal
The password for the next level is stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.

### Execution Log 
```bash
┌──(incognito㉿kali)-[~]
└─$ ssh -p 2220 bandit18@bandit.labs.overthewire.org                  
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

backend: gibson-0
bandit18@bandit.labs.overthewire.org's password: 

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

Byebye !
Connection to bandit.labs.overthewire.org closed.

┌──(incognito㉿kali)-[~]
└─$ ssh -p 2220 bandit18@bandit.labs.overthewire.org "cat readme"
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

backend: gibson-0
bandit18@bandit.labs.overthewire.org's password: 
cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8
```

### Commands used to solve this level
```bash
ssh -p 2220 bandit18@bandit.labs.overthewire.org "cat readme"
```

### Note: 
In this challenge, the .bashrc file in the home directory has been deliberately modified to automatically log the user out whenever they start an interactive SSH session. Normally, when you SSH into a Linux account, the shell reads .bashrc to configure your environment before giving you a prompt. In this case, the last line of .bashrc is something like exit or logout, so as soon as you log in interactively, the session ends, and you see “Byebye!” before you can run any commands. To solve this, you bypass the interactive shell by asking SSH to execute a command directly upon login instead of opening a normal shell. This is done by specifying the command after the SSH target, for example: `ssh -p 2220 bandit18@bandit.labs.overthewire.org "cat readme"`. SSH will then log in, run `cat readme` immediately, and print the contents without ever triggering the logout in .bashrc. This method works because .bashrc only affects interactive shells, not non-interactive command execution.


---


## Bandit 19 
### Level Goal
To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

### Execution Log 
```bash

```

### Commands used to solve this level
```bash
nc localhost 30000
```

### Note: 

---


## Bandit 20
### Level Goal
The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL/TLS encryption.
Helpful note: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage.

### Execution Log 
```bash

```

### Commands used to solve this level
```bash
nc localhost 30000
```

### Note: 

---


## Bandit 21
### Level Goal
The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL/TLS encryption.
Helpful note: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage.

### Execution Log 
```bash

```

---


## Bandit 22
### Level Goal
The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL/TLS encryption.
Helpful note: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage.

### Execution Log 
```bash

```

---


## Bandit 23
### Level Goal
The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL/TLS encryption.
Helpful note: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage.

### Execution Log 
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

