
### Install OpenLdap Single/Dual Primary & Client


# Install ansible & dependency package
pip3 install -r requirements.txt

## Default Information

### Package Version
OpenLDAP: v2.5.7
pgchecker : latest


### Server 
OpenLDAP Primary1
* OS : Rocky 8.4
* IP : 10.0.0.10

OpenLDAP Primary2
* OS : Rocky 8.4
* IP : 10.0.0.20

OpenLDAP Client
* OS : CentOS 7.10
* IP : 10.0.0.30

* OS : Rocky 8.4 
* IP : 10.0.0.40


## Generate TLS/SSL
'''
openssl req -x509 -nodes -days 365 \
  -newkey rsa:2048 \
  -keyout /etc/pki/tls/HallsHolicker-private.key \
  -out /etc/pki/tls/HallsHolicker-private.crt
'''


## Run
ansible-playbook -i inventories/opneldap/hosts OpenLdapInstall.yml -k