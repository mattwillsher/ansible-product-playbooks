This repo contains largely generic playbooks. 

It is expected this repo lives in a folder called products alongside another called clients, where the client specific playbooks live. E.g

```
products/
  atlassian/
  vagrant/
clients/
  default/
  myclient/
```

A variable, <code>$client_shortname</code>, must be defined for all hosts.

Playbooks are pretty CentOS/RHEL specific at the moment.

Contents
--------

### atlassian
Installs and configure Jira and/or Confluence. Again,see the [README](products/atlassian/README.md)

### postgresql
Basic install of PostgreSQL server on CentOS. 

### vagrant

Creates a vagrant folder at the top level with a configuration suitable for ansible development. Edit the producted inventory.ini and playbook.yml to suit. More information in the [README](products/vagrant/README.md).

