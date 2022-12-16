Lab #2

1. Using the useradd command, add accounts for the following users in your system: user1, user2,
user3, user4, user5, user6 and user7. Remember to give each user a password.

![Screenshot from 2022-12-17 01-19-26](https://user-images.githubusercontent.com/110255978/208204195-e4557514-e31e-4f2b-a6ee-925bc5bfc68a.png)

![Screenshot from 2022-12-17 01-19-47](https://user-images.githubusercontent.com/110255978/208204194-0d9e58da-51a4-4bc3-9a84-0a0c3d92e679.png)

![Screenshot from 2022-12-17 01-18-58](https://user-images.githubusercontent.com/110255978/208204196-1491ba08-7da4-4553-a4df-38039a102f81.png)

2. Using the groupadd command, add the following groups to your system.
Group GID
sales 10000
hr 10001
web 10002

![Screenshot from 2022-12-17 01-22-15](https://user-images.githubusercontent.com/110255978/208204370-27088997-b8b2-4fe9-8dc6-cca706e232da.png)

Why should you set GID in this manner instead of allowing the system to set the GID by default?

because the system will generate an incremental number not starting from 10000

3. Using the usermod command to add user1 and user2 to the sales auxiliary group, user3 and user4
to the hr auxiliary group. User5 and user6 to web auxiliary group. And add user7 to all auxiliary
groups

![Screenshot from 2022-12-17 01-26-50](https://user-images.githubusercontent.com/110255978/208204756-85a08d12-537e-4c4f-a3d9-2f084cf4820a.png)

4. Login as each user and use id command to verify that they are in the appropriate groups. How
else might you verify this information?

![Screenshot from 2022-12-17 01-28-59](https://user-images.githubusercontent.com/110255978/208205043-76d6986d-325d-415b-9d81-3686028f67e6.png)

5. Create a directory called /depts with a sales, hr, and web directory within the /depts directory.

![Screenshot from 2022-12-17 01-31-38](https://user-images.githubusercontent.com/110255978/208206508-2929c06f-72c3-4569-8cbf-5fd7999a8958.png)

6. Using the chgrp command, set the group ownership of each directory to the group with the
matching name

![Screenshot from 2022-12-17 01-40-23](https://user-images.githubusercontent.com/110255978/208208452-64507eb3-ac75-4236-9793-3d92420f88e4.png)

7. Set the permissions on the /depts directory to 755, and each subdirectory to 770

![Screenshot from 2022-12-17 01-43-03](https://user-images.githubusercontent.com/110255978/208208846-81e41584-f379-4f0d-bd47-17a221f959af.png)

8. Set the set-gid bit on each departmental directory

![Screenshot from 2022-12-17 01-44-48](https://user-images.githubusercontent.com/110255978/208209001-aee44120-2774-4b6a-8044-e3e17b39df6c.png)

9. Use the su command to switch to the user2 account and attempt the following commands:
touch /depts/sales/user2.txt
touch /depts/hr/ user2.txt
touch /depts/web/ user2.txt
Which of these commands succeeded and which failed? What is the group ownership of the files
that were created?

the ownership directory not the owner .


10. Configure sudoers file to allow user3 and user4 to use /bin/mount and /bin/umount commands,
while allowing user5 only to use fdisk command.

sudo visudo
user3 ALL=(ALL) !ALL, /bin/mount, /bin/umount
user4 ALL=(ALL) !ALL, /bin/mount, /bin/umount
user5 ALL=(ALL) !ALL, /sbin/fdisk


11. Login by user3 and try to unmount /boot.

sudo umount /dev/boot

12. Login by user4 and remount /boot. Also try to view the partition table using fdisk.

fdisk /dev/boot

13. Create a directory with permissions rwxrwx---, grant a second group (sales) r-x permissions

mkdir dir1
chmod 770 dir1
setfacl -m g:sales:rx ~/dir1

14. create a file on that directory and grant read and write to a second group (sales)

touch ~/dir1/file1
setfacl -m g:sales:rw ~/dir1/file1

15. set the the owning group as the owning group of any newly created file in that directory.
16. Grand your colleagues a collective directory called /opt/research, where they can store generated
research results. Only members of group profs and grads should be able to create new files in the
directory, and new file should have the following properties:
the directory should be owned by root
new files should be group owned by group grads
group profs should automatically have read/write access to new files
group interns should automatically have read only access to new files
other users should not be able to access the directory and its contents at all.
Bonus
Your boss thinks it’s a great idea to have one central logging server. Satisfy his
requirements
Hint:
Set up rsyslogd on the "logging server" machine to accept logging messages
from other machines.
On the your "workstation", set up rsyslogd to send messages to the "logging
server
Test the new setup by using the logger command on the "workstation" to
generate a log message
Does the message appear in the "logging server's" /var/log/messages file?
Why does this message also appear in the "workstation's" /var/log/messages
file?
How could you have the message only appear in the "logging server's" files?
