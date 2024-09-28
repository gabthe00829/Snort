# Snort
Installing and Using Snort

For this lab to work we will need 2 virtual machine, one to attack and one to defend, I will be using a Kali machine to attack and Ubuntu Server to defend. We will also need to put them in the same network, I am using virtualbox so I will put them on bridged adapters. Make sure to check the ip of both of your machines to make sure they are on the same network before we begin.

We will start by installing Snort on our machine that is defending with sudo apt install snort:

![image](https://github.com/user-attachments/assets/25561b57-a45f-4808-97ca-e9cbc9dc2cf0)

Make sure to pay attention to what your ethernet interface is during installation mine enp0s3:

![image](https://github.com/user-attachments/assets/91bcb9a9-a1f0-4029-a1fc-1fdaa29796d7)

After Snort is done installing we will have to go change our ip range in the file /etc/snort/snort.conf:

![image](https://github.com/user-attachments/assets/68da237b-219e-486b-937a-4d433c317944)

We can check if our config file is properly working using the command snort -T -c /etc/snort/snort.conf:

![image](https://github.com/user-attachments/assets/8ca90d93-e2bb-4f30-9219-af02d66db84e)

Now that we know our config file is functionning properly we will use the following command to start detecting intrusions:

![image](https://github.com/user-attachments/assets/54d89e03-99ac-4dc5-970b-582252fd3d5e)

Now that our defensive machine is listening we will do an NMAP scan with our offensive machine to make sure Snort is functionning properly:

![image](https://github.com/user-attachments/assets/61426252-7e58-4dee-a283-4b5f1d18f8cb)

On our defensive machine we should see that somebody tried to scan our machine:

![image](https://github.com/user-attachments/assets/a044a99d-c0f4-438a-9b09-931281451f11)

On our offensive machine we can use legion to do multitple scans:

![image](https://github.com/user-attachments/assets/d93f0a38-e51c-4dcf-9ce8-51de16f2a045)

We again see on our defensive machine that somebody tried to scan our machine:

![image](https://github.com/user-attachments/assets/96b552c7-6c40-445b-a506-4f0e93eae52f)

Using Snort we can also add a rule that will display a message if another machine attempts an ICMP connection by going in /etc/snort/rules/local.rules to modify the following rules:

![image](https://github.com/user-attachments/assets/ab49f630-8526-4791-9500-dd73522d24f7)

We can start back our Snort to start detecting again:

![image](https://github.com/user-attachments/assets/4213e500-872e-4971-a0e6-977c31705bed)

Going back on our offensive machine we can attempt a ping to our defensive machine:

![image](https://github.com/user-attachments/assets/2a6ad09e-7784-4deb-8b0f-e7e32d75184a)

If we take a look back on our defensive machine we will see that our message displays:

![image](https://github.com/user-attachments/assets/4ac1bf0c-83e0-4f1f-ad7d-870f44befbc1)















