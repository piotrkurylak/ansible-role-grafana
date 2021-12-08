## Role Name: Grafana

Ansible role which allows you to install Grafana on Debian systems.

## Requirements

None.

## Role Variables

Release channel. You can switch to beta releases if you want.
````yaml
grafana_apt_release_channel: "stable"
````

Grafana prerequisites.
````yaml
grafana_prerequisites: [gnupg2, apt-transport-https]
````

Grafana repository.
````yaml
grafana_apt_repo: "deb [signed-by={{ grafana_apt_keyring_path }}] https://packages.grafana.com/enterprise/deb {{ grafana_apt_release_channel }} main"

````

Grafana GPG key.
````yaml
grafana_apt_key_url: "https://packages.grafana.com/gpg.key"
````

Path to Grafana keyring file.
````yaml
grafana_apt_keyring_path: "/usr/share/keyrings/grafana-archive-keyring.gpg"
````

Location of Grafana config file.
````yaml
grafana_config_file: "/etc/grafana/grafana.ini"
````

Grafana port. You can change it if you want, default port is 3000.
````yaml
grafana_http_port: 3000
````

## Dependencies

None.

## Example Playbook

````yaml
    - hosts: all
      become: yes
      roles:
         - ansible-role-grafana
````

## License

MIT / BSD

## Author Information

Role created by Piotr Kurylak.