[![Build Status](https://travis-ci.org/ubuntunet/eduroam_tlr.png?branch=master)](https://travis-ci.org/ubuntunet/eduroam_tlr)

# Ansible Playbook for an eduroam Top Level Roaming Proxy

## Provisioning

- Clone the repository from Github

        git clone https://github.com/ubuntunet/eduroam_tlr.git

- Change into the newly created directory

        cd eduroam_tlr

- Copy the inventory template

        cp inventories/template inventories/<eduroam_tld>


- Open your new inventory and replace 
  - <FQDN or IP> with the actual URL/IP of your server
  - <eduroam_tld> with your actual inventory file name

- Copy the group_vars template

        cp group_vars/template group_vars/<eduroam_tld>

- Adopt the variables in group_vars/<eduroam_tld> to your liking

- Create the secret.yml file that contains your sensitive information. Add your credentials.

        cp group_vars/secrets.yml.example group_vars/secrets.yml

- Run the playbook. Whenever you change something in the playbook, just replay this command.

        ansible-playbook -i inventories/<eduroam_tld> tlr.yml

## Debugging

Follow the log of the Radius Proxy 

      tailf /var/log/radsecproxy.log
