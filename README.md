# Fedora Guide

### AnyDesk
#### Run the following commands as root user
1) Add AnyDesk repository
```
cat > /etc/yum.repos.d/AnyDesk-Fedora.repo << "EOF" 
[anydesk]
name=AnyDesk Fedora - stable
baseurl=http://rpm.anydesk.com/fedora/$basearch/
gpgcheck=1
repo_gpgcheck=1
gpgkey=https://keys.anydesk.com/repos/RPM-GPG-KEY
EOF
```
2) Install Anydesk
```
dnf install anydesk
```
---

### Gnome Tweaks
```
sudo install gnome-tweaks
```

### 

## Rabbit SVN for nautilus (Files) GNOME
1) Install RabbitSVN with dependencies
2) Relocate RabbitVCS.py to enable menu options in nautilus.
3) Restart nautilus.
```
sudo dnf install python3-rabbitvcs rabbitvcs-nautilus nautilus-python
mkdir -p ~/.local/share/nautilus-python/extensions
sudo cp /usr/share/nautilus-python/extensions/RabbitVCS.py /home/.local/share/nautilus-python/extensions
sudo rm /usr/share/nautilus-python/extensions/RabbitVCS.py
nautilus -q
```
