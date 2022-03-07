The newly installed armitage cannot start adn reports pg_hba.conf related error.

<img src="imgs/armitage-pg_hba-error.png">

To solve this error, edit pg_hba.conf using the following command. 
```
sudo nano /etc/postgresql/14/main/pg_hba.conf
```
For the row *# IPv4 local connections:*, change *scram-sha-256* under *Column Method* to *trust*.
<img src="imgs/pg_hba.PNG">
