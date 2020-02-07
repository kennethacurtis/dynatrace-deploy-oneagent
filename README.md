Role Name
=========

Deploy Dynatrace OneAgent on Windows or Linux.

Requirements
------------

None.

Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`):

Documentation on finding environment ID: https://www.dynatrace.com/support/help/reference/dynatrace-concepts/why-do-i-need-an-environment-id/

    tenant_url_dev: 'https://tenanturldev.org.com/e/environmentid'
    tenant_url_prod: 'https://tenanturlprod.org.com/e/environmentid'


    # switch value to 'prod' if you want to install in production and 'dev' for non prod deployment
    dynatrace_environment: dev

    # switch value to true if you want to install the latest version
    oneagent_version_latest: false


    # Documentation on custom OneAgent installs: https://www.dynatrace.com/support/help/technology-support/operating-systems/windows/installation/customize-oneagent-installation-on-windows/

    installer_type: 'default'

    # oneagent version must be in this format, e.g. '1.179.206.20191127-164958'
    oneagent_version: ''

    arch: 'all'

    # paas or tenant token
    paas_token: ''

    oneagent_installer_script_url_latest_dev: "{{ tenant_url_dev }}/api/v1/deployment/installer/agent/{{ os_type }}/{{ installer_type }}/latest/?Api-Token={{ paas_token }}&flavor=default&arch={{ arch }}"

    oneagent_installer_script_url_versioned_dev: "{{ tenant_url_dev }}/api/v1/deployment/installer/agent/{{ os_type }}/{{ installer_type }}/version/{{ oneagent_version }}/?Api-Token={{ paas_token }}&flavor=default&arch={{ arch }}"

    oneagent_installer_script_url_latest_prod: "{{ tenant_url_prod }}/api/v1/deployment/installer/agent/{{ os_type }}/{{ installer_type }}/latest/?Api-Token={{ paas_token }}&flavor=default&arch={{ arch }}"

    oneagent_installer_script_url_versioned_prod: "{{ tenant_url_prod }}/api/v1/deployment/installer/agent/{{ os_type }}/{{ installer_type }}/version/{{ oneagent_version }}/?Api-Token={{ paas_token }}&flavor=default&arch={{ arch }}"



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
