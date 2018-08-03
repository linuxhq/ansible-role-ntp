# ansible-role-ntp

[![Build Status](https://travis-ci.org/linuxhq/ansible-role-ntp.svg?branch=master)](https://travis-ci.org/linuxhq/ansible-role-ntp)
[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-ntp-blue.svg?style=flat)](https://galaxy.ansible.com/linuxhq/ntp)
[![License](https://img.shields.io/badge/license-GPLv3-brightgreen.svg?style=flat)](https://github.com/linuxhq/ansible-role-ntp/blob/master/COPYING)

Linux - Network Time Protocol daemon (ntpd)

## Requirements

None

## Role Variables

Available variables are listed below, along with default values:

    ntp_server_options: iburst
    ntp_servers:
      - "0.pool.ntp.org {{ ntp_server_options }}"
      - "1.pool.ntp.org {{ ntp_server_options }}"
      - "2.pool.ntp.org {{ ntp_server_options }}"
      - "3.pool.ntp.org {{ ntp_server_options }}"
    ntp_commands:
      disable: monitor
      driftfile: /var/lib/ntp/drift
      includefile: /etc/ntp/crypto/pw
      keys: /etc/ntp/keys
      restrict:
        - default nomodify notrap nopeer noquery
        - 127.0.0.1
        - ::1
      server: "{{ ntp_servers }}"
    ntp_sysconfig: '-g'

## Dependencies

None

## Example Playbook

    - hosts: servers
      roles:
        - role: linuxhq.ntp

## License

Copyright (C) 2018 Taylor Kimball <tkimball@linuxhq.org>

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program. If not, see <http://www.gnu.org/licenses/>.
