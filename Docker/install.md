- na správu repozitarov
````
dnf -y install dnf-plugins-core
````
- pridanie docker repa
````
dnf config-manager --add-repo https://download.docker.com/linux/fedora/docker-ce.repo
````
- inštalácia dockeru 
````
dnf -y install dnf-plugins-core
````
- problem s grupou
````
sudo grubby --update-kernel=ALL --args="systemd.unified_cgroup_hierarchy=0"
````
 
 - pridanie do grupy 
 ````
sudo usermod -aG docker patrik.sebesta
````

