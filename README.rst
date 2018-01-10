ansible-meltdown-spectre-inventory
==================================

Generates an ansible-compatible inventory grouped by "patched", "unpatched" and
"amd" hosts at /tmp/meltdown-inventory.

Example::

    $ ansible-playbook -i <inventory> get-inventory.yml
    ...
    $ cat /tmp/meltdown-inventory
    [patched]
    some state=patched fqdn=some.example.org kernel=4.4.0-108-generic distribution=Ubuntu version=16.04
    another state=patched fqdn=another.example.org kernel=4.4.0-108-generic distribution=Ubuntu version=16.04
    host state=patched fqdn=host.example.org kernel=3.10.0-693.11.6.el7.x86_64 distribution=CentOS version=7.3.1611

    [unpatched]
    unpatched state=unpatched fqdn=unpatched.example.org kernel=4.4.0-104-generic distribution=Ubuntu version=16.04

    [amd]
    amd_host state=amd fqdn=amd_host.example.org kernel=2.6.32-696.18.7.el6.x86_64 distribution=CentOS version=6.9
