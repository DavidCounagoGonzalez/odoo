# Ejercicio Odoo

Creamos el docker-compose añadiendole los datos necesarios y el puerto por defecto de postgres 5432.
Tras tener completo el docker-compose lo lanzamos con docker-compose up .
Esto puede dar error en caso de tener postgres instalado, ya que puede estar ocupando el puerto 5432,
  para buscar que proceso está ocupando este puerto disponemos de comandos que nos listan los procesos activos:
  ps -> para listar los procesos activos
  con -aux -> lista todos los procesos del dispositivo

  netstat -> lista los procesos activos y conectados al pc
  -pt -> tdp
  -put -> tdp/udp
  -putan -> servidores y establecidos
  | grep * * -> para filtrar 
  
  Tras haber encontrado el proceso usando por ejemplo nestat -putan | grep 5432
  utilizaremos el comando service para parar el proceso que deseemos 
  Para ello podemos comenzar buscando el nombre del proceso para asegurarnos usando
  sudo service ( y en este caso) pos (ya que buscamos postgresql) tras esto nos mostrará los procesos que comiencen por lo indicado
  Una vez verificado usaremos *sudo service postgresql stop* 
  para pararlo y liberar el puerto que este usando en este caso el 5432
  por lo cual ahora podremos volver a lanzar nuestro docker-compose y tenerlo en dicho puerto.
  
  En caso de querer lanzar de nuevo postgres con start , este se inciará, sin embargo no se conectará al puerto.
 
