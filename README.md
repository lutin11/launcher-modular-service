# How to enable Launcher Modular to start automatically when the device is booted

To enable Launcher Modular to start automatically when the device is started:

Download by right clicking below and selecting "save link as"

[![download](https://github.com/Fuseteam/linus-proof/blob/main/images/download.png)](https://raw.githubusercontent.com/lutin11/launcher-modular-service/refs/heads/main/user/launcher-modular.service)

Save it in your downloads folder and run the following commands:
```
mkdir -p ~/.config/systemd/user
mv ~/Downloads/launcher-modular.service ~/.config/systemd/user/launcher-modular.service
systemctl --user enable --now launcher-modular
```

Or alternatively you can download it directly
```
mkdir -p ~/.config/systemd/user
wget -O ~/.config/systemd/user/launcher-modular.service https://raw.githubusercontent.com/lutin11/launcher-modular-service/refs/heads/main/user/launcher-modular.service
systemctl --user enable --now launcher-modular
```

You can check if launcher-modular session-manager is running properly with
```
systemctl --user status launcher-modular
```
