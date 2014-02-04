Monit
========

Ansible role for configuring Monitor. Sample usage see [example.yml](example.yml).

Requirements
------------

An ansible ready host.

Role Variables
--------------

* `monit_services`: List of services to be monitorized by monit.
* `monit_service_detele_unlisted`: Remove existing service monitorization configurations not declared in the `services`. Defaults to `true`.
* `monit_mail_enabled`: Enable mail alerts. Defaults to `false`.
* `monit_webinterface_enabled`: Enable monit web interface. Defaults to `true`.
* `monit_webinterface_bind`: IP address to bind web interface. Defaults to `0.0.0.0` (listen for external requests).
* `monit_webinterface_port`: Port for web interface. Defaults to `2812`.
* `monit_webinterface_rw_group`: Define group of users allowed to read and write on web interface. Defaults to `sudo`.
* `monit_webinterface_r_group`: Define group of users allowed to read on web interface. Defaults to `users`.

