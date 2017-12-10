# ansible-role-ntp

[![Build Status](https://travis-ci.org/linuxhq/ansible-role-ntp.svg?branch=master)](https://travis-ci.org/linuxhq/ansible-role-ntp)

RHEL/CentOS - Network Time Protocol daemon (ntpd)

## Requirements

None

## Role Variables

Available variables are listed below, along with default values:

    ntp_commands:
      disable: monitor
      driftfile: /var/lib/ntp/drift
      includefile: /etc/ntp/crypto/pw
      keys: /etc/ntp/keys
      restrict:
        - default nomodify notrap nopeer noquery
        - 127.0.0.1
        - ::1
      server:
        - 0.centos.pool.ntp.org iburst
        - 1.centos.pool.ntp.org iburst
        - 2.centos.pool.ntp.org iburst
        - 3.centos.pool.ntp.org iburst
    ntp_sysconfig: '-g'

## Dependencies

None

## Example Playbook

    - hosts: servers
      roles:
        - role: linuxhq.ntp

## License

GPLv3

## Author Information

This role was created by [Taylor Kimball](http://www.linuxhq.org).
