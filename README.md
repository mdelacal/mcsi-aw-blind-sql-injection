### Información del proyecto
Autor: Miguel de la Cal Bravo

Asignatura: Auditoría Web - Módulo 3: Vulnerabilidades en la parte servidor

Universidad de Castilla-La Mancha (UCLM) - Máster en Ciberseguridad y Seguridad de la Información

### 0. Paquetes necesarios y entorno de pruebas
Primero instalamos los paquetes necesarios con *pip3*:
```
$ pip3 install requests
$ pip3 install PrettyTable
$ pip3 install bs4
```

Podemos instalar estos paquetes de forma automatizada mediante el fichero *requirements.txt*:
```
$ pip3 install -r requirements.txt
```

Este script ha sido diseñado para ser ejecutado contra la aplicación **DVWA** (nivel de seguridad *low*) para ataques de **SQL Injection** y **Blind SQL Injection**.

*NOTA: Este script ha sido ejecutado en una máquina Debian 10 con Python 3.7.3*

### 1. Ejecución por línea de comandos
Para ejecutar el script, introduciremos el siguiente comando por la línea de comandos:
```
$ python3 dvwa_blind_sql_injection.py <URL> <PARAMETER>
```

### 2. Menú del script
Una vez ejecutado el script, se realizarán unas comprobaciones iniciales para comprobar si la URL es vulnerable introduciendo comillas simples ('), comillas dobles (") o ningún carácter.

Tenemos las siguientes opciones dentro del menú:
- **[1] Calcular el nº total de bases de datos**
- **[2] Calcular el nº de caracteres de cada una de las bases de datos**
- **[3] Identificar carácter a carácter el nombre de cada una de las bases de datos**
- [4] Lanzar petición personalizada (en desarrollo)
- [5] Salir del programa