# Ansible Role: LaTeX TeX Live

Install LaTeX TeX Live via DVD download.

- Download and verify (sha512) the specified Tex Live DVD ISO
- Install GUI for Installer
- Mount the ISO and install TeX Live from mounted ISO with given options
- Adjust the Path
- Add CTAN repo to TeX Live
- Prevent TeX Live packages from being installed as a dependency by the package manager with the help of a downloaded equivs file
- Remove texlive-doc packages (configurable)

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

| Name           | Default Value   | Description                        |
| -------------- | --------------- | -----------------------------------|
| `download_dir_on_remote_host` | "/home/{{ ansible_user }}/Downloads/automatically_by_ansible_playbook" | Download Base Directory on Remote Host |
| `latex_texlive.texlive.version` | "2023" | TeX Live Version you want to install |
| `latex_texlive.texlive.install_options` | "--paper=a4 --no-doc-install --no-src-install" | Additional TeX Live installation options you want to use |
| `latex_texlive.equivs.version` | "2022" | Equivs version to use to prevent TeX Live packages from being installed as a dependency by the package manager |
| `latex_texlive.remove_texlive_doc` | "true" |  Whether texlive-doc packages should be removed |

## Dependencies

None.

## Example Playbook

```yaml
---
- hosts: all
  gather_facts: yes
  become: true

  roles:
    - role: jakoblichterfeld.latex_texlive

```

## License

MIT

## Author Information

This role was created in 2023 by [Jakob Lichterfeld](https://github.com/JakobLichterfeld).
