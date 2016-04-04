# Ansible backup-manager role

> `lr-agenceweb.ansible-backup-manager` is an [Ansible](http://www.ansible.com) role which:
>
> * installs backup-manager
> * do NOT export databases
> * configures export to an external FTP

## Installation

Using `requirements.yml`:

```yaml
- src: lr-agenceweb.ansible-backup-manager
```

## Dependencies

* Ansible >= 1.9

## Variables

Here is a list of all the default variables for this role, which are also available in `defaults/main.yml`.

```yaml
---
# Backup manager
backup_manager_conf:
  bm_frequency: daily # hourly / monthly / weekly
  bm_archive_ttl: 14 # Time to keep releases
  bm_upload_method: ftp # export option
  bm_upload_destination: /var/backups # export destination
  bm_upload_ftp_user: user # export ftp username
  bm_upload_ftp_password: password # export ftp password
  bm_upload_ftp_hosts: host # export ftp host
```


## Usage

This is an example playbook:

```yaml
---
- hosts: all
  become: yes
  roles:
    - lr-agenceweb.ansible-backup-manager
```

## License
Copyright &copy; L&R Agence web - MIT