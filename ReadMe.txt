#https://stackoverflow.com/questions/64905347/how-does-ansible-find-the-location-of-inventory-group-vars-all-yaml-user-vars

commands:
ansible-playbook -v -i inventories/stage --extra-vars server_env_group="stageservers" main_playbook.yml
ansible-playbook -v -i inventories/prod --extra-vars server_env_group="prodservers" main_playbook.yml

Structure:

.
├── inventories
│   ├── stage
│   │   ├── group_vars
│   │   │   └── stageservers.yml
│   │   └── host
│   └── prod
│       ├── group_vars
│       │   └── prodservers.yml
│       └── hosts
├── main_playbook.yml
└── roles
    └── common
        └── tasks
            └── main.yml


