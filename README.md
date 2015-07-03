# Libreborme-ansible

Script para el despliegue automático de Libreborme.

Documentación aquí: http://libreborme.readthedocs.org/es/latest/TODO

# Cómo ejecutar

    sudo apt-add-repository ppa:ansible/ansible
    sudo apt-get update
    sudo apt-get install ansible
    
Editar la IP del servidor remoto en el archivo *hosts*. Comprobar que se puede conectar:

    ansible libreborme -m ping

Resultado:

    46.101.190.150 | success >> {
        "changed": false,
        "ping": "pong"
    }

Instalar:

    ansible-playbook install_root.yml
