## alban.andrieu.subversion

[![Travis CI](http://img.shields.io/travis/AlbanAndrieu/ansible-subversion.svg?style=flat)](http://travis-ci.org/AlbanAndrieu/ansible-subversion) [![Branch](http://img.shields.io/github/tag/AlbanAndrieu/ansible-subversion.svg?style=flat-square)](https://github.com/AlbanAndrieu/ansible-subversion/tree/master) [![Donate](https://img.shields.io/gratipay/AlbanAndrieu.svg?style=flat)](https://www.gratipay.com/AlbanAndrieu)  [![Ansible Galaxy](http://img.shields.io/badge/galaxy-alban.andrieu.subversion-blue.svg?style=flat)](https://galaxy.ansible.com/list#/roles/1511) [![Platforms](http://img.shields.io/badge/platforms-ubuntu-lightgrey.svg?style=flat)](#)

Ensures that subversion is installed (using `apt`)

### Installation

This role requires at least Ansible `v1.6.3`. 

To install it, run:

    ansible-galaxy install alban.andrieu.subversion



### Role variables

List of default variables available in the inventory:

```yaml
    subversion_enabled: yes                       # Enable module
    
    subversion_previous_enabled: yes              # Enable for subversion 1.6
    #subversion_previous_codename: {{ ansible_lsb.codename }}
    subversion_previous_codename: precise
    
    #Ubuntu 13
    #subversion_major: '1'
    #subversion_minor: '6'
    #subversion_revision: '17'
    #subversion_version: "{{subversion_major}}.{{subversion_minor}}.{{subversion_revision}}"
    #subversion_ubuntu: '{{ subversion_version }}dfsg-3ubuntu3'
    
    #Ubuntu 14
    subversion_major: '1'
    subversion_minor: '8'
    subversion_revision: '8'
    subversion_version: "{{subversion_major}}.{{subversion_minor}}.{{subversion_revision}}"
    subversion_ubuntu: '{{ subversion_version }}-1ubuntu3.1'
    
    #user: 'albandri' #please override me
    user: "{{ lookup('env','USER') }}"
    subversion_owner: "{{ user }}"
    subversion_group: "{{ subversion_owner }}"
    #home: '~' #please override me
    home: "{{ lookup('env','HOME') }}"
    subversion_owner_home: "{{ home }}"
    subversion_config_dir: "{{ subversion_owner_home }}/.subversion"
    #use meld or xxdiff-subversion or xx-diff-proxy 
    subversion_diff_cmd: meld
    subversion_merge_tool_cmd_directory: /usr/bin/
    subversion_merge_tool_file: "svn-merge-meld.sh"
    subversion_diff3_cmd: "{{ subversion_merge_tool_cmd_directory }}/{{ subversion_merge_tool_file }}"
    subversion_merge_tool_cmd: "{{ subversion_diff3_cmd }}"
    #subversion_merge_tool_cmd: svn-merge-meld.py
    
    subversion_rabbitvcs_enabled: yes                       # Enable module
    subversion_diff_enabled: yes                            # Enable module
```


### Detailed usage guide

Run the following command :

`ansible-playbook -i hosts -c local -v subversion.yml -vvvv --ask-sudo-pass | tee setup.log`


### Authors and license

`alban.andrieu.subversion` role was written by:
- [Alban Andrieu](fr.linkedin.com/in/nabla/) | [e-mail](mailto:alban.andrieu@free.fr) | [Twitter](https://twitter.com/AlbanAndrieu) | [GitHub](https://github.com/AlbanAndrieu)
- License: [GPLv3](https://tldrlegal.com/license/gnu-general-public-license-v3-%28gpl-3%29)

### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/AlbanAndrieu/ansible-subversion/issues)!

***

README generated by [Ansigenome](https://github.com/nickjj/ansigenome/).
