# cowrie!
cowrie es un honeypot SSH de media-alta interacción. nos permite emular un entorno SSH en el cual todas las acciones, descargas, llaves, 
etcétera, son registradas y almacenadas para posterior revisión.

no solo registra, sino que también tiene funcionalidades de envío de información a distintas herramientas, como Elastic, Graphana, Telegram, entre otras.
tiene muchas, muchas funcionalidades. y creo que será entretenido mostrárselas a todos mis lectores.

## instalación

la verdad es que la instalación de cowrie es bastante sencilla. debemos clonar el repositorio, crear un entorno virtual, instalar sus dependencias y ejecutarlo.
es tan sencillo que yo, teniendo pésima memoria, me lo aprendí. es una tarea casi mecánica.

```
apt install python3-virtualenv
git clone https://github.com/cowrie/cowrie
cd cowrie
python3 -m venv cowrie-env
source cowrie-env/bin/activate
python3 -m pip install -r requirements.txt
bin/cowrie start
```

con esto, tendrán un cowrie corriendo en el puerto 2222. *puerto 2222?* si. cowrie no corre en el puerto 22. se debe hacer un poco de mágia con dnat e iptables para
que el tráfico del puerto 22 sea redirigido al puerto 2222. esto se debe a que, si quisiesemos ejecutar cowrie en el puerto 22, debe tener la capacidad `CAP_NET_BIND_SERVICE`,
la cual no es accesible a un usuario regular.

veremos todo esto y más en las siguientes páginas.
