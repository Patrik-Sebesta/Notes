
UAT 1  -AWS 
Ticket https://jira.tmloc.com/browse/CUSTSUPP-2518

#links
 Page | Link 
 --- | --- 
 AFS manual |  link https://gitlab.tmloc.com/afs/ansible-afs/-/tree/master/manuals%2Fdeployment#afs-deployment-manual
Sharepoint | https://threatmarkcz.sharepoint.com/sites/delivery/Shared%20Documents/Forms/AllItems.aspx?viewid=80d47fb9%2Da326%2D43be%2D9bf2%2D89341d9beb29&id=%2Fsites%2Fdelivery%2FShared%20Documents%2FDelivery%5FAFS

#Kroky
1. ***Vytvorenie xls dokumentu*** 
    v Sharepoint( link hore) -> ... -> copy to -> current directory and to customer file
2. Vytvoriť si SSH klúč na AWS 

3. z customers info zistim AWS instanciu
```
ssh -i /home/patrik.sebesta/.ssh/tm/creditas_uat ec2-user@ec2-35-180-38-130.eu-west-3.compute.amazonaws.com
````
4 Pripraviť customer repo 
    - 




#TODO
1. Typora - MD editor 
 
````
alias ssha='eval $(ssh-agent) && ssh-add'
````

 
 