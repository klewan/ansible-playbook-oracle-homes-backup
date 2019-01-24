Ansible Playbook: oracle-homes-backup
============================================

This playbook performs backup of ORACLE_HOMEs of a particular Oracle server.

In case when the host is a member of a RAC cluster, the playbook peforms backup of ORACLE_HOMEs on all nodes of the RAC (when _oracle_homes_backup_rac_support=true).


Supported OS:
-------------
* RedHat
* CentOS
* OracleLinux


Requirements
------------

This playbook requires following roles:

* `oracle-gatherinfo-gi` 
* `oracle-gatherinfo-databases` 
* `oracle-homes-backup` 

`$ ansible-galaxy install -r roles/requirements.yml`

ORACLE_HOME to be backed up is passed to `oracle-homes-backup` role as `oracle_homes_backup_ora_home` variable.


Examples
--------

    $ ansible-playbook playbook.yml --list-tasks
    $ ansible-playbook playbook.yml --list-tags

Default execution:

    ansible-playbook playbook.yml

Perform backup of ORACLE_HOMEs without RAC support (i.e. it will not backup ORACLE_HOMEs on other/remote RAC nodes)

    ansible-playbook playbook.yml --extra-vars='{"_oracle_homes_backup_rac_support": false}'


License
-------

GPLv3 - GNU General Public License v3.0

Author Information
------------------

This playbook was created in 2018 by [Krzysztof Lewandowski](mailto:Krzysztof.Lewandowski@fastmail.fm).

