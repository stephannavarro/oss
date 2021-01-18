What is supported: 
 - AIX 7.2 ( rootvg should have 60GB+ free )
 - Oracle database version 12.2.0.1.0 and 19.0.0.0.0
 
How to use these playbooks :

This playbook roles will let you install oracle DB version 12 and 19 on your existing AIX 7.2 environment. 
There is 3 roles : 
  - aix ( configures some prereqs on AIX side )
  - oracle_install ( install oracle binaries )
  - oracle_create_db ( creates a database using jfs2 )

The first thing you will have to do is to download Oracle Database binaries for AIX:

the file name and location should be :

For oracle 12.2.0.1.0: /files/aix/oracle/database/12gR2/aixppc64_12201_database.zip
For oracle 19.0.0.0.0: /files/aix/oracle/database/19c/AIX.PPC64_193000_db_home.zip

Or you can update the follwoing variables in roles/oracle_install/default/main.yml accordingly: 

For oracle 12.2.0.1.0: oracledbaix12gR2
For oracle 19.0.0.0.0: oracledbaix19c


regarding the oracle installation parameters, most of them can be change by the user when launching the playbook. 
you can use the command line ansible-playbook --extra-vars "ora_user=non_oracle_default"

Or overwrite the content of roles/oracle_install/defaults/main.yml 




