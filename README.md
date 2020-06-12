# Ansible Role: `jd_gui`

Installs or uninstalls [JD-GUI](http://java-decompiler.github.io/) - a
standalone graphical utility that displays Java sources from CLASS files.
Creates or removes a wrapper to start the program from the shell.

## Requirements

- A recent version of Ansible. Tested on 2.9. It might work on previous versions.
- Fedora 31. It might work on other versions.
- Access to an archive of JD-GUI release. Either by URL to download or
  path to a file.

## Role Variables

All variables which can be overridden are stored in
[defaults/main.yml](defaults/main.yml) file and listed in a table bellow as
well.

| Name                 | Default Value | Description  |
| -------------------- | ------------- | ------------ |
| `jd_gui_archive_src` | ""            | Path to a release archive of JD-GUI on a control host or URL to download the archive from. |
| `jd_gui_state`       | present       | By default installs the program. Set to "absent" to uninstall. |

`jd_gui_archive_src` must be overriden from its default value.

## Example Playbook

### Install

To install the program, define path to a JD-GUI release archive from the
internet:

```yaml
- hosts: all
  roles:
    - role: scrool.jd_gui
      vars:
        jd_gui_archive_src: https://github.com/java-decompiler/jd-gui/releases/download/v1.6.6/jd-gui-1.6.6.rpm
```

### Uninstall

To uninstall, set state variable to "absent":

```yaml
- hosts: all
  roles:
    - role: scrool.jd_gui
      vars:
        jd_gui_state: absent
```

## License

This project is licensed under MIT License. See [LICENSE](LICENSE) for more
details.

See [JD-GUI home page](http://java-decompiler.github.io/) for license
information.

## Author Information

- [Pavol Babinčák](https://github.com/scrool)
