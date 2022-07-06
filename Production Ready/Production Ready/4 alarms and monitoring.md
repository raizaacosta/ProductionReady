## Español

## DATA
 
 - PLATAFORMA**: Indica en qué plataforma de monitorización o alerta se encuentra la alarma.

 - **DESCRIPCIÓN**: Cuál es el objetivo de la alarma o de la monitorización.

 - **ELEMENTO A ALERTAR O MONITORIZAR**: El nombre del elemento y su tipo (ec2, RDS, etc)

 - **PÉRDIDA DE SERVICIO**: Sí o No

 - **PRIORIDAD ALTA**: Alta / Media / Baja en función de la relevancia del evento.

 - **RANGO DE ATENCIÓN**: Indicar el periodo de tiempo en el que se atiende el alertado (24x7, 8x5, ...)

 - **RANGO DE ATENCION**: Indicar el periodo de tiempo en el que se atiende el alertado (24x7, 8x5, ...)
 
## MECANISMOS DE COMUNICACIÓN
Existen métodos de comunicación automáticos para el envío de alertas.
 
 - **SNS**: Indicar el nombre del elemento sns. Ej. [Eyp-sns-[entorno] -alarmas-equipo]
 - **Correo de aplicaciones**: Gestión propia del servicio de monitorización alertado.
 - **Otros**: Cualquier otro elemento que informe de las alarmas.
 
## ACCIONES RECOMENDADAS
Acciones a seguir cuando se reproduce el alertado.

 - *Enlace a procedimiento o documentación*.
 - *Contacto de escalada (teléfono, correo, etc)*

## CONTACTOS

Contactos que reciben la alerta indicada.
 
 - *Contacto1 @ email*
 - *Contacto2 @ email*
 - *Contacto3 @ email*

## DOCUMENTACIÓN ADICIONAL
Indique si existe un enlace o documento que proporcione más información al alertado.


## INTRODUCCION

En este apartado aportaremos información a modo de guía de los servicios o elementos de los que podemos hacer uso para unas buenas practicas en el alarmado y monitorización de la infraestructura de nuestro proyecto.

Por ello indicaremos una plantilla tipo para que sea rellenada y se indiquen todos los datos del alarmado o monitorización que tiene cualquier elemento del proyecto.

A su vez tambien mostraremos los distinto servicios que se pueden utilizar para así realizar buenas practicas en este ambito de la infraestructura.

### PLANTILLA

Esta plantilla se encuentra aquí.

En ella se deben indicar diferentes aspectos como estos:

* Elemento o servicio utilizado (Cloudwatch, Datadog, CloudHealth, ...)
* Elemento alertado o monitorizado
* Nivel de prioridad o riesgo
* Acciones automaticas o manuales del alertado.
* A quien se avisa
* Cualquier documentación adicional

### SERVICIOS

Explicaremos los servicios de monitorizacion y alarmas que se utilizan en la compania.

#### CLOUDWATCH

Amazon CloudWatch es un componente de Amazon Web Services (AWS) que brinda monitorización en tiempo real de los recursos y aplicaciones de los usuarios, que se ejecutan en la infraestructura de AWS.

CloudWatch puede recolectar métricas, crear y administrar alarmas, así como reaccionar automáticamente a los cambios en tus recursos de AWS.

	https://docs.aws.amazon.com/es_es/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html
    

##### Posibles Monitores

**ALB/NLB**
 
* **_Errores 5XX/4XX_**: Estas métricas nos ayudarán a identificar problemas en la aplicación/servicio o en el cliente a través de las llamadas que se realicen. (Solo ALB)
* **_Latencia_**: Nos permitirá detectar un crecimiento anómalo en la latencia de respuesta del servicio e investigar la causa. (Solo ALB)
* **_Llamadas_**: Número total de llamadas al servicio para detectar crecimientos no previstos, ataques o cambios no esperados en la utilización del servicio. (Solo ALB)
* **_Healthy Hosts_**: Instancias/servicios activos en el balanceador.
* **_Unhealthy Hosts_**: Instancias/servicios caídos en el balanceador que nos indicarán el inicio de un problema.

