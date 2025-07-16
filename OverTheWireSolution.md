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
bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c -type f 2>/dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
  bandit7---->8
bandit7@bandit:~$ cat data.txt | grep millionth
millionth       dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
  bandit8--->9
bandit8@bandit:~$ sort data.txt | uniq -u
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
  bandit9--->10
strings data.txt| grep ===
========== the
========== password{k
=========== is
========== FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
  bandit10--->11
ls
data.txt
bandit10@bandit:~$ cat data.txt
VGhlIHBhc3N3b3JkIGlzIGR0UjE3M2ZaS2IwUlJzREZTR3NnMlJXbnBOVmozcVJyCg==
bandit10@bandit:~$ man base64
bandit10@bandit:~$ base64 -d data.txt
The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
  bandit11--->12
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
The password is 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
  bandit12--->13
bandit12@bandit:~$ cd /tmp
bandit12@bandit:/tmp$ mktemp -d
/tmp/tmp.W5t1vua6G9
bandit12@bandit:/tmp$ cd /tmp/tmp.W5t1vua6G9
bandit12@bandit:/tmp/tmp.W5t1vua6G9$ cp ~/data.txt .
bandit12@bandit:/tmp/tmp.W5t1vua6G9$ ls
data.txt
bandit12@bandit:/tmp/tmp.W5t1vua6G9$ mv data.txt hexdump_data
bandit12@bandit:/tmp/tmp.W5t1vua6G9$ ls
hexdump_data
$ cat hexdump_data | head
00000000: 1f8b 0808 0650 b45e 0203 6461 7461 322e  .....P.^..data2.
00000010: 6269 6e00 013d 02c2 fd42 5a68 3931 4159  bin..=...BZh91AY
00000020: 2653 598e 4f1c c800 001e 7fff fbf9 7fda  &SY.O...........
00000030: 9e7f 4f76 9fcf fe7d 3fff f67d abde 5e9f  ..Ov...}?..}..^.
00000040: f3fe 9fbf f6f1 feee bfdf a3ff b001 3b1b  ..............;.
00000050: 5481 a1a0 1ea0 1a34 d0d0 001a 68d3 4683  T......4....h.F.
00000060: 4680 0680 0034 1918 4c4d 190c 4000 0001  F....4..LM..@...
00000070: a000 c87a 81a3 464d a8d3 43c5 1068 0346  ...z..FM..C..h.F
00000080: 8343 40d0 3400 0340 66a6 8068 0cd4 f500  .C@.4..@f..h....
00000090: 69ea 6800 0f50 68f2 4d00 680d 06ca 0190  i.h..Ph.M.h.....
bandit12@bandit:/tmp/tmp.W5t1vua6G9$ xxd -r hexdump_data compressed_data
bandit12@bandit:/tmp/tmp.W5t1vua6G9$ ls
compressed_data  hexdump_data
$ cat compressed_data | head
P�^data2.bin=��BZh91AY&SY�O����ڞOv���}?��}��^����������ߣ��;����▒4��▒h�F�F��4▒LM
                                                                               @��z��FM��C�hF�C@�4@f��h
