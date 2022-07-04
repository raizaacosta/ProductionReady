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