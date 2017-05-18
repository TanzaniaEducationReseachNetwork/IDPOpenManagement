# IDPOpen Management (for Shibboleth 3)

This repository contains a demonstrative [Ansible](www.ansible.com) playbook for migrating legacy Shibboleth-2 identity providers to Shibboleth-3.  

It contains :

  1. An example playbook `migration.yml`
  2. Two roles as submodules
    * `roles/osct.shiboleth-idp-v3` for the shibboleth-3 configuraiton
    * `roles/osct.tomcat-8` for the tomcat layer configuration.
  1. An example inventory `inventory.hosts`
  2. Supporting files (images, stylesheets) in `files`


# How to use this repository

----
Short answer : _don't_. This repository was created just to test the two roles :smile:

----

**Note**: the playbook `migration.yml` is not suitable for re-use as-is. It merely demonstrates how to write a simple playbook to use the Shibboleth-3 role starting from an existing setup. See below for how to deplo

## If you want to deploy a Shib-v3 IdP

If you want to deploy a Shibboleth-3 Identity Provider in a Federation, take the following steps :

  1. Get Ansible - http://docs.ansible.com/ansible/intro_installation.html
  2. Go to your local toolbox, where you keep your playbooks  and roles. (_e.g._ `DevOps/Ansible`)
  3. Install the Ansible roles from [Galaxy](https://galaxy.ansible.com) : `ansible-galaxy install -p roles/ osct.shibboleth-idp-v3` (assuming that your roles are in `roles` subdirectory.)
  5. Prepare your inventory (see `inventory.hosts` for an example). Note : you can add a `idpv3` group and add the variables from `host_vars` to `group_vars/idpv3.yml`. See variables section below.
  6. Update the inventory variables (group, or host variables), and the variables  in the roles (see variables section below) :
    7. `roles/osct.shibboleth-idp-v3/[vars,default]/main.yml`
    8. `roles/osct.tomcat-8/[vars,default]/main.yml`
    See the respective `README.md`s of these roles for a description of the variables.
  1. Run your playbook : `ansible-playbook my-migration.yml`

# Support and Feedback.

There's not much here to see, but if you would like to discuss these roles, please open an issue on their respective repos :

  1. [Shib3 role](https://github.com/osct/shibboleth-idp-v3/issues/new)
  2. [tomcat-8 role](https://github.com/osct/tomcat-8/issues/new)

See [this discussion topic](http://discourse.sci-gaia.eu/t/shibboleth-idp-v3-on-idpopen/) as well.
