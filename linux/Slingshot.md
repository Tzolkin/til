# Parts of GTK3 apps become transparent
Reported on https://bugs.launchpad.net/slingshot/+bug/1443031

To resolve this issue do the following:

## Overlay Scrollbar
Disable
```
gsettings set com.canonical.desktop.interface scrollbar-mode normal
```

Enable
```
gsettings reset com.canonical.desktop.interface scrollbar-mode
```
