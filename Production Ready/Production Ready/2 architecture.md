## ESPAÑOL

## Documentación necesaria

### 1. Diagrama de la infraestructura
Diagrama con la representación a alto nivel de la arquitectura con todos los servicios de AWS y componentes y la relación entre ellos.

Para los diagramas de AWS, hay dos opciones:

- Ir a <https://app.diagrams.net/?splash=0&libs=aws4>
- Ir a "Insert Drawing", cuando se abre app.diagrams.net (antiguo draw.io), y abajo del todo pone en naranja "+ more shapes", y escoger en la sección "Networking" librería AWS19.



### 2. Documentación funcional
Documentación funcional con los flujos de trabajo o de transformación de datos

Ejemplo:  

- **Ejemplo flujo1**  
El flujo comienza con un evento de Amazon Eventbridge que dispara... finalmente los datos son almacenados en... 

### 3. Configuracion Redes

- VPC
- Subnets
- NACL
- Security Groups

### 4. Listado de servicios utilizados, su configuración y sus permisos (de ser necesarios)  

Ejemplo:  

###### **AWS Lambda**
Nombre: **aws-lambda-function1**  
Descripcion: Función que calcula x  
Configuración:

 - RAM Size: 128MB
 - Timeout: 60 segundos
 - VPC y subnets (si hay)
 - Trigger: S3 PutObject /created
 - Permisos:
    - S3 (GetObject)
    - DynamoDB (GetItem)  
 
###### **S3**
Nombre: **bucket-input-data**  
Descripcion: Bucket de entrada de datos  
Configuración:  

 - Lifecycle:

###### **EC2**
Nombre: Instancia1  
...

_ _ _


## ENGLISH


## Required documentation

### 1. Infrastructure diagram

Diagram with the high level representation of the architecture with all AWS services and components of AWS and the and the relationship between them.
For AWS diagrams, there are two options:
- Go to <https://app.diagrams.net/?splash=0&libs=aws4>
- Go to "Insert Drawing", when you go to app.diagrams.net (old draw.io), and in the bottom appears in orange "+ more shapes", then choose in the selection "Networking" library AWS19.


### 2. Functional documentation
Functional documentation with the workflows or data transformation flows

Example:

- **Example workflow1**  
The flow begins with an Amazon Eventbridge event that triggers ... finally the data is stored in ...


### 3. Network Configuration
- VPC
- Subnets
- NACL
- Security Groups

### 4. List of services used, their configuration and permissions (if required)
Example:
###### **AWS Lambda**
Name: **aws-lambda-function1**  
Description: Function that calculates x  
Configuration:  

 - RAM Size: 128MB
 - Timeout: 60 segundos
 - VPC y subnets (si hay)
 - Trigger: S3 PutObject /created
 - Permissions:
    - S3 (GetObject)
    - DynamoDB (GetItem)

###### **S3**
Name: bucket-input-data  
Description: Bucket that stores the input data  
Configuration:  
 - Lifecycle:

###### **EC2**
Name: Instance1
...