check_reboot
============
**A Nagios plugin to check if Debian based systems need rebooting.**

Debian and Ubuntu packages can trigger the creation of `/var/run/reboot-required` in their postinst file by executing the helper script `/usr/share/update-notifier/notify-reboot-required`.  Additionally, the file `/var/run/reboot-required.pkgs` lists the packages that requested the reboot.  The script `/usr/lib/update-notifier/update-motd-reboot-required` is responsible for adding the `*** System restart required ***` message to the MOTD.

*Please note that `/var/run/reboot-required` does not get created unless the `update-notifier-common` package is installed.*

This plugin checks for the presence of `/var/run/reboot-required` and returns **`WARNING`** if the file exists (along with a description of the packages that requested the reboot), **`OK`** if it doesn't, or **`UNKNOWN`** if it encounters a problem.
