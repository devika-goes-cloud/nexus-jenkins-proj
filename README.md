

## Deploying Java WAR Artifact to Nexus via Jenkins


This project uses a Jenkins pipeline to build a Java application and deploy its WAR artifact to a Nexus Repository Manager (Nexus 3).


<img width="1912" height="827" alt="image" src="https://github.com/user-attachments/assets/c1cf775c-0d20-44ca-b110-7a6d16f39efb" />
<br>
<img width="1238" height="977" alt="nexus" src="https://github.com/user-attachments/assets/8aebaf53-31e2-4ec1-b3c4-ab5ef02bf285" />



**Pipeline stages:**

- Tool Install – Configures Maven in Jenkins.

- Code Checkout – Pulls source code from the Git repository.

- Package App – Uses Maven to compile the code and package it into a WAR file (mvn clean package).

- Push to Nexus – Uploads the WAR file to the Nexus repository using nexusArtifactUploader.

- Post Actions – Final cleanup and notifications.



