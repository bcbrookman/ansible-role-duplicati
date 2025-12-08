# Ansible Role: Duplicati

An Ansible role to install the Duplicati backup client on Linux. It downloads and installs Duplicati, configures it to run as a systemd service, and enables the web-interface on all interfaces.

## Requirements

This role is currently tested on the following platforms, but should also work on other modern Debian and RHEL based distros.

- Debian 12
- Debian 11
- Rocky Linux 9

> [!NOTE]
> You may have to override the `duplicati_dependencies` variable in your inventory when using other distros as package names may differ from distro to distro. See [Role Variables](#role-variables) below.

## Role Variables

|Variable|Description|Default Value|
|--------|-----------|-------|
|duplicati_package_release|The [Duplicati release](https://github.com/duplicati/duplicati/releases) to download and install. |`"v2.1.0.5_stable_2025-03-04"`|
|duplicati_package_os|The OS component of the Duplicati package to download and install.|Automatically determined|
|duplicati_package_arch|The architecture component of the Duplicati package to download and install.|Automatically determined|
|duplicati_package_type|The install type component of the Duplicati package to download and install.|`"gui"`|
|duplicati_package_extension|The file extension component of the Duplicati package to download and install.| Automatically determined|
|duplicati_download_url|The URL for the Duplicati release to be downloaded. Ignores `duplicati_package_*` variables if set. |Automatically generated|
|duplicati_download_dir|The directory where the Duplicati release will be downloaded.|`"/tmp"`|
|duplicati_dependencies|A list of apt/yum dependencies needed by Duplicati. This generally won't need to be overridden, but may be required when installing a different Duplicati release, or on other distros.|Varies by platform, but generally `[mono-devel]`|

> [!NOTE]
> If needed, refer to the assets attached to the desired [Duplicati release](https://github.com/duplicati/duplicati/releases) for the possible `duplicati_package_*` variable values. The installation package names follow the convention `duplicati-<RELEASE>-<OS>-<ARCH>-<TYPE>.<EXTENSION>`. You can also ignore these variables entirely by manually setting the `duplicati_download_url` variable.

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
