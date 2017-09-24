# Unifi-SSL

Installs SSL certificates for Unifi, Unifi Video and Unifi CloudKey platforms.

## Requirements

- Python >= 2.6
- OpenSSL
- Hosts running Unifi, Unifi Video or a Unifi Cloudkey

## Role Variables

Available variables are listed below, along with default values.

### Required Fields:

    crt_full_path: "" # Full path to certificate file on remote system
    key_full_path: "" # Full path to signing key on remote system
    intermediate_full_path: "" # Full path to intermediate certificate on remote system

### Important Notes:
It is **strongly reccomended** to use a "Full Chain" certfificate when deploying to a Unifi Video system. There may be issues with Live Playback and other websocket functions if one is not used.

## Example Playbook

    - hosts: unifi
      tasks:
      
      - name: Apply new SSL certificates
        include_role:
          name: unifi-ssl
        vars:
          crt_full_path: "/etc/ssl/certificates/cert.pem"
          key_full_path: "/etc/ssl/certificates/cert.key"
          intermediate_full_path: "/etc/ssl/certificates/intermediate.crt"

# TODO:

- Add support for copying certificate files located on host machine
- Add support for non-Debian Unifi-Video 
- Improve overall structure

# License

MIT

# Author Information

Created in 2017 by [Ben Dews](bendews.com)
