### SOC sync
- servica ktorá sync  listy a webinjecty 
- centralne sa držia na SOCu 

### PHISHING 
28.12 - Matúš 
slsp ako vzor 
    - pozrieť verziu v customers repu 
    - v gite pozrieť  do akeho tagu je aplikovaný nový fix 
vytvoriť  medziverziu :

    - vytvoriť novú branche 
    - všetkým javascriptom povedať, aký hotfix maju použiť (afs-js v configu )\
    - git commit -m [PABK/PROD/SIT] TICKET 
    - git push HEAD 
    
server :

    - pripojiť sa na server a upraviť to ručne (/home/afsadmin/ansible-afs) Dopísať tag_owerride 
    - ak je iba jeden node upraviť docker composer a stiahnuť nove docker image. 
    - Ak je nodov viac,treba to robiť cez ansible.
    - upraviť docker-compose - ak sme na jednej mašine 
    - nasledne ich spustiť 
        ```
        docker-compose up -d --force-recreate afs-js-ibsk/ibcz/ib365 
        ```
        
  #ako na to 
  - do aws pridať toho nového zakaznika - AWS číslo z customer repa 
  - do ~/.ssh/config pridať  zakaznika 
  - do ~/.ssh/tm/  pridať private key 
  -  ssha ~/.ssh/tm/b2b_prod   a pak ssha a cesta ku klúču 