First of all, if you want everything to be fine, you do definitely need to:
1) Turn off or set to permissive SElinux/apparmor;
2) Turn off or allow required ports in your firewall settings;
3) Make sure you time is synchronized on all of you nodes;
4) Your locale settings are configured properly.

This is simple **OpenLDAP OLC** server config, which includes: 
 - server installation and basic configuration;
 - CA and server certificate files creation, DH key creation (may take some time);
 - admin accounts for cn=config and for base;
 - logging;
 - basic OUs (People and Group);
 - passwd and group files migration to ldif and import. 

And also basic **client config** using **nscd** and **nslcd**.

You may need extra ansible-galaxy collection to work with certificates:
```
ansible-galaxy collection install community.crypto
```

These playbooks have been tested on **Centos7** and **Ubuntu 20.04**.