4hh�▒=C%�>X▒,�k���1��GY��                                                                              ��i�hPh�Mh
�J�쌑Oϊ��{RBp�Qix�Y�Z!d��j�(�搿ݳ��/��A�#�A��F��0P��v��`�"3�

                                          ��d�bX?��z��2��<��A �n}
5(3A��
      wO�R����6�XS{�
���9?L�P�yB��=z�m?�L�Nt*�7{qP���%"�w9�qm4�� N3�6���K��H䋑[��}!
                                                              d��3A4$��M~�\ɠJ�C�kUƦ\���\�FSN��&=�[��q   \)�$:��H�t&/�(����]��BB9<s ��h=
bandit12@bandit:/tmp/tmp.W5t1vua6G9$ cat hexdump_data 
00000000: 1f8b 0808 0650 b45e 0203 6461 7461 322e  .....P.^..data2.
bandit12@bandit:/tmp/tmp.W5t1vua6G9$ mv compressed_data compressed_data.gz
bandit12@bandit:/tmp/tmp.W5t1vua6G9$ ls
compressed_data.gz  hexdump_data
bandit12@bandit:/tmp/tmp.W5t1vua6G9$ gzip -d compressed_data.gz 
bandit12@bandit:/tmp/tmp.W5t1vua6G9$ ls
compressed_data  hexdump_data
bandit12@bandit:/tmp/tmp.W5t1vua6G9$ xxd compressed_data 
00000000: 425a 6839 3141 5926 5359 8e4f 1cc8 0000  BZh91AY&SY.O....
bandit12@bandit:/tmp/tmp.W5t1vua6G9$ mv compressed_data compressed_data.bz2
bandit12@bandit:/tmp/tmp.W5t1vua6G9$ ls
compressed_data.bz2  hexdump_data
bandit12@bandit:/tmp/tmp.W5t1vua6G9$ bzip2 -d compressed_data.bz2
bandit12@bandit:/tmp/tmp.W5t1vua6G9$ mv compressed_data compressed_data.gz
bandit12@bandit:/tmp/tmp.W5t1vua6G9$ gzip -d compressed_data.gz
bandit12@bandit:/tmp/tmp.W5t1vua6G9$ cat compressed_data 
data5.bin0000644000000000000000000002400013655050006011240 0ustar  rootrootdata6.bin0000644000000000000000000000033613655050006011247 0ustar  rootrootBZh91AY&SY
                                          +
�A��z�<jA��j                               ���Y�@�U��Z��t!ހ��u�  �
            �@ѣ ��!�h▒iM�
 ���BȨ$fz&1*�Ԇf��zG�g}�+�Q�P(f}���@Թ��▒���Tj�1�P�EƮ��ߨ���@Ț��=�s��*���As*Y��!$r��5���Es�]��B@ 0�,
bandit12@bandit:/tmp/tmp.W5t1vua6G9$ xxd compressed_data | head                                                      
00000000: 6461 7461 352e 6269 6e00 0000 0000 0000  data5.bin.......
00000010: 0000 0000 0000 0000 0000 0000 0000 0000  ................
00000020: 0000 0000 0000 0000 0000 0000 0000 0000  ................
00000030: 0000 0000 0000 0000 0000 0000 0000 0000  ................
00000040: 0000 0000 0000 0000 0000 0000 0000 0000  ................
00000050: 0000 0000 0000 0000 0000 0000 0000 0000  ................
00000060: 0000 0000 3030 3030 3634 3400 3030 3030  ....0000644.0000
00000070: 3030 3000 3030 3030 3030 3000 3030 3030  000.0000000.0000
00000080: 3030 3234 3030 3000 3133 3635 3530 3530  0024000.13655050
00000090: 3030 3600 3031 3132 3430 0020 3000 0000  006.011240. 0...
bandit12@bandit:/tmp/tmp.W5t1vua6G9$ mv compressed_data compressed_data.tar
bandit12@bandit:/tmp/tmp.W5t1vua6G9$ tar -xf compressed_data.tar 
bandit12@bandit:/tmp/tmp.W5t1vua6G9$ ls
compressed_data.tar  data5.bin  hexdump_data
bandit12@bandit:/tmp/tmp.W5t1vua6G9$ tar -xf data5.bin
bandit12@bandit:/tmp/tmp.W5t1vua6G9$ xxd data6.bin 
00000000: 425a 6839 3141 5926 5359 080c 2b0b 0000  BZh91AY&SY..+...
bandit12@bandit:/tmp/tmp.W5t1vua6G9$ bzip2 -d data6.bin
bzip2: Can't guess original name for data6.bin -- using data6.bin.out
bandit12@bandit:/tmp/tmp.W5t1vua6G9$ ls
compressed_data.tar  data5.bin  data6.bin.out  hexdump_data
bandit12@bandit:/tmp/tmp.W5t1vua6G9$ tar -xf data6.bin.out
bandit12@bandit:/tmp/tmp.W5t1vua6G9$ ls
compressed_data.tar  data5.bin  data6.bin.out  data8.bin  hexdump_data
bandit12@bandit:/tmp/tmp.W5t1vua6G9$ xxd data8.bin
00000000: 1f8b 0808 0650 b45e 0203 6461 7461 392e  .....P.^..data9.
bandit12@bandit:/tmp/tmp.W5t1vua6G9$ mv data8.bin data8.gz
bandit12@bandit:/tmp/tmp.W5t1vua6G9$ gzip -d data8.gz
bandit12@bandit:/tmp/tmp.W5t1vua6G9$ ls
compressed_data.tar  data5.bin  data6.bin.out  data8  hexdump_data
bandit12@bandit:/tmp/tmp.W5t1vua6G9$ cat data8
Password:FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
bandit13--->14
bandit13@bandit:~$ ls
sshkey.private
bandit13@bandit:~$ ssh -i sshkey.private -p 2220 bandit14@localhost
bandit14@bandit:~$ cat /etc/bandit_pass/bandit14



















