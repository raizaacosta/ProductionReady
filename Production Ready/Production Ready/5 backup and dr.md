## Español

## Análisis inicial

Para definir los procedimientos de copia de seguridad, es necesario identificar el tipo de recurso/datos que le interesa respaldar y la criticidad de los procesos, de modo que se puedan abordar los tres principales factores decisivos:
1. **¿Se considera que se puede hacer una copia de seguridad?**
2. **¿Con qué frecuencia se actualiza la copia de seguridad?**
3. **¿Qué tipo de copia de seguridad se recomienda?**

### ¿Qué se puede respaldar?

- Código.
	- Aplicación.
    - Infraestructura.
    - Automatizaciones generales.
    - Cualquier pieza funcional de código.
- Datos
	- Datos históricos: datos útiles para la prueba de herramientas o para el archivo.
	- Datos actuales.
- **Documentación**
	- Descripción del proceso de despliegue en AWS.
    - Información útil de arquitectura/componentes.

### Periodicidad de las copias de seguridad y período de retención

- **Última versión del código.**
	- Ramas Git: Pro/Dev/QA.
- **Datos.**
	- Copia única de los datos históricos.
    - Muestra actualizada de los datos de cada mes/año.
- **Single copy for procedural documentation.**
	- Technical processes.
    - Operational.

### Tipo de soporte de la copia de seguridad

- Método de copia de seguridad.
	- BDs externas.
    	- La copia de seguridad debe utilizar un servicio diferente para garantizar la disponibilidad.
    - RDS.
    	- Utilice el período de retención de la copia de seguridad.
        - En caso de que se necesite un procedimiento de copia de seguridad periódica personalizado, se puede utilizar una función Lambda.
    - DynamoDB, seleccione el método en función de las necesidades particulares.
    	- Configurar copias de seguridad continuas con recuperación puntual.
        - Configurar copias de seguridad bajo demanda para crear copias de seguridad completas de las tablas.
        - En caso de que se necesite un procedimiento de copia de seguridad periódica personalizado, se puede utilizar una función Lambda.
	- S3.
    	- Definir las políticas del ciclo de vida de S3 para mover los datos entre los tipos de almacenamiento en consecuencia.
    	- Utilizar S3 Glacier para archivar los datos reduciendo el coste de almacenamiento.
        
- **Se requiere que los equipos de SRE y Producto, PO y Desarrollo tengan acceso a las BackUps configuradas.**

#### <b><span style="color:red"> Example :</span></b>
 
 | Nombre de la copia de seguridad | Contenido | Periodicidad | Entorno | Tipo de soporte de la copia de seguridad | Ubicación 
 |--|--|--|--|--|--|
 |Nombre de la copia de seguridad de ejemplo | Datos históricos | Semanal | Pro/Dev/QA | S3 |https://s3.us-west-2.amazonaws.com/mybucket/example-backup-name.
 
 ## Recuperación de desastres
 
 Los procedimientos de copia de seguridad deben ser capaces de proporcionar un medio para la recuperación de desastres en caso de que haya un fallo en la plataforma.
 
 Para diseñar un proceso de DR, hay que tener en cuenta lo siguiente: 
  #### Objetivo de tiempo de recuperación (RTO)
 > Duración del tiempo y del nivel de servicio en el que debe restablecerse un proceso de negocio tras una interrupción para evitar pérdidas inaceptables.
 #### Objetivo de punto de recuperación (RPO)
 > Punto de tiempo en el que deben recuperarse los datos o se producen pérdidas aceptables. Depende del método de copia de seguridad.
 - **Plataforma secundaria/sitio**: haber abordado cómo hacer que una plataforma secundaria esté disponible es clave para hacer frente a una situación inesperada.
 
 La estrategia de contingencia está sujeta a las necesidades de la plataforma/proyecto y suele implicar una solución particular para cada caso, pero estos términos fundamentales deben estar definidos de antemano.




## English

## Initial analysis

To define the backup procedures, it is necessary to identify the type of resource/data you're interested in backing up and the criticalness of the processes, so that the main three deciding factors can be addressed:
1. **Is it considered capable of being backed up?**
2. **How often is the backup updated?**
3. **What type of backup is recommended?**

### What can be backed up?

- **Code**
	- Application.
    - Infrastructure.
    - General automations.
    - Any functional piece of code.
- **Data**
	- Historical data: useful data for tool testing or archival.
	- Current data.
- **How To - Documentation**
	- Description of the deployment process in AWS.
    - Useful architectural/component information.

### Backup Periodicity & Retention Period

- **Latest version of the code.**
	- Git branches: Pro/Dev/QA.
- **Data.**
	- Single copy of historical data.
    - Updated sample of data for each month/year.
- **Single copy for procedural documentation.**
	- Technical processes.
    - Operational.

### Type of backup support

- **Backup method.**
	- External DBs.
    	- The backup must use a different service to ensure availability.
    - RDS.
    	- Use the Backup Retention Period.
        - In case there's a need for a customized periodical backup procedure, a Lambda function can be used.
    - DynamoDB, select method depending on the particular needs.
    	- Configure continuous backups with point-in-time recovery.
        - Configure on-demand backups to create full backups of the tables.
        - In case there's a need for a customized periodical backup procedure, a Lambda function can be used.
	- S3.
    	- Define S3 lifecycle policies to move data between storage types accordingly.
    	- Use S3 Glacier for data archiving while reducing storage cost.
        
- **It is required for the SRE & Product teams, PO and Development to have access to the configured BackUps.**

####  <b><span style="color:red"> Example :</span></b>
 
 | Backup name | Content | Periodicity | Environment | Type of backup support | Location | 
 |--|--|--|--|--|--|
 |example-backup-name | Historical data | Weekly| Pro/Dev/QA | S3 |https://s3.us-west-2.amazonaws.com/mybucket/example-backup-name.
 
 ## Disaster Recovery
 
 Backup procedures must be able to provide a means for Disaster Recovery in case there's a failure in the platform.
 
 To design a DR process, the following should be addressed: 
  #### Recovery Time Objective (RTO)
 > Duration of time and service level within which a business process must be restored after a disruption in order to avoid unacceptable losses.
 #### Recovery Point Objective (RPO)
 > Point in time to which data must be recovered or acceptable loss. It is dependent on the Backup method.
 - **Secondary Platform/Site**: having addressed how to make a secondary platform available is key to tackle an unexpected situation.
 
 The contingency strategy is subject to the needs of the platform/project and usually implies a particular solution for each case scenario, but these fundamental terms must be defined beforehand.
