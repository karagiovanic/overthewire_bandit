bandit.labs.overthewire.org
port:2220
bandit0:
bandit0--->1
cat readme
Password:ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
bandit1--->2
user:bandit1
Commands: ls -a
-  .  ..  .bash_logout  .bashrc  .profile
bandit1@bandit:~$ cat ./-
Password: 263JGJPfgU6LtdEvgfWU1XP5yac29mFx
bandit2--->3
ls
spaces in this filename
bandit2@bandit:~$ cat "spaces in this filename"
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
bandit3--->4
ls
inhere
bandit3@bandit:~$ cd inhere/
bandit3@bandit:~/inhere$ ls -a
.  ..  ...Hiding-From-You
bandit3@bandit:~/inhere$ cat ...Hiding-From-You
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
bandit4--->5



