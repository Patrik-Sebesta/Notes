# Interne školenie Ondrej Svačina 

#MariaDB
````
mysql -p  - prihlási sa ako root (keď som root) 
mysql -u root -h 127.0.0.1 -P 3000   - to same 
````
DB beží na porte 3000 


***show databases;***

***use databasename***  - prepne sa danu DB  
***show table meno_tabulky*** - popis tabulky \
***desc meno;*** - to same v stĺpcoch \
*** show full processlist\G;*** 

#Postup pripojenia do DB na AAIB
- zistiť na ktorom node/ip beží MariaDB - invenory list v customer repu.
- v mobaterm vytvoriť ssh pripojenie s userom afsadmin
- prepnúť sa na roota s heslom na afsadmina  - vault banka/prostredie/ssh/afsadmin 
- prihlásiť sa do db ``` mysql -p```
- heslo z vaultu  banka/prostrenie/local/database/mariadb_root 


#DB
```
MariaDB [(none)]> show databases;
+--------------------+
| Database           |
+--------------------+
| afs_apps_0         | -  androide zariadenia ? 
| afs_biometry_0     | - biometria 
| afs_cm_0           | - paymenty ? 
| afs_core_0         | -
| afs_score_0        | -
| afs_soc_0          | -
| afs_web_0          | -
| afs_winject_0      | -
| information_schema | -
| mysql              | -
| performance_schema | -
+--------------------+
```

```
SELECT table_name, column_name FROM information_schema.columns WHERE column_name LIKE ('%payment%');
alebo '%account%';
```
```
select * from f_wire_payment where source_account_id = '1011994360010203';
```
# Interne školenie Ondrej Svačina 

#MariaDB
````
mysql -p  - prihlási sa ako root (keď som root) 
mysql -u root -h 127.0.0.1 -P 3000   - to same 
````
DB beží na porte 3000 




***show full processlist\G;*** 

KILL ID - zabije querry  

uživatele 
AFS_0 -  DB user pre AFS 
AFW_WEB_0 - pro webovou DB 
specialny usery pre backup, replikaci, prometea 


show create table 


Variably 

less /etc/my.cnf.d/my-afs.cnf


logy - /data/mysql/log/mariadb-slow.log  - dlhotrvajúce querry 

# Replikace 
-iba na českej banke  - rozklonovaná na viac strojov 
- pomocou binarných logu  
master uklada  do binarných logov , slave sa dotazuje na zmeny 



# Data
/data/mysql/data 

každa DB ma svoju složku 
Každá db ma 2 subory  - data 

Velkosť tabuliek 
du tabulka/* | sort -h  



mysqldump -u -root -p -all-databases >dump.sql - lockuje DB 



PostGress
- 1 DB 
cd /data/pgsql/
