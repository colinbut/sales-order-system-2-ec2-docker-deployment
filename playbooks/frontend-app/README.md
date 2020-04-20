Frontend App
=========

This Ansible role deploys a containerized sales-order-system-app frontend client app onto an EC2 instance within the Sales Order System 2.0 EC2 platform.

Requirements
------------

The EC2 instance is already provisioned using Terraform from the [Sales Order System 2.0: EC2 Infrastructre](sales-order-system-2-ec2-infrastructre). 

Role Variables
--------------

Variables from global vars and an environment specific variable file from the environment_vars directory.
"Extra Variables" will be passed in on the CLI to `ansible-playbook` using `--extra-vars` flag. See Usage section below.

Dependencies
------------

No dependencies.

Usage
----------------

e.g. to deploy into 'dev' environment...

```bash
ansible-playbook -i inventory/hosts deploy_frontend_app.yml \
  --extra-vars="ENV=dev MICROSERVICE_NAME=sales-order-system-app MICROSERVICE MICROSERVICE_VERSION=1.0.0-SNAPSHOT MICROSERVICE_PORT=80"
```

Note above example, we require to pass in an extra variable "ENV" in order to select the correct specific environment specific variable file to use.

License
-------

The Unlicense

Author Information
------------------

Colin But
www.colinbut.com
