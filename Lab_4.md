# Lab_4
---------------------

1. Use fdisk -l to locate information about the partition sizes.
  - fdisk -i

2. Use fdisk to add a new logical partition that is 1GB in size.

![Screenshot from 2022-12-23 19-02-44](https://user-images.githubusercontent.com/110255978/209373784-1d8b923f-5981-49f1-8fa6-b15da115bea1.png)

3. Did the kernel feel the changes? Display the content of /proc/partitions file? What
did you notice? How to overcome that?
  - no
  - ![Screenshot from 2022-12-23 19-06-54](https://user-images.githubusercontent.com/110255978/209374009-7ab57977-4bf9-45bc-ac08-8ddc5c55c7f2.png)
  - New partitoion didn't listed
  - Reaboot the system.

4. Make a new ext2 file system on the new logical partition you just created.
Bonus: Try creating the ext2 filesystem with 2k blocks and one inode per
every 4k (two blocks) of filesystem.

- mkfs.ext4 /dev/nvme0n1p3.

5. Create a directory, name it /data.

-sudo mkdir/data.

6. Add a label to the new filesystem, name it data.

-e2label /dev/nvme0n1p3

7. Add a new entry to /etc/fstab for the new filesystem using the label you just
create.

![Screenshot from 2022-12-23 19-12-28](https://user-images.githubusercontent.com/110255978/209374709-f2b4673f-2211-4ae3-b5f8-de671de84aa9.png)

![Screenshot from 2022-12-23 19-12-09](https://user-images.githubusercontent.com/110255978/209374732-2c8e4503-b82f-40a0-8b43-aa7dd6c8bd3e.png)

8. Mount the new filesystem.

- mount /dev/nvme0n1p3 /data

9. Display your swap size.
10. Create a swap file of size 512MB.
11. Add the swap file to the virtual memory of the system.
12. Display the swap size
13. Implement disk quotas for users on the /home directory by taking the following actions
a. Edit /etc/fstab and add the usrquota option to the /home filesystem
b. Remount the filesystem with the command mount -o remount /home
c. Use the quotacheck command to create the quota-tracking file
quotacheck /home
d. Use the quotaon command to enable quota tracking by the kernel quotaon /home
