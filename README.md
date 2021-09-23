# Fedora Guide

### 5 Things to do after installing Fedora 34
https://www.youtube.com/watch?v=-NwWE9YFFIg

---

### Gnome Extensions
https://extensions.gnome.org/

---

### Unity 
Download unity hub from https://unity3d.com/get-unity/download

Open terminal and change permissions
```
chmod a+rwx UnityHub.AppImage
```
Double click to open UnityHub

To solve "not enough space issue", launch Unity Hub using this below command.
```
TEMP=~/tmp ./UnityHub.AppImage
```

Note: Change the Unity installation path from Unity Hub settings. By default Unity is installed in Root Folder.

---

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
sudo dnf install anydesk
```
3) Solve connection issue
```
sudo yum install lightdm lightdm-gtk
sudo systemctl disable gdm.service
sudo systemctl enable lightdm.service
```
4) Reboot.
```
reboot
```
---

### Gnome Tweaks
Install gnome for extra settings & customization.
```
sudo install gnome-tweaks
```
---
### Notice: There are some bugs in RabbitSVN it's recommended to use the svn from terminal.  
### Rabbit SVN for nautilus (Files) GNOME
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

### SVN Commands
```
svn status
svn commit -m "COMMIT MESSAGE"
```
 #### SVN ignore list like gitignore.txt
1) Create a "svnignore.txt"
```
.idea
*.csproj
*.sln*
Builds
Library
Logs
obj
UserSettings
```
2) Execute this command to add files to ignore list.
```
svn propset svn:ignore -F svnignore.txt .
```

Reference: https://www.math-linux.com/linux/tip-of-the-day/article/svn-how-to-ignore-file-or-directory-in-subversion
