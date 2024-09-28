# Snort
Installing and Using Snort

For this lab to work we will need 2 virtual machine, one to attack and one to defend, I will be using a Kali machine to attack and a Ubuntu Server to defend. We will also need to put them in the same network, I am using virtualbox so I will put them on bridged adapters. Make sure to check the ip of both of your machines to make sure they are on the same network before we begin.

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


