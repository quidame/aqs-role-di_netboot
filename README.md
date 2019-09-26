# di_netboot

Ansible role to download and unpack debian-installer, and optionnally install
custom menus.

This role is a piece of (*yet another*)
[Ansible Quick Starter](/aqs-common) (**AQS**).

## Requirements

None.

## Role Variables

The main action the role is called for. Choices are `setup` (the default) and
`unset`.
```yaml
di_netboot__action: unset
```

The directory where to unpack the debian-installer netboot tarball.
```yaml
di_netboot__path: /srv/tftp
```

The debian-installer's architecture.
```yaml
di_netboot__arch: amd64
```

The debian-installer's version (`stable`, `testing`).
```yaml
di_netboot__version: stable
```

The host to download the package from.
```yaml
di_netboot__host: ftp.debian.org
```

## Dependencies

None.

## Installation

To make use of this role as a galaxy role, put this in `requirements.yml`:

```yaml
- name: "di_netboot"
  src: "https://github.com/quidame/aqs-role-di_netboot.git"
  scm: "git"
  version: master
```

And then run:

```bash
ansible-galaxy install -r requirements.yml
```

## Example Playbook

Download and unpack debian-installer netboot:
```yaml
- hosts: pxe
  roles:
    - role: di_netboot
```

Remove debian-installer netboot tree:
```yaml
- hosts: pxe
  roles:
    - role: di_netboot
      di_netboot__action: unset
```

## License

GPLv3

## Author Information

<quidame@poivron.org>