**EC2**

* **_Status_**: Se monitorizará las instancias para saber el estado en el que se encuentra, pudiendo ser apagada, encendida, con problemas, etc...
* **_Autoescalado_**: Monitorizaremos los autoescalados para detectar cambios anómalos en el uso de las instancias o posibles problemas en el servicio que provoque apagados contínuos de instancias.
* **_CPU_**: El incremento de CPU nos indicará si hay problemas con la instancia.

**EFS**

* **_Conexiones de cliente_**: Conoceremos el número de cliente conectados al EFS.
* **_Límite I/O_**: Monitorizaremos cuánto de cerca estamos de llegar al límite de performance en I/O.

**LAMBDA**

* **_Consumo memoria_**: Nos indicará si las ejecuciones de una lambda necesitan más memoria.
* **_Tiempo de ejecución_**: Saltará una alarma si se acerca osobrepasa de los 15 minutos.
* **_Incremento en el tiempo de ejecución_**: Detectar si el tiempode ejecución de una lamba se ha incrementado a lo largo de X días (determinar).
* **_Error/Fallo en la ejecución_**: Nos indicará que una lambda hafallado y no ha podido ejecutarse o terminar.

**RDS**

* **_Ram/CPU_**: El incremento de CPU o RAM nos indicará si hay problemas con el servicio.
* **_Conexiones_**: A través de las conexiones realizadas a la BBDD podremos detectar fallos o un aumento no esperado en dichas conexiones.
* **_Espacio en disco_**: Monitorizaremos el espacio en disco del RDS.

**S3**

* **_Errores 5XX/4XX_**: Estas métricas nos ayudarán a identificar problemas en la aplicación/servicio o en el cliente a través de las llamadas que se realicen.
* **_Tamaño S3_**: Detectar crecimientos no previstos en un bucket.
* **_Latencia_**: Detectar un crecimiento anómalo en la latencia derespuesta del bucket.

#### DATADOG

Datadog es un servicio de monitorización para aplicaciones en la nube, que proporciona monitorización de servidores, bases de datos, herramientas y servicios, a través de una plataforma de análisis de datos basada en "Software como Servicio".

	https://www.datadoghq.com/product/
    
En este enlace se encuentra toda la informacion relativa a DataDog en la compañia.

#### CLOUDHEALTH

La plataforma de CloudHealth recopila y analiza datos de servicios de computación en la nube y otros entornos de TI para que los clientes puedan informar sobre los costos, informar sus modelos de negocio y proyectar tendencias futuras.

Mas información sobre este producto en este enlace:

	ENLACE

    ## INTRODUCTION

## English

## DATA
 
 - **PLATFORM**: Indicate on which monitoring or alerted platform the alarm is.

 - **DESCRIPTION**: What is the purpose of the alarm or monitoring

 - **ELEMENT TO ALERT OR MONITOR**: The name of the element and its type (ec2, RDS, etc)

 - **LOSS OF SERVICE**: Yes or No

 - **HIGH PRIORITY**: High / Medium / Low depending on the relevance of the event.

 - **ATTENTION RANGE**: Indicate the period of time in which the alerted is attended (24x7, 8x5, ...)

 - **RANGO ATENCION**: Indicar el periodo de tiempo en el que se atiende el alertado (24x7, 8x5, ...)
 
## COMMUNICATION MECHANISMS
There are automatic communication methods for sending alerts.
 
 - **SNS**: Indicate the name of the sns element. Ex. [Eyp-sns- [enviroment] -alarms-team]
 - **Application Mailing**: Own management of the alerted monitoring service.
 - **Others**: Any other element that reports alarmed.
 
