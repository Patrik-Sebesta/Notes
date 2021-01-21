# AWS Update

Update AWS deployment (slsp asseco).

Log in to vault, add ssh key and make secrets
````
    export VAULT_ADDR=https://vault.tmloc.com:8200; vault login -method=ldap username=kauf
    ssh-add ~/.ssh/tm/slsp-nonprod-key
    cd .../cusotmers
    make secrets DEPLOYMENT=slsp ENVIRONMENT=asseco
````
Configure access to aws
````
    cd ~/.aws/config
      ...
      [profile slsp-nonprod]
      output = json
      region = eu-west-3
      role_arn=arn:aws:iam::376951411065:role/OrganizationAccountAccessRole
      source_profile=default
````
Initialize terraform
````
    cd .../afs-aws
    git checkout master
    git pull
    cd deployments/slsp/asseco
    terraform init
    terraform plan #check and in case of change apply
    terraform apply #check and confirm by "yes"
````
Configure path to repositories and run plays
````
    cd .../customers
    vim .config/aaa
      ANSIBLE_AFS_PATH=${HOME}/path/to/ansible-afs
      AFS_AWS_PATH=${HOME}/path/to/afs-aws
      ANSIBLE_TF_BIN=/usr/local/bin/terraform #path to terraform binary
    make version DEPLOYMENT=slsp ENVIRONMENT=asseco
    ./aaa slsp asseco plays/private/consistency_check.yml
````
Clean environment and apply full_afs.yml
````
    ./aaa slsp asseco plays/clean.yml
    ./aaa slsp asseco plays/full_afs.yml
````