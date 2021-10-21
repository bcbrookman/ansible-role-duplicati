# Ansible Role: Duplicati

This is a simple Ansible role I use to install the Duplicati backup client on my Debian and Debian-like systems. It downloads and installs Duplicati, configures it to run as a systemd service, and enables the web-interface on all interfaces.

## Requirements

This role currently only runs on Debian and Debian-like systems. 

## Role Variables

No variables can currently be set.

## Dependencies

No other Ansible roles are needed as dependencies.

## Example Playbook

    - hosts: servers
      roles:
         - duplicati

## License

MIT

## Author Information

Brian Brookman (@bcbrookman)
