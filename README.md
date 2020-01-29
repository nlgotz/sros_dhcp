# sros-dhcp

Playbooks to get current DHCP Servers under VPRN interfaces and update them

Please update group_vars/all.yml with current DHCP Servers and Future DHCP
Servers before running

Please update mpls with all nodes you want to run this on

## How to Run

1. Run the Playbook to Gather DHCP Interfaces

    ansible-playbook -i mpls gather_dhcp_interfaces.yml

2. Review Nodes and Interfaces (host_vars/<Node>.yml)

3. Review Node Interfaces that don't match the supplied current DHCP
configuration (bad_interfaces.csv)

4. Run the Playbook to Push the changes out

    ansible-playbook -i mpls update_dhcp_interfaces.yml

