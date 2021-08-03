## Legacy
*Easy*

Used rustscan to find open ports.

![](images/legacy-scan.png)

To find the version of SMB I used metasploit.

![](images/legacy-version.png)

I googled 'Windows XP SP3 (language:English)' and found [this](https://www.rapid7.com/db/modules/exploit/windows/smb/ms08_067_netapi/) article useful.

![](images/legacy-msf1.png)

Ran the exploit.

![](images/legacy-meterpreter.png)

We are the administrator.

![](images/legacy-user.png)

![](images/legacy-root.png)

User flag  **e69af0e4f443de7e36876fda4ec7644f**

Root flag  **993442d258b0e0ec917cae9e695d5713**
