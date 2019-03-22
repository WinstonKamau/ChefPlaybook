# learn_chef_apache2

TODO: Enter the cookbook description here.

## Setup a chef server
Create a chef server by creating an Ubuntu 16.04 instance and running the script under
setup-chef-server/install_chef_server_ubunut_16.04.sh

### Upload cookbook
knife cookbook upload learn_chef_apache2

### Confirm ssl configuration
knife ssl fetch
knife ssl check

### Bootstrap the node i.e install chef client and 
knife bootstrap {ip address} --ssh-user chef_user --sudo --identity-file {paht to private key} --node-name chef-node --run-list 'recipe[learn_chef_apache2]'

### Ssh to a chef node and do a chef-client run
knife ssh 'name:chef-node' 'sudo chef-client' --ssh-user chef_user --ssh-identity-file {path to private key} --attribute cloud.public_ipv4

### Search attributes for a chef node
knife search node "name:chef-node" -F json > p.json
