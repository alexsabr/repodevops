ALEXANDRE
SABRI
21986486
M2 GENIAL
command to launch the ansible playbook containing everything to run a small application.
ansible-playbook  -i inventories/setup.yml  playbook2.yml

You'll need to change the path in inventories/setup.yml
to another private rsa key if you want to connect via ansible
/ through SSH ! 
