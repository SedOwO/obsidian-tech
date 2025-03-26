### 1.Install
```bash
sudo apt install qemu-kvm virt-manager libvirt-daemon-system virtinst libvirt-clients bridge-utils
```

### 2.Enable VM
```bash
sudo systemctl enable --now libvirtd
sudo systemctl start libvirtd
```

### 3.Check status
```bash
sudo systemctl status libvirtd
```

### 4.Add current user to kvm and libvirt group
```bash
sudo usermod -aG kvm $USER
sudo usermod -aG libvirt $USER
groups $USER  # Check if the users are added to the groups
```

### 5.Create a bridge interface
```bash
sudo nano /etc/netplan/01-netcfg.yaml
```

01-netcfg.yaml
```yaml
network:
  version: 2
  renderer: NetworkManager
  ethernets:
    ens33:
      dhcp4: false
      dhcp6: false
  bridges:
    br0:
      interfaces: [ens33]
      dhcp4: false
      addresses: [192.168.2.120/24]

      routes:
        - to: default
          via: 192.168.2.1
          metric: 100
      nameservers:
        addresses: [8.8.8.8]

```

```bash
sudo netplan apply
```


