# CreatingEC2Users

Creating EC2 Users on RedHat8 AWS Instances

After logging into my AWS console, I’ll create a snapshot of my RedHat8 instance’s root-volume. Also going to create users into this E2 instances.
I’m going to create your username firstinitial_lastname (all lowercase) using my initials, so my username would be j_o using the adduser j_o command. After I created my user sudo to get root access then pwd to see which account I’m in which shows /home/j_o.

<img width="682" height="346" alt="image" src="https://github.com/user-attachments/assets/d2cdaa45-3343-4e6d-8ab0-a48258eb157a" />

Because I created a new user I would need to use puttygen to create a ssh-key pair for my new user
 
<img width="480" height="472" alt="image" src="https://github.com/user-attachments/assets/a2a58c99-a9aa-4203-8158-64ac1188b27a" />

This was a tricky step where details mattered casue I ran into problems trying to connect using ssh. I need to properly prepare my user home directory for my public-ssh-key, so what I’ll do is make a directory in my as root using the mkdir .ssh command in my username directory. I then did the ls command to see what was in it after I made the directory which was nothing, but after research I realized I had to use -al utility after ls to view the hidden files.
 
<img width="618" height="330" alt="image" src="https://github.com/user-attachments/assets/cdfb206d-c831-495e-80ce-2fa22124a4e9" />

I then copied the public-ssh-key into /home/j_o/.ssh/authorized_keys directory. Then used the cat command to see the contents of the id_rsa.pub > authoized_keys files which shows my keys.

<img width="757" height="258" alt="image" src="https://github.com/user-attachments/assets/1de78dea-628b-4c6e-b06f-b87484ed4346" />

When I use the ls command again I could view that the keys are now within the directory. Also going to use the chmod to change permissions on .ssh directory to 700 –recursively then use the ls command to see if there was any changes. The changes I didn’t noticed untill I navigated out using the .. command the change directory then used ls -al to view changes.

<img width="556" height="324" alt="image" src="https://github.com/user-attachments/assets/b614cb85-8ca4-4374-a24d-d0621aaa5213" />
 
<img width="827" height="241" alt="image" src="https://github.com/user-attachments/assets/8238089a-7ed7-43f5-bb92-0a78bcdc4b6a" />

After setting up putty again I connected into my newly created username and private-ssh-key.
 
<img width="770" height="231" alt="image" src="https://github.com/user-attachments/assets/7e4f3b2b-4bec-4fa9-8dac-527522e35b40" />

I created another user into my ec2 instance. Then sudo into the account.

<img width="591" height="205" alt="image" src="https://github.com/user-attachments/assets/647b964a-3183-4c12-be82-8c7a067d496d" />

Like I did with my account im going to setup a homedir and place public-ssh-key attached to the  /home/pdelacruz/.ssh/authorized_keys direcotry. Then used vi which is a text editor in linux to place the user within the file so it would be able to connect using the keys.

<img width="667" height="178" alt="image" src="https://github.com/user-attachments/assets/7b1899b5-4ac4-44e0-bd73-e7655649f0f8" />

Then like I did with my own user I chmod to setup security on the homedir .ssh folder exactly how I did before.
 
<img width="894" height="166" alt="image" src="https://github.com/user-attachments/assets/ea9755c4-7fca-4956-914d-2fa2e1d66b8b" />

