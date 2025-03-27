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
    wlp0s20f3:  # Replace with your actual Wi-Fi interface name (use `ip a` to check)  
      dhcp4: true  
      dhcp6: false  bridges:  
    br0:  
      interfaces: [wlp0s20f3]  
      dhcp4: true  
      dhcp6: false  
      parameters:  
        stp: false  
        forward-delay: 0  
      mtu: 1500
```

```bash
sudo netplan apply
```


### Debug bridge
```bash
sudo ip link add name br0 type bridge
sudo ip link set br0 up
sudo systemctl restart libvirtd
```

change tty to gui
```bash
sudo chvt x  # x: [1-7]
```
