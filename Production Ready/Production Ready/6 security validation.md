This topics and requirements need to be check and discuss in the meeting are:

### Architecture

- **Diagram with the next information:**

	- Public services (exposed to the Internet - Specify protocol access, example:HTTPS ).
    - Private zones.
    - AWS services used.
    - Third party services used.
    - Cconnections with on-premise or other accounts.
    - CNAMEs with MAPFRE domains.
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

- The method for authenticating users is documented. If the application is connected to the MAPFRE ADFS, please specify it.

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