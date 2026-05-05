# IT-SECURITY
Write the full absolute path:
- find /root/......../ > (to the file to want to named to)

Create a new user and lock password with name user86315:
- useradd 86315
- passwd -l user86315

Assign each public key of each person and check for verification:
- openssl dgst -verify (public key of a person) -signature (signature)
  if the verification is ok.
  - echo (name) > (to the file to save)
 
Download the file (file) with the help ..........., password is (password), copy the content to the directory /root:
-.....................
-losetup -f /(file)
-cryptsetup luksOpen /dev/loop0 loop
put the password
-mount /dev/mapper/loop /mnt
-ls /mnt 
(contents)
cp /mnt/(content) /root
cp -r /mnt/(content) /root

Decrypt the (file1) using (number) as a key and 0 initalization vector. Decrypt using aes-128-cbc. Save the result as (file2):
-openssl aes-128-cbc -d -in (file1) -K (number) -iv 0 > (file2)
-cat (file2)

Decrypt the (file1) using (number) as a key and 0 initalization vector. Decrypt using des-ede. Save the result as (file2):
-openssl des-ede -d -in (file1) -k (number) > (file2)
-cat (file2)

Sign the (file1) with the following private key. Use SHA 256. Save the signature as (signature):
-umask 077
-cat -k
(private key)
(ctrl+d) 
-openssl dgst -sign k -sha256 -out (signature) (file1)
-xxd (signature)

Set the permission of the (file) to read-only:
-chmod 444 (file) 
-stat (file)

Give the read-only permission to the operator on (file) with a NEW USER ACL:
-setfacl -m u:operator:r (file)
-getfacl (file) 

Set the owner of (file) to operator user:
-chown operator (file)

Create a file name (file) and size (number):
-dd if=/dev/zero of=(file) bs=(number) count=1

Generate an 1024 bit RSA key and save it to the (file) as a PKCS8 private key:
-openssl genkey -algorithm  RSA -pkeyopt rsa_keygen_bits:1024 -out (file)
-openssl rsa -text -noout -in (file)

Create a new (file) in a (drive) format it using ext2, and mount it in read mode
-fdisk /dev/sdc 
-n
enter x5
-w
-mkfs.ext2 (file)
-mount -o ro (file) /mnt

Allow the owner of the private key and log on as a root user:
-stat .ssh
-unmask
-mkdir .ssh
-shh-keygen -y -f kk >.ssh/authorized_keys
-stat.ssh/authorized_keys


Create a (user) and generate a new default RSA key (key) and allow (user) to log as root.
-useradd (user)
-su (user)
-ssh-keygen
enterx3
-shh-copy-id root@localhost
-yes
student or exam
-exit

Find the (directory) where the sticky bit is set. Write the full absolute name to the (file):
-find (directory) /perm/1000 > (file)

Configure the user operator, password expires on 2021-07-24 and it maximum days to change is 100:
-chage operator -M 100
-chage operator -l (x2)
-chage operator -d 2021-04-15
-chage operator -l

Set the permission of (file) so the permission as -r--rws--T in the directory listing:
-chmod 3470 (file)

Delete all the ACL from (file):
setfacl -b (file)

Set ownership of (file) so that the owner will be operator and the owner group will be users:
-chown operator:users (file)

Copy the first 70 bytes of the (file1) to (file2):
dd if= (file1) of=(file2) bs = 70 count = 1

Create a new (file) encrypted xfs on (drive) and mount it to the /mnt directory
-cryptsetup luksFormat (drive) 
-YES
-any password
-cryptsetup liksOpen (drive) x
-same password
-mkfs.xfs /dev/mapper/x
-umount /mnt/ 
-mount /dev/mapper/x /mnt


ssh-keygen
ssh-copy-id root@localhost

exit

-perm /100
-not -user bob

openssl dgst -sha256 -verify  -signature //

losetup -f /efajh2332
lsblk -f
cryptsetup luksOpen /dev/loop0 loop0

mount /dev/mapper/loop0 /mnt
cp /mnt/* /root

setfacl -m+ -b all -x -
setfacl -m u:operator:rw mess.txt
setfacl -b mess.txt

chown u:g .txt

dd if= of= bs= count=

getfacl

cryptsetup luksFormat /dev/sdc
cryptsetup luksOpen /dev/sdc
mk.xfs /dev/mapper/x
umount /mnt/
mount /dev/mapper/x /mnt
fdisk /dev/sdc

lusetup -f /af90u09ua
cryptsetup luksOpen /dev/loop0 loop
mount /dev/mapper/loop0 /mnt
ls /mnt
cp /mnt/?? /root

openssl aes-128-cbc -d -K -iv -in -ouy

openssl dgst -sha256 -sign private  -out file
openssl dgst -sha256 -verify  -signature   file

openssl genpkey -algorithm RSA -pkeyopt rsa_keygen_bits:2014 -out 
rsa -noout -text -in
setfacl -m u:operator:r file

fdisk /dev/sdc
n p w
mk.ext2 /dev/sdc1
mount -o ro /dev/sdc1 /mnt

4 o
2 g
1 T

ssh-keygen -y -f k > .ssh/authorized_keys
chmod 444 authro...

Permission rules (key to avoid “Permission denied”)
~/.ssh must be 700 (drwx------)
~/.ssh/authorized_keys must be 600 (-rw-------)
The user’s private key (id_rsa) must be 600
The parent home directory must be owned by the correct user and not writable by others.
