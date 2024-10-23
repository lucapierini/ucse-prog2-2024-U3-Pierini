# Correcciones - Estado: APROBADO
- La aplicación funciona bien y el docker-compose es correcto
- Como aclaración porque he visto en otros casos que no lo están probando correctamente, cuando se hace "docker-compose up" la aplicación debería hacer el build y el bootstraping de los servicios. 
Una vez se ejecutaron, al acceder a la siguiente url `http://localhost:4001/checker?url=app1&zone=America/New_York` éste servicio "app2" se conecta con la "app1" y retorna el valor. 
Noten que se pasan 2 query parameters, uno es el zone y el otro el nombre del contenedor del servicio 1 para poder generar el request correspondiente al contenedor del servicio1. Hay que resaltar que éste último se utiliza al hacer el GET usando Axios para dirigirse al servicio, pero NO deberían de hardcodearlo como "localhost".

Les dejo otras urls para testear:

	http://localhost:4001/checker
	http://localhost:4001/checker?url=app1&zone=America/Argentina/Buenos_Aires
	http://localhost:4001/checker?url=app1&zone=America/New_York
	http://localhost:4001/checker?url=app1&zone=Europe/London
Más acerca de timezones https://en.wikipedia.org/wiki/List_of_tz_database_time_zones

- Podrían haber utilizado "container_name" como parámetro en el docker-compose.yml (https://community.bigbeartechworld.com/t/customizing-container-names-in-docker-and-docker-compose/320)

