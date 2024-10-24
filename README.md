# Ansible Role: Kerberos for Raspberry Pi

This Ansible role sets up and configures a Kerberos server on Raspberry Pi. It provides an easy way to manage Kerberos authentication for users and services in your network.

## Features

- **Automated Installation:** Installs and configures the Kerberos server with minimal manual intervention.
- **Key Distribution Center (KDC):** Configures a KDC for handling authentication requests.
- **Customizable Configuration:** Easily customize Kerberos settings, including realms, principals, and encryption types.
- **Lightweight:** Optimized for deployment on Raspberry Pi devices, making it suitable for small networks or personal projects.

## Requirements

- Raspberry Pi with a compatible OS (e.g., Raspberry Pi OS).
- Ansible installed on the control machine.
- Root or sudo privileges on the Raspberry Pi.

## Role Variables

Key configurable variables can be found in the `defaults/main.yml` file. Important variables include:

```yaml
# The Kerberos realm
kerberos_realm: "EXAMPLE.COM"

# The Kerberos domain name
kerberos_domain: "example.com"

# The admin principal
kerberos_admin_principal: "admin@EXAMPLE.COM"

# Kerberos password for the admin principal
kerberos_admin_password: "admin_password"
```

You can override these variables in your playbook or inventory files as needed.

## Example Playbook

Here's a sample playbook to utilize this role:

```yaml
---
- hosts: raspberrypi
  become: true
  roles:
    - role: ansible-kerberos-role-rpi
      vars:
        kerberos_realm: "MYREALM.COM"
        kerberos_domain: "myrealm.com"
        kerberos_admin_principal: "admin@MYREALM.COM"
        kerberos_admin_password: "securepassword"
```

## Installation

To install and use this role:

1. Clone the repository:
   ```bash
   git clone https://github.com/OddRefrigerator/ansible-kerberos-role-rpi.git
   ```

2. Include the role in your Ansible playbook.

3. Run the playbook to configure the Kerberos server on your Raspberry Pi:
   ```bash
   ansible-playbook -i inventory my-playbook.yml
   ```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Please feel free to submit issues or open a pull request if you have improvements or fixes.

### Steps for Contribution

1. Fork the repository.
2. Create a new branch for your feature or fix:
   ```bash
   git checkout -b feature-name
   ```
3. Commit your changes:
   ```bash
   git commit -m "Description of your feature or fix"
   ```
4. Push to your branch:
   ```bash
   git push origin feature-name
   ```
5. Open a pull request, detailing your changes.

## Author

This role was created by [OddRefrigerator](https://github.com/OddRefrigerator).

## Contact

For inquiries or issues, feel free to open an issue on GitHub or contact the repository owner.
