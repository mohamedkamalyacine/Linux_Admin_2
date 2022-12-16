Lab 1

1. Use systemctl to view the status of all the system services.

![Screenshot from 2022-12-15 13-33-21](https://user-images.githubusercontent.com/110255978/207849312-6da20f2d-7596-4727-9d5b-75b1c769274c.png)


2. Change the default run level back to multi-user.target and reboot.

![Screenshot from 2022-12-15 13-46-15](https://user-images.githubusercontent.com/110255978/207851418-ce844e22-7014-40b7-af34-63beb3b76085.png)


3. Send mail to the root user.

![Screenshot from 2022-12-15 13-50-58](https://user-images.githubusercontent.com/110255978/207852369-809b426c-d547-4578-b95f-3f087c3a8119.png)

4. Verify that you have received this mail.

![Screenshot from 2022-12-15 13-52-56](https://user-images.githubusercontent.com/110255978/207852711-d6a34ab2-52ae-4426-a47a-88ffb05fa186.png)

5. Use systemctl utility to stop postfix service

![Screenshot from 2022-12-15 13-55-20](https://user-images.githubusercontent.com/110255978/207853185-fcb93647-1fdc-4561-8e4b-ac14c9d27557.png)

6. Send mail again to the root user.

![Screenshot from 2022-12-15 13-50-58](https://user-images.githubusercontent.com/110255978/207854848-94e87372-b9b5-4971-9580-fd4e2e03d40d.png)

7. Verify that you have received this mail.

![Screenshot from 2022-12-07 22-34-45](https://user-images.githubusercontent.com/110255978/207856133-1e50da02-7792-41c6-9dad-a072db3822fd.png)

8. Use systemctl utility to start postfix service

![Screenshot from 2022-12-15 14-08-53](https://user-images.githubusercontent.com/110255978/207855691-0f790835-5306-4b52-82e9-a3e29810f568.png)

9. Verify that you have received this mail.

![Screenshot from 2022-12-07 22-37-42](https://user-images.githubusercontent.com/110255978/207855907-18e11f23-2818-404c-a7a3-d3e25111208f.png)

10. Edit in the GRUB2 configuration file and change the timeout variable equal 20
seconds.

vi /etc/default/grub

11. Edit in the GRUB2 configuration file and change your default operating system

![Screenshot from 2022-12-07 22-42-23](https://user-images.githubusercontent.com/110255978/207857042-8b33c997-7de4-4a3d-afca-fa0ab13f4879.png)

12. Install a new printer called "tty12" using web utility. Have the printer queue be "/dev/tty12" and specify a "Text Only Printer" for its model type.

![Screenshot from 2022-12-08 13-15-56](https://user-images.githubusercontent.com/110255978/207858601-15179186-16a0-4a9b-889e-74b960c5fb81.png)

13. Print the file /etc/hosts to the printer and view the /dev/tty12 console to ensure that the print job went to the "printer".

![Screenshot from 2022-12-08 14-14-22](https://user-images.githubusercontent.com/110255978/207858818-4e94e404-6abb-451d-b9d9-e0f6d213f4a6.png)

14. Prevent jobs from leaving the tty12 printer queue to the printer. Do not prevent users from sending jobs to the tty12 printer queue.

![Screenshot from 2022-12-08 14-21-02](https://user-images.githubusercontent.com/110255978/207859466-9173d2e2-ab70-423a-a285-1a4e9ee465e8.png)

15. Print three files (/etc/hosts, /etc/xinetd.conf, and /etc/hosts.allow) to the tty12 printer

![Screenshot from 2022-12-08 14-21-32](https://user-images.githubusercontent.com/110255978/208193193-29c25b48-dcfc-4cb0-b2ba-0e5763f1f4ef.png)

16. View the print queue.

![Screenshot from 2022-12-08 14-32-12](https://user-images.githubusercontent.com/110255978/208193263-3e7ef564-6087-4476-a3be-55fb545f5f15.png)

![Screenshot from 2022-12-08 14-33-19](https://user-images.githubusercontent.com/110255978/208193452-4b98b71b-003c-48f4-bd3d-ee4d8d052d53.png)


17. Remove the second print job from the tty12 printer queue, and then allow the print jobs from
the queue to be printed

![Screenshot from 2022-12-08 14-34-41](https://user-images.githubusercontent.com/110255978/208193494-684a0ff8-7007-40ac-95b4-d3f8b66576e3.png)


18. Prevent print jobs from going to the tty12 printer's print queue.

- cupsreject tty12

19. Verify this by trying to print the /etc/hosts file.

- lp -d tty12 /etc/hosts
- lp: Destination "tty12" is not accepting jobs.

20. Delete the tty12 printer with the lpadmin command.

- lpadmin -x tty12

21. You want to know some information about the status of the system every ten minutes today
between the hours of 8:00 AM and 5:00 PM. to help investigate some performance issues you
have been having. You suspect it might be memory related and want to keep an eye on those
resources.

![Screenshot from 2022-12-16 23-44-26](https://user-images.githubusercontent.com/110255978/208194131-61804101-5f30-4767-845d-a64dc22e325d.png)
![Screenshot from 2022-12-16 23-44-09](https://user-images.githubusercontent.com/110255978/208194141-34c140fe-bcc8-4a9f-afe0-424c5ad1047c.png)


22. Use mail as the root user to check for e-mail from the cron jobs you have scheduled.
23. How could you send the output from these cron jobs to another e-mail address (the manager
user)?
24. Use mail as the manager user to check for e-mail from the cron jobs you have scheduled.
