## Usage

### Run:
```shell
docker-compose up -d
```

## Environment variables and defaults
https://github.com/ServerContainers/samba/blob/master/README.md

### Samba

* __ACCOUNT\_username__
    * multiple variables/accounts possible
    * adds a new user account with the given username and the env value as password

to restrict access of volumes you can add the following to your samba volume config:

    valid users = alice; invalid users = bob;

* __SAMBA\_CONF\_WORKGROUP__
    * default: _WORKGROUP_

* __SAMBA\_CONF\_SERVER\_STRING__
    * default: _file server_

* __SAMBA\_CONF\_MAP_TO_GUEST__
    * default: _Bad User_

* __SAMBA\_CONF\_ENABLE\_PASSWORD\_SYNC__
    * default not set - if set password sync is enabled

* __SAMBA\_CONF\_ENABLE\_NTLM\_AUTH__
    * default not set - if set password sync is enabled
    * _use for compatibility with xp if you have troubles like NTLMv1 passwords NOT PERMITTED for user_
    * !!! NOTE: NTLMv1 is known to be broken and it's easy to recover the real password from the hash !!!

* __SAMBA\_VOLUME\_CONFIG\_myconfigname__
    * adds a new samba volume configuration
    * multiple variables/confgurations possible by adding unique configname to SAMBA_VOLUME_CONFIG_
    * examples
        * "[My Share]; path=/shares/myshare; guest ok = no; read only = no; browseable = yes"
        * "[Guest Share]; path=/shares/guests; guest ok = yes; read only = no; browseable = yes"

