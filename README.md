# glpi
GLPI

## Installation des machines

```bash
git clone https://gitea.lyc-lecastel.fr/gsb2025/gsb2025.git
```

```bash
mkvm -r -s s-adm
```

```
sed -i 's/bookworm/s-adm/g' /etc/host{s,name} ; reboot
```

ou

```
git clone https://gitea.lyc-lecastel.fr/gsb2025/gsb2025.git
export HOST=s-adm 
curl 192.168.99.99/gsbstore/inst1|bash
reboot # on redemarre
```

Puis 

```
mkdir -p tools/ansible ; cd tools/ansible git clone https://gitea.lyc-lecastel.fr/gsb2025/gsb2025.git cd gsb2025/pre bash inst-depl cd /root/tools/ansible/gsb2025/pre DEPL=192.168.99.99 bash gsbboot cd ../.. ; bash pull-config
```
