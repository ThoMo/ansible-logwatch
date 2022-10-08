Ansible Role: thomo.logwatch [![Build Status](https://app.travis-ci.com/thomo/ansible-logwatch.svg?branch=main)](https://app.travis-ci.com/thomo/ansible-logwatch)
========

Ansible role to install and configure logwatch.

Installation
------------
### Ansible Galaxy

If you want to install it in the local ansible project dir:

    ansible-galaxy install -p roles thomo.logwatch

To install it on system level

    ansible-galaxy install thomo.logwatch

### Manual

Alternative you can install it by downloading it from github.

    wget https://github.com/thomo/ansible-logwatch/archive/master.zip
    unzip -d roles master.zip
    mv roles/ansible-logwatch-master roles/thomo.logwatch

Role Variables
--------------

    # default is root
    logwatch_mail_to: 'root'

    # default is Logwatch
    logwatch_mail_from: 'Logwatch'

    # Output: stdout, file, mail
    logwatch_output: 'stdout'

    # Format: text, html
    logwatch_format: 'html'

    # default is 'all'
    logwatch_services: [all]

    # specifiy service names without prepending a hyphen, default is []
    logwatch_disabled_services: []

    # valid ranges are: yesterday (yesterday), today, all
    logwatch_range: 'yesterday'

    # search through the archives, default is Yes
    logwatch_archive: 'Yes'

    # valid values are: Low, Med, High or a number (0 - 10), default is Low(0)
    logwatch_detail: 'Low'

    # Limit report to hosts
    logwatch_limit_to_hosts: []

    # Use hostname for the reports instead of this system's hostname.
    logwatch_hostname: ''

    # Number of characters that html output should be wrapped to. Default is 80.
    logwatch_html_wrap: 80

    #Inhibits additional name lookups, displaying IP addresses numerically.
    logwatch_numeric: 'No'


Example Playbook
----------------

    - hosts: servers
      roles:
         - role: thomo.logwatch
           logwatch_detail: 'Med'

License
-------

**MIT** - see LICENSE file for details.

Author Information
------------------

Thomas Mohaupt https://github.com/thomo/ansible-logwatch
