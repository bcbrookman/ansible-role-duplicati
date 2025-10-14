# Ansible Role: Duplicati

An Ansible role to install the Duplicati backup client on Linux. It downloads and installs Duplicati, configures it to run as a systemd service, and enables the web-interface on all interfaces.

## Requirements

This role is currently tested on the following platforms, but should also work on other modern Debian and RHEL based distros.

- Debian 12
- Debian 11
- Rocky Linux 9

> NOTE: You may have to override the `duplicati_dependencies` variable in your inventory when using other distros as package names may differ from distro to distro. See [Role Variables](#role-variables) below.

## Role Variables

|Variable|Description|Default Value|
|--------|-----------|-------|
|duplicati_download_url|The URL for the Duplicati release to be downloaded.|The latest stable release from [duplicati/releases](https://github.com/duplicati/duplicati/releases)|
|duplicati_download_dir|The directory where the Duplicati release will be downloaded.|`/tmp`|
|duplicati_dependencies|A list of apt/yum dependencies needed by Duplicati. This generally won't need to be overridden, but may be required when installing a different Duplicati release, or on other distros.|Varies by platform, but generally `[mono-devel]`|

## Dependencies

No other Ansible roles are needed as dependencies.

## Example Playbook

```yaml
- hosts: all
  roles:
      - bcbrookman.duplicati
```

## License

MIT

## Author Information

Brian Brookman (@bcbrookman)