## RECOMMENDED ACTIONS
Actions to follow when the alerted is reproduced.

 - *Link to procedure or documentation*
 - *Escalation contact (phone, mail, etc)*

## CONTACTS

Contacts that receive the indicated alerted.
 
 - *Contact1 @ email*
 - *Contact2 @ email*
 - *Contact3 @ email*

## ADDIOTINAL DOCUMENTATION
Indicate if there is a link or document that provides more information to the alerted.

In this section we will provide information as a guide to the services or elements that we can use for good practices in alarming and monitoring the infrastructure of our project.

For this reason, we will indicate a standard template to be filled in and all the alarm or monitoring data that any element of the project has is indicated.

At the same time, we will also show the different services that can be used in order to carry out good practices in this area of infrastructure.

### TEMPLATE

This template is located here.

In it, different aspects such as these should be indicated:

* Element or service used (Cloudwatch, Datadog, CloudHealth, ...)
* Element alerted or monitored
* Level of priority or risk
* Automatic or manual actions of the alerted.
* Who is notified
* Any additional documentation

### SERVICES

We will explain the monitoring and alarm services used in the company.

#### CLOUDWATCH

Amazon CloudWatch is a component of Amazon Web Services (AWS) that provides real-time monitoring of users' resources and applications, running on the AWS infrastructure.

CloudWatch can collect metrics, create and manage alarms, and automatically react to changes in your AWS resources.

	https://docs.aws.amazon.com/es_es/AmazonCloudWatch/latest/monitoring/WhatIsCloudWatch.html
    

##### Possible Monitors

**ALB / NLB**
 
* **_5XX / 4XX errors_**: These metrics will help us identify problems in the application / service or in the client through the calls that are made. (ALB only)
* **_Latency_**: It will allow us to detect an abnormal growth in the service response latency and investigate the cause. (ALB only)
* **_Calls_**: Total number of calls to the service to detect unforeseen growth, attacks or unexpected changes in the use of the service. (ALB only)
* **_Healthy Hosts_**: Instances / services active in the balancer.
* **_Unhealthy Hosts_**: Instances / services down in the balancer that will indicate the beginning of a problem.

**EC2**

* **_Status_**: Instances will be monitored to know the status they are in, being able to be turned off, on, with problems, etc ...
* **_Autoscaling_**: We will monitor autoscaling to detect anomalous changes in the use of instances or possible problems in the service that cause continuous shutdowns of instances.
* **_CPU_**: The increase in CPU will tell us if there are problems with the instance.

**EFS**

* **_Client connections_**: We will know the number of clients connected to the EFS.
* **_I / O Limit_**: We will monitor how close we are to reaching the I / O performance limit.

**LAMBDA**

* **_Memory consumption_**: It will tell us if the executions of a lambda need more memory.
* **_ Execution time_**: An alarm will be triggered if it approaches or exceeds 15 minutes.
* **_Increase in execution time_**: Detect if the execution time of a lamba has increased over X days (determine).
* **_Error / Failure in execution_**: It will indicate that a lambda has failed and could not be executed or terminated.

**RDS**

* **_Ram / CPU_**: The increase in CPU or RAM will indicate if there are problems with the service.
* **_Connections_**: Through the connections made to the database, we can detect failures or an unexpected increase in said connections.
* **_Disk space_**: We will monitor the RDS disk space.

**S3**

* **_5XX / 4XX errors_**: These metrics will help us identify problems in the application / service or in the client through the calls that are made.
* **_S3 size_**: Detect unforeseen growth in a bucket.
* **_Latency_**: Detect abnormal growth in bucket response latency.

#### DATADOG

Datadog is a monitoring service for cloud applications, which provides monitoring of servers, databases, tools and services, through a data analysis platform based on "Software as a Service".

	https://www.datadoghq.com/product/



#### CLOUDHEALTH

The CloudHealth platform collects and analyzes data from cloud computing services and other IT environments so that clients can report on costs, inform their business models, and project future trends.