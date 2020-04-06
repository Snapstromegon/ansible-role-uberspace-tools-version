# Ansible Role: uberspace-tools-version

This is part of the uberspace roles collection.

This is meant to be used on your [Uberspace](https://uberspace.de/).

Please be aware, that I'm neither part of the Uberspace team, nor am I associated to them other than having some Uberspaces myself.
This project was created, because I wanted to use the roles for myself and thought they were okay-ish enough to share them.

## What is this

You can use mailboxes in the form of $MAILBOX@$USER.uber.space. If you have set up additional domains, $MAILBOX@$DOMAIN will also work.

You can find the documentation of the replaced tool `uberspace tools version` in the Uberspace Manual [here](https://manual.uberspace.de/).

## Usage

| Variable | Choices/Default | Description                                                                |
| :------: | :-------------- | :------------------------------------------------------------------------- |
|   tool   |                 | The name of the tool you want to set the version for                       |
| version  |                 | The version of the tool to use (look at the manual for available versions) |
|  tools   | []              | A list of tool, version combinations to set multiple users at once         |

## Examples

### Set tool version

```yaml
- hosts: uberspace
  roles:
    - name: uberspace-tools-version
      tool: node
      version: 12
```

### Set multiple tool versions

```yaml
- hosts: uberspace
  roles:
    users:
      - name: uberspace-tools-version
        tool: php
        version: 7.1
      - name: uberspace-tools-version
        tool: node
        version: 12
```
