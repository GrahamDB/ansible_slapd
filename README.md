Role Name
=========

install openldap servers on CentOS - should work on RH too

Requirements
------------

none

Role Variables
--------------
defined in vars/main.yml and vars/CentOS.yml

  * ldap_domain      - example
  * ldap_domain_ex   - net 
  * ldap_suffix      - constructed from variables above example.net
  * ldap_admin_dn    - cn=manager,{{ ldap_suffix }}
  * ldap_admin_password - 123Soleil - should be in a vault ...)
  * ldap_packages    - liste of packages - should be the only thing to change to
    adapt to other distro
  * ldap_service     - name of service unit file - slapd
  * ldap_user        - slapd service account
  * import_data      - bool - control wether we import initial data from LDIF files you will have put in templates subdirectory. Default No
  * ldap_schemas     - list of additionnal schema names to load - default cosine

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

      - hosts: servers
      roles:
         - role: slapd
           vars:
              ldap_domain: example
              ldap_domain_ex: net
              import_data: true
              ldap_schemas:
              - cosine
              - nis
              - inetorgperson

License
-------

BSD
Author Information
------------------

Thomas C <thomas@opendoor.fr>
