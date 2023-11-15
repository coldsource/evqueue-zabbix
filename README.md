# evQueue Zabbix template

## Host configuration

* Create a home directory for the zabbix user
* Create the file */home/zabbix/.evqueue.api.conf* with the following content (customize host, port, user and password) :

```
api.connect=tcp://localhost:5000
api.user=admin
api.password=admin
```

## Agent configuration

* Edit */etc/zabbix/zabbix_agentd.conf*
* Add evqueue API key : 

```
UserParameter=evqueue.api[*], evqueue_api --$1 --$2 $3 $4
```

## Server
Import the YML template and configure your host
