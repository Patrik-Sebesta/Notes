#MySQL školení 

## Algoritmy 
- ***B-Tree***
    - Datova struktura z binarneho stromu \
vyváženy - do každého listu je z koreňa rovnako daleko 

- ***B+Tree*** 
    - Data jsou uložene až v listech.
Uzly obsahuju ukazatele na sousedy. 

- ***LSM Tree***
    - Má nekolik úrovni, obsahuje dvojivce Klíč - hodnota. 
    - **SST** - roztriedena a nemenna maka klúč-hodnota 

- ***Fractal Tree***
    - Má naviac od B+stromu message buffery 
- ***T-Tree***

## Locky
- Table level lock 
    - zamkne celú tabulku - kontorluje sa jeden zámok 
- Row level lock 
    - na úrovni enginu
- Record level lock 
    - zamykanie indexov
- Gap level lock 
    - Zamykanie indexov - range 
- Next Key level 

##Transakce
- Skupina príznakov ktorou prevediem DB z jedneho konzistentného stabu do druhého\
 
A - Aromicity - vše jako celek nebo nic \
C - Consistency - neni porušene žiadne integritni omezeni \
I - Isolation - operace uvni\
D - Durability


#2. workshop
## Škálovani a dostupnosť
 
- vertikalne škálovani 
    - zmena HW /či už HW alebo SW 
- horizontalne 
    - loudbalancovať na stroj vedla ( na viacero mašín)
### Autoscaling
automatizace horizontalního a vert. škalovani na základe metrik 
 
 #škalovanie:
 - clustering - rozdeleni req. napriek strojmi HA 
  
    Replikace
 - sharding - rozdeleni dat naprič stroji 
 - partitioning - rozdelenie dat do tabuliek 
 
 
 ## Ramka a DB 
 BufferPool - do ramky si uklada data z tabulky s ktorými pracuje. Uklada si ich do ***page***s.
 Ak je v nich zmena su to dirty pages. (data so zmenou ale neuložena v DB). Na hdd sú uložene ibd data. 
 Po commite  sa  zmeny uložia do double writte buffer, pak do idb - až pak sa pošle uživateli potvrdenie o commite. 
 Rollback segment - kvázi snapchot. 
 
Pomocne tabulky sa  ukladajú v RWM, ak su vačšie ako nastavene hodnoty, ukladajú sa na disk.

#3. workshop 



 