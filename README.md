# spring_cloud_data_flow



### Info útil
    http://www.baeldung.com/spring-cloud-data-flow-stream-processing
    https://github.com/eugenp/tutorials/tree/master/spring-cloud-data-flow
    
    https://dzone.com/articles/data-mart-with-spring-cloud-data-flow
    https://github.com/wkennedy/spring-data-flow-example
    
    
Pasos
1. Cargar entorno
    docker-compose up -d
2. Lanzar server
    http://localhost:9393/dashboard/index.html
3. Lanzar shell

4. En el shell, ejecutar:
    
app register --name time-source --type source  --uri maven://com.poc:time-source:jar:1.0-SNAPSHOT
 
app register --name time-proccesor --type processor   --uri maven://com.poc:time-proccesor:jar:1.0-SNAPSHOT
 
app register --name log-sink --type sink   --uri maven://com.poc:log-sink:jar:1.0-SNAPSHOT

stream create --name time-to-log --definition 'time-source | time-proccesor | log-sink'

stream deploy --name time-to-log