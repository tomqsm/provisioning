# provisioning
## Limitations
For sake of security this repo doesn't contain required 'fromtemplate' (needs to be created, execution of plays will load it with files) folder and ansible-vault password file and will not run as such.

## droplets_api playbook
With DigitalOcean REST API setup 'droplets'

`ansible-playbook droplets_api.yml --tags createDropletsRequest,createDroplets,listDroplets,createVolumesRequest,createVolumes,listVolumes,createAttachVolumesRequest,attachVolumes,update_inventory,host_variables --vault-password-file pass`

`ansible-playbook droplets_api.yml --tags [power_on | power_off] --vault-password-file pass`

## droplets_root playbook
Perform the following securing operations on created droplets: setup new user with password, enable user's ssh connectivity, forbid root sccees and password access, reload ssh.

## droplets_user playbook
Install packages required by Ansible to controll docker-compose, create docker-compose files, upload to droplets and start docker-compose.

## name_api playbook
Update DNS records. 
`ansible-playbook name_api.yml --vault-password-file pass`