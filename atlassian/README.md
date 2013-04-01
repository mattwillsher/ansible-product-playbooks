Atlassian Playbooks
===================

This playbook performs a basic install of Jira & Confluence. The following variables are required:

* product - provide as a playbook parameter variable and set to the product to install e.g. jira, confluence e.g. ```- include: atlassian/install_product.yml product=jira```

Other variables need to be set. The name of them is product dependent. For Jira:

* jira_database_server - the IP address of the DB server to use. Current only localhost is tested
* jira_version - the version to install e.g. 5.2.9
* jira_rmiPort - Port to run RMI on e.g. 8005
* jira_httpPort - Port to listen for HTTP requests on e.g 8080

For Confluence, substitute jira for confluence in the above variables.

The generated database password will be stored in <code>../../$client_shortname/credentials/jira/database</code>.
