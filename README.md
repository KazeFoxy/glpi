# GLPI Install and Bastion Guacamole Install
Tuto installation GLPI GSB
> Pour Bastion Guacamole - Skip r-ext !

# Installation des machines

```bash
git clone https://gitea.lyc-lecastel.fr/gsb2025/gsb2025.git
cd gsb2025/scripts/
```

## Pour s-adm
```bash
mkvm -r -s s-adm
```

```bash
sed -i 's/bookworm/s-adm/g' /etc/host{s,name} ; reboot
```

**ou**

```bash
git clone https://gitea.lyc-lecastel.fr/gsb2025/gsb2025.git
export HOST=s-adm 
curl 192.168.99.99/gsbstore/inst1|bash
reboot # on redemarre
```

**Puis**

```
mkdir -p tools/ansible ; cd tools/ansible git clone https://gitea.lyc-lecastel.fr/gsb2025/gsb2025.git cd gsb2025/pre bash inst-depl cd /root/tools/ansible/gsb2025/pre DEPL=192.168.99.99 bash gsbboot cd ../.. ; bash pull-config
```

## Pour s-infra

```bash
mkvm -r -s s-infra
```

```bash
sed -i 's/bookworm/s-infra/g' /etc/host{s,name} ; reboot
```

**ou**

```bash
git clone https://gitea.lyc-lecastel.fr/gsb2025/gsb2025.git
export HOST=s-infra   
curl 192.168.99.99/gsbstore/inst1|bash
reboot # on redemarre
```

**Puis**

```bash
mkdir -p tools/ansible ; cd tools/ansible
git clone https://gitea.lyc-lecastel.fr/gsb2025/gsb2025.git
cd gsb2025
vim s-infra.yml  # Enlever les rôles tel que Zabbix, elk et awx
ansible-playbook -i localhost, -c local s-infra.yml
```
> Important : Bien enlever les rôles !

## Pour r-ext

```bash
mkvm -r -s r-ext
```

```bash
sed -i 's/bookworm/r-ext/g' /etc/host{s,name} ; reboot
```

**ou**

```bash
git clone https://gitea.lyc-lecastel.fr/gsb2025/gsb2025.git
export HOST=r-ext  
curl 192.168.99.99/gsbstore/inst1|bash
reboot # on redemarre
```

**Puis**

```bash
mkdir -p tools/ansible ; cd tools/ansible
git clone https://gitea.lyc-lecastel.fr/gsb2025/gsb2025.git
cd gsb2025
vim r-ext.yml  # Enlever les rôles tel que Zabbix et syslog-cli
ansible-playbook -i localhost, -c local r-ext.yml
```
> Important : Bien enlever les rôles !
> 
> Important : Faire deux fois le playbook

## Pour r-int

```bash
mkvm -r -s r-int
```

```bash
sed -i 's/bookworm/r-int/g' /etc/host{s,name} ; reboot
```

**ou**

```bash
git clone https://gitea.lyc-lecastel.fr/gsb2025/gsb2025.git
export HOST=r-int 
curl 192.168.99.99/gsbstore/inst1|bash
reboot # on redemarre
```

**Puis**

```bash
mkdir -p tools/ansible ; cd tools/ansible
git clone https://gitea.lyc-lecastel.fr/gsb2025/gsb2025.git
cd gsb2025
vim r-int.yml  # Enlever les rôles tel que Zabbix et syslog-cli
ansible-playbook -i localhost, -c local r-int.yml
```
> Important : Bien enlever les rôles !
> 
> Important : Faire deux fois le playbook

## Pour s-itil

```bash
mkvm -r -s s-itil
```

```bash
sed -i 's/bookworm/s-itil/g' /etc/host{s,name} ; reboot
```

**ou**

```bash
git clone https://gitea.lyc-lecastel.fr/gsb2025/gsb2025.git
export HOST=s-itil 
curl 192.168.99.99/gsbstore/inst1|bash
reboot # on redemarre
```

**Puis**

```bash
mkdir -p tools/ansible ; cd tools/ansible
git clone https://gitea.lyc-lecastel.fr/gsb2025/gsb2025.git
cd gsb2025
vim s-itil.yml  # Enlever les rôles tel que Zabbix et syslog-cli
ansible-playbook -i localhost, -c local s-itil.yml
```
> Important : Bien enlever les rôles !
