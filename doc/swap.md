## swap
add swap for VPS

```bash
# change to home directory
cd ~

# change to last position
cd -

# of -> output file name, output swap file name is .swap
dd if=/dev/zero of=.swap bs=1024 count=1048576

# make swap file
sudo mkswap .swap

# swap on
sudo swapon .swap

# take effect immediately, reboot will disappear
free -m
```