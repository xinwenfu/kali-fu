## xrdp 

Install xrdp
```
sudo apt update
sudo apt install xrdp

sudo systemctl enable xrdp
sudo systemctl restart xrdp
```

To [allow multiple sessions for the same user](https://c-nergy.be/blog/?p=16698), edit startwm.sh
```
sudo nano /etc/xrdp/startwm.sh
```
Add the following command at the end of the file
```
export $(dbus-launch)
```


## Armitage

### Installation of armitage on new Kali VM

```
sudo apt-get update
sudo apt-get -y install armitage  
```
*-y* means automatic yes to prompts.


### pg_hba.conf error
The newly installed armitage cannot start adn reports pg_hba.conf related error.

<img src="imgs/armitage-pg_hba-error.png">

To solve this error, edit pg_hba.conf using the following command. 
```
sudo nano /etc/postgresql/14/main/pg_hba.conf
```
For the row *# IPv4 local connections:*, change *scram-sha-256* under *Column Method* to *trust*.
<img src="imgs/pg_hba.PNG">

Then restart postgresql.
```
sudo service postgresql restart
```
