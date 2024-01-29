1. inventory.ini
[myhosts]
192.168.1.32

2. verify your inventory
ansible-inventory -i inventory.ini --list

3. ping the myhosts group in your inventory
ansible myhosts -m ping -i inventory.ini

4. playbook.yaml
- name: My first play
  hosts: myhosts
  tasks:
   - name: Ping my hosts
     ansible.builtin.ping:

   - name: Print message
     ansible.builtin.debug:
      msg: Hello world

5. run playbook
ansible-playbook -i inventory.ini playbook.yaml