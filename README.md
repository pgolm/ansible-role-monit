Monit
========

Ansible role for configuring Monit. Sample usage see [example.yml](http://github.com/pgolm/ansible-playbook-monit/blob/master/example.yml).

Requirements
------------

An ansible ready host.

Role Variables
--------------

* `monit_services`: List of services to be monitorized by monit.
* `monit_service_delete_unlisted`: Remove existing service monitorization configurations not declared in the `services`. Defaults to `true`.
* `monit_mail_enabled`: Enable mail alerts. Defaults to `false`.
* `monit_webinterface_enabled`: Enable monit web interface. Defaults to `true`.
* `monit_webinterface_bind`: IP address to bind web interface. Defaults to `0.0.0.0` (listen for external requests).
* `monit_webinterface_port`: Port for web interface. Defaults to `2812`.
* `monit_webinterface_rw_group`: Define group of users allowed to read and write on web interface. It is only applied when defined and is empty by default.
* `monit_webinterface_r_group`: Define group of users allowed to read on web interface. It is only applied when defined and is empty by default.
* `monit_webinterface_acl_rules`: List of ACL rules for the web interface, such as "localhost" or "hauk:password". It is only applied when defined and is empty by default.
* `monit_apache_rules`: List of monitoring rules for apache service. You should adjust them to your needs.
* `monit_apache_groups`: List of groups for the apache service. This list is empty by default.
* `monit_memcached_rules`: List of monitoring rules for memcached service. You should adjust them to your needs.
* `monit_memcached_groups`: List of groups for the memcached service. This list is empty by default.
