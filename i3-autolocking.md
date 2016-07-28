Ubuntu without systemctl.

# Inside: /etc/init.d/screenlock.service

[Unit]
Description=Lock X session using slock
Before=sleep.target

[Service]
User=my_user
Environment=DISPLAY=:0
ExecStart=/usr/bin/xautolock -locknow

[Install]
WantedBy=sleep.target

# Then make it autostart:
sudo update-rc.d screenlock.service defaults

# restart...
