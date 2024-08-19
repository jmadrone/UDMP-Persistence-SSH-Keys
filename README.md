# UDMP Persistence SSH Keys

## Persistence on Reboot

This script need to run every time the system is rebooted since the `/root/.ssh/authorized_keys` overwrites every boot.  
This can be accomplished with a boot script. Flow this guide: [UDM / UDMPro Boot Script](https://github.com/boostchicken-dev/udm-utilities/tree/master/on-boot-script)

## Compatibility

  * Tested on UDM PRO
  * UDM Pro doesn't support __ed25519__ SSH Keys

## Installation

The script was tested on UDM PRO

```bash
curl https://raw.githubusercontent.com/jmadrone/UDMP-Persistence-SSH-Keys/main/install.sh | bash 
```

Add you public RSA keys to:

```bash
/data/ssh/authorized_keys
```

## Uninstall

Delete the 99-ssh-keys.sh file

```bash
rm -rf /data/on_boot.d/99-ssh-keys.sh
```

Delete your authorized_keys file

```bash
rm -rf /data/ssh/authorized_keys
```

## Usage

At boot the script with read the `/data/ssh/authorized_keys` file and add the content to UDM's `/root/.ssh/authorized_keys`

Manual run:

```bash
/data/on_boot.d/99-ssh-keys.sh
```
