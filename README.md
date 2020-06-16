ssh-keygen
=========

A role foi elaborada para geração de um par de chaves no host master e instalada nos hosts slaves.
Ex: Você tem um parque de hosts que deseja automatizar tarefas usando Ansible ou Rundeck 
e não deseja informar a senha de acesso aos hosts nas suas tarefas.
Arole considera que o usuário usado para alcançar os hosts será o mesmo para a trocada de chaves.
Considera também que a porta ssh é a mesma para todos os hosts, masters e slaves.
Caso seu cenário seje diferente, revise a role.

Requirements
------------

Requer a instalação do sshpass
[yum, apt] install sshpass

Role Variables
--------------

defaults/main.yml
Declaração das variáveis WORDKDIR e KEYNAME

vars/main.yml
Declaração dos hosts alvo de instalação da chave

Example Playbook
----------------

- name: Troca de chaves de acesso SSH
  hosts: master_servers
  roles: 
    - ssh-keygen

Example Inventory
----------------

[master_servers]
Ansible ansible_ssh_host=localhost

[master_servers:vars]
ansible_connection=ssh
ansible_ssh_port=22
ansible_ssh_user=...usuario ssh... 
ansible_ssh_pass=...senha...
ansible_python_interpreter=/usr/bin/python2.7

License
-------

BSD

Author Information
------------------

Willian Romão
willian.romao@outlook.com.br
https://github.com/willianromao
