# plsql-credentials-storage
This project is implementation of security credential storage. 
Purpose hier ist not to store passwords, API keys etc in code/repository but in separate properties file which will not saved in repository.
Put file credentials.store.properties in directory on server where oracle user can read from. In my example it ist /home/oracle/oracleAccess. 
if it should be another path, corresponding changes have to be done in file getPropertie.
File credentials.store.properties is normal java properties file.

In order for user to read file from filesystem from SYS user should be issued following command
```
exec dbms_java.grant_permission( 'GOOGLE_MAIL', 'SYS:java.io.FilePermission', '/home/oracle/oracleAccess/credentials.store.properties', 'read' );
```
run setup.sql from schema where it should be used.