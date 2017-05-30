# ansible-role-ntp

[![Build Status](https://travis-ci.org/linuxhq/ansible-role-ntp.svg?branch=master)](https://travis-ci.org/linuxhq/ansible-role-ntp)

RHEL/CentOS - Network Time Protocol daemon (ntpd)

## Requirements

None

## Role Variables

Available variables are listed below, along with default values:

    ntp_crypto: False
    ntp_disable:
      - monitor
    ntp_driftfile: /var/lib/ntp/drift
    ntp_includefile: /etc/ntp/crypto/pw
    ntp_keys: /etc/ntp/keys
    ntp_restrict:
      - default nomodify notrap nopeer noquery
      - 127.0.0.1
      - '::1'
    ntp_server:
      - 0.centos.pool.ntp.org
      - 1.centos.pool.ntp.org
      - 2.centos.pool.ntp.org
      - 3.centos.pool.ntp.org
    ntp_statistics:
      - clockstats
    ntp_sysconfig_options: '-g'

Additional variables available, not set by default:

    ntp_trustedkey: [ '4', '8', '42' ]
    ntp_requestkey: 8
    ntp_controlkey: 8

## Dependencies

None

## Example Playbook

    - hosts: servers
      roles:
        - role: linuxhq.ntp

## License

BSD

## Author Information

This role was created by [Taylor Kimball](http://www.linuxhq.org).
