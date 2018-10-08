# Usage
## Configuration
At a minimum, set envars
```
export OS_AUTH_URL=https://openstack-keystone:5000/v3
export OS_USERNAME=username
export OS_PASSWORD=supersecurepassword
```
Otherwise use `.envrc-example` to create your own `.envrc` and use direnv.

Edit `vars/config.yml` to customise

To use the loadbalancer playbook, you will need to create the `hosts` file from `hosts.example` and update it with somehwere that has access to neutron cli commands and a keystonerc file to source (look at the playbook if you want to see how it works)

## Run it
Run all playbooks
```
ansible-playbook -i hosts all.yml
```

Or run individual playbooks
```
ansible-playbook -i hosts project.yml # Create the project
ansible-playbook -i hosts users.yml # Create users in the project
ansible-playbook -i hosts network.yml # Set up the networks
ansible-playbook -i hosts security_groups.yml # Create security groups
ansible-playbook -i hosts security_group_facts.yml # List security groups
ansible-playbook -i hosts quotas.yml # Set quotas
ansible-playbook -i hosts loadbalancers.yml # Create load balancers
```

# Note
This is not really set up for anything more than building a demo environment.

Use it at your own risk
