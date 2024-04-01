## ansible_role_osticket

Ansible rol para instalar un servidor OsTicket v1.14.6/v1.16.3/v1.18.1 + plugins.

Testeado con Vagrant + QEMU + ubuntu_22.04.

---

### Descripción

La idea del proyecto es automatizar vía ansible la instalación/configuración de un servicio [osticket](https://osticket.com/) para pruebas de laboratorio, el repo cuenta con 5 roles:
1. mariadb
2. osticket_1.14.6
3. osticket_1.16.3
4. osticket_1.18.1
5. plugins

### Dependencias

* [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/installation_distros.html)
* [Vagrant](https://developer.hashicorp.com/vagrant/install) (opcional)

### Uso

* Clonar proyecto + ejecutar playbooks
```
git clone https://github.com/pgraffigna/ansible_role_osticket.git
cd ansible_role_osticket
ansible-playbook main.yml --tags/--skip-tags TAG --> según corresponda
```

### Extras
* Archivo de configuración (Vagrantfile) para desplegar una VM descartable con ubuntu-22.04 con libvirt como hipervisor.
* Archivo con notas para realizar migración entre versiones.
* Archivo ***.editorconfig*** para configurar los parametros en vscode/vscodium.

### Uso Vagrant (opcional)
```
vagrant up --> levanta la vm
vagrant upload FILE --> sube archivos hacia la vm
vagrant ssh --> acceder a la vm
```

### To-Do
* Probar si con un condicional IF se puede llamar a las diferentes versiones.