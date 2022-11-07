gearboxscott.controller.role_export_credential_input_sources
=========

This role will generate a file that contains a export of the credential input sources defined manually in Ansible Automation Controller GUI. This file can be include to setup credential input sources using `ansible.controller.credential_input_source` from the `ansible.controller` collection. This allows for restoration or configuration changes of the input sources using configuration-as-code options.

Requirements
------------

This role requires the collection `ansible.controller`.

Role Variables
--------------

---
| Variable | Type | Defaults | Description |
|-|-|-|-|
| `controller_hostname` | String/<span style="color:red">_required_</span> | none | URL to your Automation Platform Controller instance. |
| `controller_username` | String/<span style="color:red">_required_</span> | `admin` | Username for your controller instance. |
| `controller_password` | String/<span style="color:red">_required_</span> | none` | Password for your controller instance.|
| `controller_validate_certs` | Boolean/<span style="color:red">_required_</span> | `false` | Whether to allow insecure connections to Controller. |
| `yaml_file` | String/<span style="color:red">_required_</span> | none | `current_credential_input_sources.yml` | File to receive the exported data. |

Dependencies
------------

Existing credential input sources have been defined in Ansible Automation Controller.

Example Playbook
----------------

Here is a sample of how to use this role:

* Fill out the `defaults/main.yml` variables so this role can perform it's tasks.

* Fill out the `collections/requirements.yml` with:

```yaml
---
collections:
  - name: ansible.controller
  - name: gearboxscott.controller

```

* Create a playbook to call the role:

```yaml
- name: Export Credential Input Sources
  hosts: localhost
  connection: local
  gather_facts: false

  roles:
    - gearboxscott.controller.role_export_credential_input_sources
```

License
-------

GPL

Author Information
------------------

Scott Parker (sparker@redhat.com)