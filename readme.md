# Fedora Deployment
Playbook for setting up my Laptop. Why? Because I'm lazy and I don't want to do it manually every time I reinstall my system. Whyyy? Because I can.


## Features 
- [x] Installs all my applications (dnf, flatpak)
- [x] Installs and configures VSCode 
- [x] Installs Docker 
- [x] Configures my gnome settings
- [x] Installs zsh, oh-my-zsh, and powerlevel10k theme
- [x] Restores from a backup, so I have all my sessions from before reinstalling, if I want to
- [x] Specific work-related configurations


## Installation & Usage
``` bash
sudo dnf install pipx python3-libdnf5 -y
pipx install --include-deps ansible
git clone https://github.com/danielkaramyshev/fedora-deployment.git
cd fedora-deployment/
ansible-galaxy install -r requirements.yml
ansible-playbook -i inventory.yml main.yml -K
```


### Create Backup
Simple playbook, which copy pastes all my day to day files which I want to easily restore after reinstalling my system.
``` bash
ansible-playbook -i inventory.yml backup.yml -K
```


### Configuration
Mainly in inventory.yml for overriding default variables. To see those, explore each role 
