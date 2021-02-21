## DVWA Auto Blind SQL Injection

### Información del proyecto
Autor: Miguel de la Cal Bravo

Asignatura: Auditoría Web - Módulo 3: Vulnerabilidades en la parte servidor

Universidad de Castilla-La Mancha (UCLM) - Máster en Ciberseguridad y Seguridad de la Información

### 0. Paquetes necesarios y entorno de pruebas
Primero instalamos los paquetes necesarios con *pip3* de forma automatizada mediante el fichero *requirements.txt*:
```
$ pip3 install -r requirements.txt
```

Este script ha sido diseñado para ser ejecutado contra la aplicación **DVWA** (nivel de seguridad *low*) para ataques de **SQL Injection** y **Blind SQL Injection**.

*NOTA: Este script ha sido ejecutado en una máquina Debian 10 con Python 3.7.3*

### 1. Ejecución por línea de comandos
Para ejecutar el script, introduciremos el siguiente comando por la línea de comandos:
```
$ python3 dvwa_blind_sql_injection.py <URL> <PARAMETER> <EXPECTED_TRUE_OUTPUT> <PHPSESSID>
```
1. **URL**: la dirección url base sin el parámetro GET.
2. **PARAMETER**: el parámetro que pasaremos por GET en las consultas para realizar las pruebas de SQL Injection.
3. **EXPECTED_TRUE_OUTPUT**: la salida esperada al realizar una consulta verdadera.
4. **PHPSESSID**: al hacer uso de DVWA es necesario añadir este valor en las cookies, ya que se requiere una cookie de sesión.


Un ejemplo del comando a ejecutar sería el siguiente:
```
$ python3 dvwa_blind_sql_injection.py http://<IP_ADDRESS>/dvwa/vulnerabilities/sqli_blind/ id "First name: admin" d04d0074f7d56c20bf3c4c99269b5061
```

*¡IMPORTANTE!: Es conveniente añadir las comillas dobles en el parámetro EXPECTED_TRUE_OUTPUT para evitar problemas con la cadena de texto a comprobar.* 

### 2. Menú del script
Una vez ejecutado el script, se realizarán unas comprobaciones iniciales para comprobar si la URL es vulnerable introduciendo comillas simples ('), comillas dobles (") o ningún carácter.

Tenemos las siguientes opciones dentro del menú:
- **[1] Calcular el nº total de bases de datos**
- **[2] Calcular el nº de caracteres de cada una de las bases de datos**
- **[3] Identificar carácter a carácter el nombre de cada una de las bases de datos**
- [4] Lanzar petición personalizada (experimental)
- [5] Salir del programa