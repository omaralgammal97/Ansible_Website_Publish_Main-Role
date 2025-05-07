# 📡 Website Publish Ansible Role

This Ansible role automates the installation and configuration of an **Apache HTTP Server** on Red Hat-based systems. It enables serving a basic web page with customizable content on a user-defined port.

---

## 📁 Role Structure

```
Website_Publish-role/
├── defaults/
│   └── main.yml         # Default variables
├── tasks/
│   └── main.yml         # Main task definitions
├── templates/
│   └── index.html.j2    # Web page template
```

---

## ⚙️ Role Variables

| Variable         | Description                             |
|------------------|-----------------------------------------|
| `webserver_port` | The port number on which Apache listens |

> **Example variable configuration:**
> ```yaml
> webserver_port: 88
> ```

---

## ▶️ Usage Instructions

1. **Extract the Role Archive:**
   ```bash
   tar -xzvf Website_Publish-role.tar.gz
   ```

2. **Include the Role in Your Playbook:**
   ```yaml
   - name: Deploy a Custom Website
     hosts: webservers
     become: yes

     vars:
       webserver_port: 88

     roles:
       - Website_Publish-role
   ```

3. **Execute the Playbook:**
   ```bash
   ansible-navigator run -m stdout site.yml --pae=false
   ```

---

## 🛠️ Prerequisites

- A Red Hat-based Linux system (e.g., RHEL, CentOS)
- Ansible and Ansible Navigator installed
- Root or sudo privileges

---

## 👤 Author

**Omar Ali Al-Gammal**