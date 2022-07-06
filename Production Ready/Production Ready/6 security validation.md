## Español

Los temas y requisitos que hay que comprobar y discutir en la reunión son los siguientes
### Arquitectura

- Diagrama con la siguiente información

	- Servicios públicos (expuestos a Internet - Especificar protocolo de acceso, ejemplo:HTTPS ).
    - Zonas privadas.
    - Servicios de AWS utilizados.
    - Servicios de terceros utilizados.
    - Conexiones con cuentas on-premise u otras.
    - CNAMEs con dominios.
    - Otras incidencias relacionadas con seguridad

</br>

- **Security Groups:**

	- Tener los mínimos privelegios posibles (Ips, referencias a otros sg). 
    - Nunca usar 0.0.0.0.
    - Especificar excepciones para ser revisadas por seguridad.

</br>

- **S3 Buckets:** 

	- No hay buckets públicos. 
    - Especificar excepciones para revisar.

##### Autenticación

- El método para autenticar usuarios está documentado. Si la aplicación está conectada al ADFS, por favor especificarlo.

##### Datos

- Revise la siguiente información para cumplir con los puntos.

	- Todos los datos están encriptados en reposo y en tránsito, con KMS personalizado si los datos son sensibles. 
    - Por favor, documente los datos sensibles y preséntelos a ciberseguridad. Cumplimiento del GDPR.
    - Todos los datos se almacenan en la UE.
    - Todas las contraseñas y secretos se almacenan en servicios como el KMS, el almacén de parámetros o el gestor de secretos y no hay claves o secretos codificados en el repositorio o en la aplicación.
    
##### Aplicación (opcional pero requerida en un futuro).

- Asegúrese de que ha pasado la validación de ciberseguridad de las vulnerabilidades y las versiones de las bibliotecas o cualquier dependencia instalada.

##### Solo acceso IAM   (necesita aprobación del CoE)

- Los roles tienen permisos mínimos y aplican el principio de menor privación.
- Los usuarios con clave de acceso/clave secreta (es decir, el proceso de ingestión) están documentados. Especifíquelo en la revisión.


Si tienes todas estas cosas documentadas y/o toda tu arquitectura utiliza piezas pre-aprobadas por seguridad, puedes saltarte la revisión de ciberseguridad enviando toda la información a [Ciberseguridad](EMAIL</u>)</span>.

## English

This topics and requirements need to be check and discuss in the meeting are:
### Architecture

- **Diagram with the next information:**

	- Public services (exposed to the Internet - Specify protocol access, example:HTTPS ).
    - Private zones.
    - AWS services used.
    - Third party services used.
    - Cconnections with on-premise or other accounts.
    - CNAMEs with  domains.
    - Other issues regarding security.

</br>

- **Security Groups:**

	- Have the least priviledges (Ips, references to other sg). 
    - Never use 0.0.0.0.
    - Specify exceptions for review with security.

</br>

- **S3 Buckets:** 

	- There are no public S3 buckets. 
    - Specify exceptions for review.

##### Authentication 

- The method for authenticating users is documented. If the application is connected to the  ADFS, please specify it.

##### Data

- Review the next information to accomplish the points.

	- All data are encrypted at rest and in transit, with custom KMS if the data is sensitive. 
    - Please document the sensitive data and present it to cibersecurity. GDPR Compliance.
    - All the data is stored in the EU.
    - All passwords and secrets are stored in services like KMS, parameter store o secrets manager and there is no keys or secrets hardcoded in the repository or in the application.
    
##### Application (optional but required in the future).

- Ensure that it has passed the cyber security validation of vulnerabilities and library versions or any installed dependencies.

##### Only IAM access  (need CoE approval)

- Roles have minimum permissions and apply the least-priviledge principle.
- Users with Access Key/Secret Key (i.e. ingestion process) are documented. Specify it in the review.


If you have all this things documented and/or your entire architecture uses pre-approved by security pieces, you can skip the cibersecurity review sending all the information to [Ciberseguridad](EMAIL</u>)</span>
