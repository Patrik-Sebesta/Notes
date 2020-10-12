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
- Skupina príznakov ktorou prevediem DB z jedneho konzistentného stabu do druhého 
A - Aromicity - vše jako celek nebo nic \
C - Consistency - neni porušene žiadne integritni omezeni \
I - Isolation - operace uvni
D - Durability