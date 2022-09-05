# Images that won't update

When loading older images and attempting to update them via apt / apt-update, they may fail to pull any and all information due to SSL / certificate issues.

### Option 1: disable peer verification
Running `apt update -o Acquire::https::Verify-Peer=false` may "just work". 
This effectively disables all the good stuff associated with security / https / ssl / life.

### Option 1: update certificates 
Another option which may or may not work depending on how outdated the certificates are:
1. Edit `/etc/ca-certificates.conf`
1. Add a bang (`!`) as a prefix / at the start of the line containing `mozilla/DST_Root_CA_X3.crt`
1. Save / Exit
1. Run `update-ca-certificates -f` with `-f-` meaning `Fresh updates. Remove symlinks in /etc/ssl/certs directory.`
1. Double-check to make sure the `/etc/ca-certificates.conf` file was updated and that your bang (`!`) was removed (hint: remove it if it's still there)
