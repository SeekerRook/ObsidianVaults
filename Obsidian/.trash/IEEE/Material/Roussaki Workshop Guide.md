# Internal Networking Setup [Ethical hacking](Ethical)

## Install VMs

- from Metasploitable
- from ftp
    - `ftp 147.102.40.15`
    - User : `anonymous`
    - Password : {nothing}
    - run `get DMZ.ova`

* * *

## Import in VirtualBox

### For Metasploitable :

- click `New`
- Select \`Linux 2.4 (64bit)\`\`
- click `Next`
- Select `Memory` *(you can use the defaults 128GB)*
- click `Next`
- Select `Use existing Disk`(3rd Option)
- Find th `Metasploitable.vmdk` file you downloaded
- click `Create`

### For DMZ.ova :

- select `File`
- click `Import Appliance`
- find the `DMZ.ova` file you downloaded
- click `Next`
- In `MAC Adress Policy` 
	- select `Generate New MAC Address for ...`
- click `Import`

When it is Creted:
- go in `Settings` > `USB` > `USB Addapter 1.1`
* * *
## Internal Networking (Settings)

### For Metasploitable
- go to `Settings` > `Network` > `Attached To` : `Internal Network`
	- `Name` : `SECLAB`
### For DMZ.ova
- it must be preconfigured
### For your KALI Linux VM
- Same as Metasploitable

* * *
## Internal Networking (in each VM)
### For your KALI Linux VM
- open your Terminal
- run `ifconfig`
- check for `eth0` (or smth else)
- run `sudo ifconfig eth0 10.10.10.10/28`
- run `ifconfig` to check that your `eth0` ip address is `10.10.10.10`
### For Metasploitable
- login using `msfadmin`:`msfadmin`
- run `ifconfig`
- check for `eth0` (or smth else)
- run `sudo ifconfig eth0 10.10.10.11/28`
- run `ifconfig` to check that the `eth0` ip address is `10.10.10.11`

from your KALI Linux VM :
- `ping 10.10.10.11` to check connection between the machines

After everithing is ok close the machine (`x`) and remember to `Save the machine state`
* * *


## Wordlists
### In your KALI Linux VM
   - run `ftp 147.102.40.15`
  - User : `anonymous`
   - Password : {nothing}
   - run `get 1984.txt`
   - On your Favorite Text Editor  Create  a file Containing:
```c
admin admin   
msfadmin msfadmin
user user
admin 1234
user 1234
```
# Good Luck !!!!!