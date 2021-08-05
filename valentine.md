## Valentine
*Easy*

Port scanning using restscan

![](images/val-scan1.png)

I opened the web page.

![](images/val-web1.png)

I then used gobuster.

![](images/val-gob.png)

I then opened /dev and found the file hype_key inetresting.

![](images/val-web2.png)

Then I used cyber chef to decode the hex data. I then got an RSA private key.

![](images/val-rsa.png)

I then tried to get the password using john, but I wasen't successful.  
Not knowing what to do, I looked back at the webpage. I was a heart bleeding. So maybe, we need to use the heartbleed exploit :)

![](images/val-searchsploit.png)

I used the first exploit I found.

```
python 32764.py 10.10.10.79 > result.txt
```
Found this piece of base64 in result.txt

![](images/val-decode.png)

On decoding I got 'heartbleedbelievethehype'. We can now decrypt the rsa private key using this password and login to ssh.

![](images/val-user.png)

User falg  **e6710a5464769fd5fcd216e076961750**

Now for privilage escalation, I cannot use sudo -l because I don't know hype's password. So I lookes into his command history.

![](images/val-history.png)

Notice the command "tmux -S /.devs/dev_sess". Root user was using this dev_sess as a session filefor tmux. Tmux is a terminal multiplexer. So when I ran the command I becane root.

![](images/val-root.png)

Root flag **f1bb6d759df1f272914ebbc9ed7765b2**

