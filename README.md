# Ansible Role: Postfix

[![Build Status](https://travis-ci.org/geerlingguy/ansible-role-postfix.svg?branch=master)](https://travis-ci.org/geerlingguy/ansible-role-postfix)

Installs postfix on RedHat/CentOS or Debian/Ubuntu.

## Requirements

If you're using this as an SMTP relay server, you will need to do that on your own, and open TCP port 25 in your server firewall.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    postfix_config_file: /etc/postfix/main.cf
    postfix_ssl_directory: /etc/postfix/ssl
    postfix_smtp_tls_ca_url: [not set by default]

The path to the Postfix `main.cf` configuration file.

    postfix_service_state: started
    postfix_service_enabled: true

The state in which the Postfix service should be after this role runs, and whether to enable the service on startup.

    postfix_inet_interfaces: localhost
    postfix_inet_protocols: all

Options for values `inet_interfaces` and `inet_protocols` in the `main.cf` file.

    postfix_relay_to_mailhog: no

Option to enable relaying to MailHog on the localhost, port 1025. Requires [MailHog](https://github.com/geerlingguy/ansible-role-mailhog) to be installed on localhost.

    postfix_ssl_directory: /etc/postfix/ssl
    postfix_smtp_tls_ca_url: ...

Options to make use of an SSL CA certificate for SMTP TLS.

## Dependencies

None.

## Example Playbook

    - hosts: all
      roles:
        - geerlingguy.postfix

## License

MIT / BSD

## Author Information

This role was created in 2014 by [Jeff Geerling](https://www.jeffgeerling.com/), author of [Ansible for DevOps](https://www.ansiblefordevops.com/).
