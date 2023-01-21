# Compartiendo almacenamiento 📁 local en una VM 🖥️ con Vagrant
![Vagrant_Video_02_HD_1080p.jpg](images%2FVagrant_Video_02_HD_1080p.jpg)
En este video vamos a ver como montar almacenamiento o directorios locales del Host en una VM en Vagrant, de esta forma podemos gestionar las configuraciones desplegadas en nuestras VMs sin necesidad de acceder a ellas.

0:00 Entrada
0:11 Intro
0:23 DEMO
7:38 Posible caso de uso
8:29 Destrucción de VM
8:50 Despedida
9:00 Outro

GitHub:
https://github.com/TheAutomationRules/vagrant/blob/main/Video_02/README.md

Twitter: @TheAutomaRules
Instagram: TheAutomationRules

#hashicorp #vagrant #virtualizacion #virtualbox #storage #sharing

## Requisitos:

- Tener instalado el binario de Vagrant https://developer.hashicorp.com/vagrant/downloads
- Tener instalado VirtualBox https://www.virtualbox.org/wiki/Downloads

---

Clonamos el repositorio

````
git clone https://github.com/TheAutomationRules/vagrant.git
````
Entramos al directorio vagrant/Video_02
````
cd vagrant/Video_02
````
Levantamos la maquina virtual
````
vagrant up
````
Entramos al la maquina virtual
````
vagrant ssh
````
Comprobamos el directorio local Video_02 montado en el path /vagrant y veremos en el contenido del directorio con 
el archivo Vagrantfile y el README.md de nuestro repositorio.
````
ll /vagrant

vagrant@vagrant-test:~$ ll /vagrant/
total 20
drwxrwxrwx  1 vagrant vagrant 4096 Jan 19 18:01 ./
drwxr-xr-x 20 root    root    4096 Jan 19 18:16 ../
-rwxrwxrwx  1 vagrant vagrant  271 Jan 19 17:48 README.md*
drwxrwxrwx  1 vagrant vagrant 4096 Jan 19 18:01 .vagrant/
-rwxrwxrwx  1 vagrant vagrant  641 Jan 19 18:01 Vagrantfile*
````
Comprobamos el contenido del directorio .secret montado en el home del usuario vagrant
````
ll .secret/test
````
Editamos el fichero .secret/test/secret.user desde el Host local de la maquina virtual.
````
vim .secret/test/secret.user
````
Y ahora desde la maquina virtual comprobamos el contenido del archivo para ver la modificacion
````
cat .secret/test/secret.user
````
Salimos de la maquina virtual
````
exit
````
Eliminamos la maquina virtual
````
vagrant destroy -f
````
Y eso es todo Automators! disfrutar! 🤖🤘