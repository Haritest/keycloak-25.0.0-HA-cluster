Keycloak
========

To Configure a Keycloak cluster with high availability and run in any environment. 
The scenario is to access the keycloak nodes through a load balancer and the caching should happen at
Postgres database level.

Pre-requesties 
===============

Keycloak version : 25.0.0
Postgresql
Elastic Load balancer or any
All the configuration is passed as environment variable in the keycloak systemd service

Configuration
=============

We have to update the following files with key configurations on all the servers
1. keycloak.service
2. custom-ispn.xml

Update the keycloak.service file with the respective values like DB name, host, port, loadbalancer name, etc..
and copy it under /etc/systemd/system/. If you are using different version of linux / windows. update as per the OS version

    $systemctl daemon-reload

Update custom-ispn.xml file with the respective values.

Restart keycloak on all servers

    $ systemctl start keycloak
