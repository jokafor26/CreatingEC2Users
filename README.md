# CreatingEC2Users

Creating EC2 Users on RedHat8 AWS Instances

After logging into my AWS console, I’ll create a snapshot of my RedHat8 instance’s root-volume. Also going to create users into this E2 instances.
I’m going to create your username firstinitial_lastname (all lowercase) using my initials, so my username would be j_o using the adduser j_o command. After I created my user sudo to get root access then pwd to see which account I’m in which shows /home/j_o.

 ![Image](https://github.com/user-attachments/assets/201100f4-cb3b-440e-bea3-0371d098482f)

Because I created a new user I would need to use puttygen to create a ssh-key pair for my new user
 
![Image](https://github.com/user-attachments/assets/ab83d574-0351-4525-bf06-0dd8cacdfd5b)

This was a tricky step where details mattered casue I ran into problems trying to connect using ssh. I need to properly prepare my user home directory for my public-ssh-key, so what I’ll do is make a directory in my as root using the mkdir .ssh command in my username directory. I then did the ls command to see what was in it after I made the directory which was nothing, but after research I realized I had to use -al utility after ls to view the hidden files.
 
![Image](https://github.com/user-attachments/assets/661b6cef-c96c-4ff8-a2c2-56bbbc88096c)

I then copied the public-ssh-key into /home/j_o/.ssh/authorized_keys directory. Then used the cat command to see the contents of the id_rsa.pub > authoized_keys files which shows my keys.

 ![Image](https://github.com/user-attachments/assets/e8fe8184-b440-41ec-b1a9-7508afe97a9d)

When I use the ls command again I could view that the keys are now within the directory. Also going to use the chmod to change permissions on .ssh directory to 700 –recursively then use the ls command to see if there was any changes. The changes I didn’t noticed untill I navigated out using the .. command the change directory then used ls -al to view changes.

 ![Image](https://github.com/user-attachments/assets/b97cd54e-50c8-4265-9737-05f3323e4ad6)
 
 ![Image](https://github.com/user-attachments/assets/4e5db362-038b-43a8-81d0-9d55a6863633)

After setting up putty again I connected into my newly created username and private-ssh-key.
 
![Image](https://github.com/user-attachments/assets/66c30d2d-b4a8-47e8-bed0-99f9dfe2be41)

Im created another user into my ec2 instance. Then sudo into the account.

 ![Image](https://github.com/user-attachments/assets/305ddfd0-b55e-4cf5-9245-0688d8135ae1)

Like I did with my account im going to setup a homedir and place public-ssh-key attached to the  /home/pdelacruz/.ssh/authorized_keys direcotry. Then used vi which is a text editor in linux to place the user within the file so it would be able to connect using the keys.

![Image](https://github.com/user-attachments/assets/8ca2e1cf-779c-4cec-b32f-1524e02736b8)

Then like I did with my own user I chmod to setup security on the homedir .ssh folder exactly how I did before.
 
![Image](https://github.com/user-attachments/assets/53c7f6e1-f6a5-46c9-a3a6-7abf45ef33ed)

