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
bandit4@bandit:~$ ls -a
.  ..  .bash_logout  .bashrc  inhere  .profile
bandit4@bandit:~$ cd inhere/
bandit4@bandit:~/inhere$ file ./-*
./-file00: PGP Secret Sub-key -
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
  bandit 5---->6
bandit5@bandit:~/inhere$ find -type f -readable ! -executable -size 1033c
./maybehere07/.file2
bandit5@bandit:~/inhere$ cd maybehere07
bandit5@bandit:~/inhere/maybehere07$ cat .file2
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
  bandit6---->7






