# JiraBox

Vagrant box for setting up local Jira server.

Steps:

- Create an `ansible/vars/all.yml` file and configure your setup there.

For example, this is how it might look like:

```yaml
---
vagrant_local:
    hostname: jira
pgsql:
    database: jira
    user: jira
    password: secret
java:
    version: 8
    subversion: 121
    install_dir: /usr/local/java
    set_javahome: true
jira:
    gid: ~
    hash_salt: jira
    pass: secret
    uid: ~
    user: jira
```

- Download JRE from Oracle website to `ansible/files` directory e.g. `server-jre-8u121-linux-x64.tar.gz`. Update your variable with the version of Java you downloaded.

- Run `vagrant up`
