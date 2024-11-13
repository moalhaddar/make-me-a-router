# Make me a router
A simple net filtet configuration that allows you to turn your linux host into a router, useful for forwarding to VPNs for example, that are not available/connected on other hosts.

# How to use
0. Enable ip forwarding on your host kernel. You'll need to add this to your `/etc/sysctl.conf` file
```
net.ipv4.ip_forward = 1
```

Then run `sysctl -p` for the changes to take effect.


1. Modify the source subnet and interface name in `install_router.nft`. That is, it will route traffic coming from a certain subnet and a certain interface. You can find the interface name using `ip address` command.
2. Install the nf table
```sh
./install_router.nft
```
3. Watch the status of the nf table
```sh
./watch_router.sh
```
4. If you're done then remove the nf table
```sh
./remove_router.nft
```

# Author
Mohammed Alhaddar