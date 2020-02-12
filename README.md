Role Name
=========

Deploy Dynatrace OneAgent on Windows or Linux.

Requirements
------------

None.

Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`):


    # switch value to 'prod' if you want to install in production and 'dev' for non prod deployment
    dynatrace_environment: dev


    # Documentation on custom OneAgent installs: https://www.dynatrace.com/support/help/technology-support/operating-systems/windows/installation/customize-oneagent-installation-on-windows/

    installer_type: 'default'

    # oneagent version must be in this format, e.g. '1.179.206.20191127-164958'
    oneagent_version: ''

    arch: 'all'

    # paas or tenant token
    paas_token: ''

    # see install parameters for the oneagent in the OS specific vars in the vars folder
    # documentation for host groups: https://www.dynatrace.com/support/help/how-to-use-dynatrace/hosts/configuration/organize-your-environment-using-host-groups/
    oneagent_host_group: ''



Dependencies
------------

None.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: all
      roles:
        - kennethacurtis.dynatrace-deploy-oneagent

License
-------

BSD

Author Information
------------------

https://github.com/kennethacurtis
