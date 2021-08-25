#Fedora Guide

###Rabbit SVN for nautilus (Files) GNOME
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