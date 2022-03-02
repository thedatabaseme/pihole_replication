piHole Replication Playbook
=========

This Playbook enables you to replicate a piHole Configuration from one piHole Server to another

Requirements
------------

- Ansible 2.7

Playbook Variables
--------------

Variables to be specified when running the Playbook:

    pihole_source_host: Defines the piHole Source Server from which the Configuration should be replicated from
    pihole_target_host: Defines the piHole Configuration Replication Target

Default Variables:

    pihole_home: '/etc/pihole/'
    pihole_gravity_db: '{{ pihole_home }}gravity.db'
    pihole_config: '{{ pihole_home }}pihole-FTL.conf'
    pihole_customlist: '{{ pihole_home }}custom.list'
    pihole_adlist: '{{ pihole_home }}adlist.csv'
    pihole_domainlist: '{{ pihole_home }}domainlist.csv'
    pihole_dhcpleases: '{{ pihole_home }}dhcp.leases'
    dnsmasq_home: '/etc/dnsmasq.d/'
    dnsmasq_cnamelist: '{{ dnsmasq_home }}05-pihole-custom-cname.conf'
    pihole_user: pihole
    pihole_group: pihole
    update_gravity_on_source: true

When setting `update_gravity_on_source`, a Gravity DB update will take place on the source host before the actual replication starts.

More Informations
------------

None

Example Playbook
----------------

An example Playbook Call looks like this. Ofcourse you may want to specify the Variables within your Playbook or within your Inventory:

    - ansible-playbook pihole_replication.yml -i hosts -e "pihole_source_host=piholesource pihole_target_host=piholetarget" -u username -k -K

Author Information
------------------

This Role is created by P. Haberkern (thedatabaseme)
