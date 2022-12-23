Lab 3
---------------

1. Display your MAC address by 2 different ways.

![Screenshot from 2022-12-23 14-41-08](https://user-images.githubusercontent.com/110255978/209337872-52ff09cc-3eaf-4ae6-8889-107a6a548bdf.png)

2. Display the network settings of all active interfaces.

![Screenshot from 2022-12-23 14-42-56](https://user-images.githubusercontent.com/110255978/209338079-58cf961d-a52b-4515-b751-7ad1ac281808.png)

3. Display the network setting of all interfaces both active inactive.

![Screenshot from 2022-12-23 14-44-20](https://user-images.githubusercontent.com/110255978/209338251-b2db58b5-6dfc-4bd2-9ba9-e543389dcc1c.png)

4. Bring your interface down.

![Screenshot from 2022-12-23 14-46-42](https://user-images.githubusercontent.com/110255978/209338610-620a174c-adb7-47bf-b158-c8ca07de3cea.png)

5. Configure your network card to have static IP.

![Screenshot from 2022-12-23 14-57-25](https://user-images.githubusercontent.com/110255978/209339901-19dbd64f-53cb-46bd-b1ca-f1424a34e906.png)


- Create a new file named /etc/sysconfig/network-scripts/ifcfg-eth0 the same as the above photo:
    - DEVICE=eth0
    - BOOTPROTO=none
    - ONBOOT=yes
    - PREFIX=24
    - IPADDR=192.168.2.203
    
- then, Restart network service using this command:
    - systemctl restart NetworkManager


6. Bring your interface up.
  - ip link set dev eth0 up

7. Verify your network setting using ifconfig command

![Screenshot from 2022-12-23 15-06-03](https://user-images.githubusercontent.com/110255978/209341109-9fe8df61-fd5f-41e8-b7c6-51d0f9b226f4.png)

8. Configure your network card to have dynamic IP using network
manager command.

9. Check using ifconfig then check its configuration file.

![Screenshot from 2022-12-23 15-12-52](https://user-images.githubusercontent.com/110255978/209341949-92d19e5b-e496-43b6-a63b-f4bf2d162292.png)

10. Reconfigure your network card using system-config-network
utility to have static IP.
11. Configure your network card to have 3 IPs and check that they
are all working using ifconfig command.
12. Change your host name in your global network file.
13. Check the present value of /proc/sys/net/ipv4/icmp_echo_ignore_all
14. It should be 0, change it to 1 which will prevent other hosts from successfully pinging your host
while not affecting your ability to ping them.
15. Try to ping your colleague, let your colleague try to ping your host.
16. Reboot and try the last step. What happened? Why?
17. Edit /etc/sysctl.conf and put the following line at the bottom:
net.ipv4.icmp_echo_ignore_all=1
18. Execute sysctl –p command.
19. Check the value of /proc/sys/net/ipv4/icmp_echo_ignore_all.

Using yum
20. Attempt to run the command gnuplot. You should find that it is not
installed.

![Screenshot from 2022-12-23 15-16-00](https://user-images.githubusercontent.com/110255978/209342327-0c786af7-b18f-4d32-93d0-c2c8cb698e0d.png)


21. Search for the plotting packages.

![Screenshot from 2022-12-23 17-32-43](https://user-images.githubusercontent.com/110255978/209360784-c02af60d-0f13-4adf-870e-4862125f59db.png)

22. Find out more information about the gunuplot package.

![Screenshot from 2022-12-23 17-58-42](https://user-images.githubusercontent.com/110255978/209364057-6cf6d1e0-83da-4644-8250-59fa9ca1f721.png)

23. Install the gnuplot package.

![Screenshot from 2022-12-23 17-57-06](https://user-images.githubusercontent.com/110255978/209363910-5837b5a9-5fdf-4209-8670-1aad06af6b38.png)

24. Attempt to remove the gnuplot package, but say no
How many packages would be removed

![Screenshot from 2022-12-23 18-00-22](https://user-images.githubusercontent.com/110255978/209364275-04eced40-0e13-44b0-a81b-b78e3565adfc.png)

25. Attempt to remove the gunplot-common package but say no
How many packages would be removed
Using rpm

![Screenshot from 2022-12-23 18-02-14](https://user-images.githubusercontent.com/110255978/209364479-82e5fab6-aa1e-4a95-8608-69d8517d723f.png)

26. List all installed packages in your system.

![Screenshot from 2022-12-23 18-03-15](https://user-images.githubusercontent.com/110255978/209364638-12b7b795-c6d4-431a-9adb-a4f6243b8071.png)

27. View the files in the initscripts package

![Screenshot from 2022-12-23 18-11-24](https://user-images.githubusercontent.com/110255978/209365585-147b56f5-7fc1-494a-9a8c-005e415cc0fe.png)

28. Get general information about bash rpm.

![Screenshot from 2022-12-23 18-04-59](https://user-images.githubusercontent.com/110255978/209364827-44f8a45a-ddf2-446d-a6af-0afecf972cd2.png)

29. Have the files from the pam package changed since it was
installed.

![Screenshot from 2022-12-23 18-12-20](https://user-images.githubusercontent.com/110255978/209365681-4afde34e-d41b-4399-869e-697eaba0f1d7.png)

30. Which installed packages have gnome in their names?

![Screenshot from 2022-12-23 18-13-22](https://user-images.githubusercontent.com/110255978/209365779-fcd0241c-ece9-489a-a26c-2e674970f7a8.png)

31. Install any uninstalled package from RH Enterprise Linux cds

![Screenshot from 2022-12-23 18-14-19](https://user-images.githubusercontent.com/110255978/209365939-51bb73d4-cad8-4596-bac6-204f106aec0a.png)

32. Search for software resemble the Photoshop software other than
Gimp and install it.

![Screenshot from 2022-12-23 18-19-24](https://user-images.githubusercontent.com/110255978/209366715-52380d88-c4ef-4a72-9805-14a53b8cac36.png)

33. Create the file /etc/yum.repos.d/cdrom.repo to enable install from
the iso from the iso of Red Hat.
34. Try to install any package from the new repository
