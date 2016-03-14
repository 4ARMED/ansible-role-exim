# Ansible Role: Exim

[![Build Status](https://travis-ci.org/4ARMED/ansible-role-exim.svg?branch=master)](https://travis-ci.org/4ARMED/ansible-role-exim)

Installs Exim (a Mail Transfer Agent) on RedHat/CentOS or Debian/Ubuntu.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    exim_dc_eximconfig_configtype: internet

(Debian/Ubuntu only) Main configuration type. Should be 'internet' for public mail sending, or 'local' if mail should only be delivered locally. See Exim documentation for other options.

    exim_dc_localdelivery: mail_spool

(Debian/Ubuntu only) Default transport for local mail delivery. Defaults to `mail_spool` if unset.

    exim_dc_smarthost: smtp.mandrillapp.com

(Debian/Ubuntu only) Default smarthost for mail delivery. Defaults to `smtp.mandrillapp.com` if unset but only used if configtype is `satellite`.

	exim_password_entry

(Debian/Ubuntu only) Add an entry to the Exim passwd.client file if your remote smarthost needs auth. Recommend this is added to defaults/vault.yml.


## Dependencies

None.

## Example Playbook

    - hosts: servers
      roles:
        - { role: 4armed.exim }

## License

MIT / BSD

## Author Information

This role was created in 2015 by [Jeff Geerling](http://jeffgeerling.com/), then forked by 4ARMED in 2016 to add extra configuration.
