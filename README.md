# VidAS Docker  
This repository contains a ready-to-use version of PSYMBIOSYS VidAS System for Docker.  

## Content  
The components inside the repository are listed below:

- **vidas_volume**: This folder contains the docker volumes definition of all the components related to PSYMBIOSYS VidAS System.  
	- **java_security**: replicates the "security" folder of Java. It contains the JCE, to avoid limitation on keys length, and  the "cacert" file with all the reliable Certificates.
	- **tomcat**: replicates the installation directory of Apache Tomcat, in which is possible to deploy web applications in the form of ".war" files [Data](vidas_volume\tomcat\tomcat_container\tomcat\data) folder.
	- **openldap**: volume related to the OpenLDAP Docker Image, with *DB configuration*, *VidAS.schema* and *Configuration folder*
	- **orientdb**: volume related to the OrientDB Docker Image, with the databases already defined, the configuration folder and the backup folder.
- **docker-compose.yml**: YAML file used to start the entire System.
- **VidAS.ldif**: defines the structure of the directory to be managed by the OpenLDAP. It contains some users as example.
> **Note:** *Tomcat* volume contains also *Video*, *Policy*, *Keygen* and *logs* folders used by the VidAS System.

## Usage  
Download the latest version of Docker from its website and launch it. After the correct configuration of VidAS System, use the command line to move into the folder already downloaded and locally stored; type the following command:

`docker-compose up`

This command will automatically start all the services.  

> **Note:** For more details about the usage and the configuration, visit [VidAS GitHub Repository](https://github.com/FINCONS-IBD/VidAS)