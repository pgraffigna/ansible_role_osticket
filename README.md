## ansible_role_osticket

Ansible rol para instalar un servidor OsTicket v1.17.6/v1.18.2 + plugins.

Testeado con Vagrant + QEMU + ubuntu_24.04.

---

### <u>Descripción</u>
La idea del proyecto es automatizar vía ansible la instalación/configuración de un servicio [osticket](https://osticket.com/) para pruebas de laboratorio, el repo cuenta con 5 roles:
1. mariadb
2. apache
3. osticket_1.17.6
4. osticket_1.18.2
5. plugins

### <u>Dependencias</u>

* [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/installation_distros.html)
* [Vagrant](https://developer.hashicorp.com/vagrant/install) (opcional)

### <u>Uso</u>
```shell
git clone https://github.com/pgraffigna/ansible_role_osticket.git
cd ansible_role_osticket
ansible-playbook main.yml --tags/--skip-tags tag
```

### <u>Extras</u>
* Archivo de configuración (Vagrantfile) para desplegar una VM descartable con ubuntu-22.04 con libvirt como hipervisor.
* Archivo con notas para realizar migración entre versiones.
* Archivo ***.editorconfig*** para configurar los parametros en vscode/vscodium.

### <u>Uso Vagrant (opcional)</u>
```shell
vagrant up
vagrant upload "archivo" # sube archivos hacia la vm
vagrant ssh
```
