![pickle-rick](https://user-images.githubusercontent.com/94487022/159127062-cde0b0df-aa9e-45bb-93fe-52dbf61f8949.jpeg)

This Rick and Morty themed challenge requires you to exploit a webserver to find 3 ingredients that will help Rick make his potion to transform himself back into a human from a pickle.

First of all, we need to find first ingredient Rick needs.

Jump to webpage.

![webpage](https://user-images.githubusercontent.com/94487022/159127102-1c71558d-5e4c-44ea-943e-68040e35d6d6.png)

View page source to get some clues.

![source](https://user-images.githubusercontent.com/94487022/159127154-90b866c6-2c05-4f67-981b-73fd481d9d54.png)

We have username now. "R1ckRul3s". Let's try some "robots.txt" magic.

![robots txt](https://user-images.githubusercontent.com/94487022/159127164-c2dd6542-1b44-429a-aefe-fd1e4c8d2a2a.png)

Found some interesting information. Now try to see other pages. Used dirb to brute force directories to discover directories and pages on this website. Dirb discovered few interesting pages.

Found a login page asking for a username and password. Try "R1ckRul3s" and "Wubbalubbadubdub".

![loginphp](https://user-images.githubusercontent.com/94487022/159127180-cfd0cfe2-a534-4ff3-8e4a-924572c79067.png)

We're in! There is a Command Panel. Try listing content with "ls -la".

![commandpanel](https://user-images.githubusercontent.com/94487022/159127220-8e82c6fb-d08b-4c72-8d0e-9f503a969dd9.png)

Found a interesting txt file named "Sup3rS3cretPickl3Ingred.txt" which is cannot read with cat. Try getting a reverse shell from the server. We can use pentestmonkey cheat sheet for python reverse shell.

![pentestmonkey](https://user-images.githubusercontent.com/94487022/159127241-9f099e90-1714-48f8-8005-d62fca45f803.png)

Started a netcat listener on port 4444.

![nc](https://user-images.githubusercontent.com/94487022/159127249-0f7eac9e-a3f4-4446-99b5-561e839154e0.png)

Got the shell with user “www-data” authority from system.

![reverse-shell](https://user-images.githubusercontent.com/94487022/159127258-ed601290-2821-4caf-bfb2-31eb2a7e483d.jpeg)

Found first ingredient! "mr. meeseek hair".

![1-1-ingredient](https://user-images.githubusercontent.com/94487022/159127268-83508d5e-7fdc-4c70-a3d8-51fbb8382d41.png)

Read file named "clue.txt".

![clue txt_](https://user-images.githubusercontent.com/94487022/159127288-f6e25983-44be-4e7d-a4d6-b82ff24d5832.png)

Easiest task. Go "/home/rick" folder to find the second ingredient.

![1-2-ingreient-2](https://user-images.githubusercontent.com/94487022/159127295-ae9cbf8f-ee3e-44b3-8ec2-3425f7037266.png)

Found second ingredient. "1 jerry tear". Now we have to find final ingredient. It should be inside the root folder. I think.. But there is a problem. Access denied. Privilege escalation! Somehow all commands were allowed without any password. Run "sudo bash -i" to get root access.

![sudo-l-1](https://user-images.githubusercontent.com/94487022/159127310-3880a1d6-cf62-4f70-bca0-cf412e41f5de.png)

![root-access-1](https://user-images.githubusercontent.com/94487022/159127327-6458e5dc-223e-4509-905c-f20348e23229.png)

![1-3-ingredient](https://user-images.githubusercontent.com/94487022/159127329-04e4cbc5-d82f-4466-bd47-d9ed7f3ae068.png)

Browsed to root folder to get final ingredient. And here it comes! "fleeb juice". That's all.

Challenge solved. Thanks for reading the writeup!
