

in order to avoid ssh connection problems with Ansible add these lines to the .ssh/config

```
Host 127.0.0.1 192.168.222.?
  StrictHostKeyChecking no
  UserKnownHostsFile=/dev/null
```

what you need
==============
  - vagrant installed
  - ansible installed

install the code:
```bash
git clone https://github.com/mszel-blackbirdit/vagrant
```

then run the following 
```
cd vagrant/RainGauge-Ansible-Demo/
vagrant up
ansible-playbook site.yml -i hosts
````
after the playbook is finished log in to the db hosts in a separate window with:
```
vagrant ssh db1
vagrant ssh db2
```
run the following on each db host:
```
/usr/local/bin/sbtest.sh
```
....wait....

point your browser to:

http://localhost:8808/RainGauge/

