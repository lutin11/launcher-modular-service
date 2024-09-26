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

If you want to disable autostart
```
systemctl --user --now launcher-modular
```

If you want to automatically re-start when it is close (maybe by accident) you have to edit the file
and change `Restart=on-failure` to `Restart=always` 
```
sed -i 's/Restart=on-failure/Restart=always/g' ~/.config/systemd/user/launcher-modular.service
```
To rollback as before:
```
sed -i 's/Restart=always/Restart=on-failure/g' ~/.config/systemd/user/launcher-modular.service
```
