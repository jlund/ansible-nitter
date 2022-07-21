# ansible-nitter

A simple Ansible playbook that sets up and configures a fully functional [Nitter](https://github.com/zedeus/nitter) server (Nitter + Redis + [Caddy](https://caddyserver.com/) w/ HTTPS).

This playbook was used to set up the Unofficial Bird public Nitter instances:
- https://unofficialbird.com (🇺🇸)
- https://canada.unofficialbird.com (🇨🇦)
- https://india.unofficialbird.com (🇮🇳)
- https://nederland.unofficialbird.com (🇳🇱)
- https://singapore.unofficialbird.com (🇸🇬)
- https://uk.unofficialbird.com (🇬🇧)

## Setup Instructions
1. Launch a Ubuntu 22.04 VPS and point a domain or subdomain to its new IP.
2. [Install](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) Ansible (unless you already have it!).
3. Clone this repo.
4. Copy and modify the example inventory file:
   * `cp inventory.example inventory && vim inventory`
     * Change `123.456.789.012` to the IP of your new Ubuntu 22.04 server.
     * Change the `nitter_hostname` value to the domain or subdomain you've chosen.
     * Change the `hmac_key` value to something random. Let your cat walk on your keyboard, or use the output from something like `openssl rand -hex 32`.
5. Run the Ansible playbook:
   * `ansible-playbook -i inventory playbook.yml`
6. Visit your new Nitter instance!
