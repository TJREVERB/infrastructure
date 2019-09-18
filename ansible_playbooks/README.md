# Infrastructure
## Ansible Playbooks
### Playbooks to setup flight and engineering model computers

#### How to use
** Make sure [ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) is installed on your system **

1. Login on `pi-cubesat`
2. Preconfigure hosts
	* Configure networking for each host
		- Assign IPs
		- Setup routes
		- Setup hostname
	* Set root password
		- `sudo passwd`
	* Configure preliminary ssh
		- Allow root password login
		- Restart sshd server
3. Copy over `pi-cubesat` ssh key onto each host
	* `ssh-copy-id -i ~/.ssh/id_rsa.pub root@[HOST]`
4. Add each host to `hosts` file
5. Run playbooks
	* `ansible-playbook -i hosts [PLAYBOOK].yml`

#### To Run ALL Playbooks
`ansible-playbook -i hosts sites.yml`

#### To Run SPECIFIC Playbook
`ansible-playbook -i hosts [PLAYBOOK].yml`


### Structure

```
- group_vars
- helper_scripts
- host_vars
- public_keys
- roles
	- [role_name]
		- files
			- [file]
		- tasks
			- main.yml
			- [task].yml
		- template
			- [file].j2
	- *OTHER ROLES*
- site.yml
- [playbook_name].yml
- *OTHER PLAYBOOKS*
- README.md
- hosts
```

### Usage
* group_vars
	* Directory for variables common for a certain group
	* e.g. `flight` NOT `flight-pi`
	* Read more about (variables)[https://docs.ansible.com/ansible/latest/user_guide/playbooks_variables.html]

* helper_scripts
	* Directory for scripts to be run on remote host

* host_vars
	* Directory for variables specific to a certain host
	* e.g. `blind1` NOT `blinds`
	* Read more about [variables](https://docs.ansible.com/ansible/latest/user_guide/playbooks_variables.html)

* public_keys
	* Directory for user PUBLIC ssh keys
	* Preferably id_rsa.pub
	* File name should be hostname of client

* roles
	* Directory for ansible roles
	* More about [roles](https://docs.ansible.com/ansible/latest/user_guide/playbooks_reuse_roles.html)

* [playbook_name].yml
	* Ansible Playbook for certain group
	* End in .yml
	* Should be in following format:
	```
	- name: {Playbook Name}
	  hosts: {Group Name}
	  remote_user: root{Or specific user}
	  vars:
	  	{Any specific variables}
	  	variable_name: variable_value
	  roles:
	    {Any relevant roles}
	    - role_name
	```
	* Define tasks in `roles` not in playbook.yml
	* Read more about [playbooks](https://docs.ansible.com/ansible/latest/user_guide/playbooks.html)

* sites.yml
	* Main playbook to run all playbooks
	* `ansible-playbook -i hosts sites.yml`
	* Should be in following format:
	```
	- import_playbook: {playbook_name}.yml
	```

* hosts
	* File that defines remote hostnames to a group name
	* Should be in the following format
	```
	[{group_name}]
	{host_names}

	[{group_name}]
	{host_name}
	```

	* Read more about [hosts](https://docs.ansible.com/ansible/latest/user_guide/intro_inventory.html)

### Role Structure
* Follow the [ansible best practices](https://docs.ansible.com/ansible/latest/user_guide/playbooks_best_practices.html)
* `tasks`
	* Tasks to run
	* Tasks defined in `main.yml` will be executed
	* Tasks can be placed in other files and referenced by the `import_tasks` key
* `files`
	* Place to store all static files to be copied over onto remote host
	* Can retain original file extension
* `templates`
	* Place to store all files that change depending on remote system
	* Edit file using [Jinja2 syntax](http://jinja.pocoo.org/docs/2.10/)
	* Add .j2 to filename