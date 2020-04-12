Create swap file
================
Recommended size for swap file for Splynx 3.0 version - 4GB. If your server has RAM more than 4GB, swap file can be decreased.

Copy and paste in console of your server this command:

```bash
if [[ ! -f /swapfile ]]; then
    echo "Building swapfile..."
    dd if=/dev/zero of=/swapfile bs=64M count=64
    mkswap /swapfile
    chmod 0600 /swapfile
    swapon /swapfile

    # Mount on reboot
    if [[ -z "$(cat /etc/fstab | grep swapfile)" ]]; then
        echo "/swapfile none swap sw 0 0" | tee -a /etc/fstab > /dev/null 2>&1
    fi
fi
```

Using this command swap file with size 4GB will be created.
If you need more or less change `count=64` value:

* `count=16` - for 1 GB,
* `count=32` - for 2 GB.
