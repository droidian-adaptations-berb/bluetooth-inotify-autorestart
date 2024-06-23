# Autorestart bluetooth service 
May happen that the bluetooth service hangs if the controller is managed from the Phosh GUI until the bluetooth service is restarted.
For this cases, this fix monitors the bluetooth service and auto-restart it when some event on rfkill devices is detected, and the bluetooth service is not responding. 

Also the file /var/lib/bluetooth/inotify-macs.allow can be used to add device MACs (one per line), and the autorestart will be done on every rfkill event detection if some device registeered MAC is on the .allow file

The service is enabled by default, if problems are detected, stop and disable the droidian-xiaomi-vayu-inotify-bluetooth.service

A log registry is writed every time the bluetooth service is autorestarted (/var/log/bluetooth-inotify.log)

