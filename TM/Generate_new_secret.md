#new value in Vault 
- najprv treba byť prihláseny



- zmeniť zákaznika a prostredie 
- do Ansiblu ide heslo hashovane [WIKI](https://gitlab.tmloc.com/afs/ansible-afs/-/blob/master/manuals/deployment/accounts.md#http-basic-authentication)

````
CUSTOMER=creditas
ENVIRONMENT=prod

tm_secret_afs_pg_pass='AFSSecurePassword'
vault kv put kv/v1/afs/$CUSTOMER/$ENVIRONMENT/local/postgres \
password="$tm_secret_afs_pg_pass"

tm_secret_postgresql_monitoring_pass='FqqdvOy6OIeXBxc8crki'
vault kv put kv/v1/afs/$CUSTOMER/$ENVIRONMENT/local/postgres_monitoring \
password="$tm_secret_postgresql_monitoring_pass"

tm_secret_afs_panel_db_pass='AFSSecurePassword'
tm_secret_afs_panel_secret_key='VfNl8F3WXtWxBP4zfFHn'
vault kv put kv/v1/afs/$CUSTOMER/$ENVIRONMENT/local/afs_panel \
secret_key=$tm_secret_afs_panel_secret_key \
password=$tm_secret_afs_panel_db_pass
````
