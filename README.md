# Libreborme-ansible

Script para el despliegue automático de Libreborme.

Documentación aquí: http://libreborme.readthedocs.org/es/latest/install_production_automated.

El playbook está pensado para ser ejecutado en Ubuntu 15.04 x64. Versiones posteriores quizás funcionen, versión anteriores fallarán seguro al no existir ciertos paquetes.

# Cómo ejecutar

En Ubuntu 15.04 el intérprete de Python por defecto es de Python3 mientras que por otra parte, Ansible todavía necesita Python2. En la máquina remota, instala Python 2:

    sudo apt-get install python-minimal

Instala la versión más reciente de ansible desde el repositorio PPA:

    sudo apt-add-repository ppa:ansible/ansible
    sudo apt-get update
    sudo apt-get install ansible
    
Editar la IP del servidor remoto en el archivo *hosts*. Comprobar que se puede conectar:

    ansible webservers -m ping

Resultado:

    46.101.190.150 | success >> {
        "changed": false,
        "ping": "pong"
    }

Ejecuta el playbook:

    ansible-playbook install.yml

En aproximadamente 5 minutos está todo funcionando.

TODO: Importar backup

Actualizar a la última versión de libreborme:

    ansible-playbook update.yml
