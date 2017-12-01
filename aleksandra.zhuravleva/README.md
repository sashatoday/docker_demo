# Postgres Database and Rest Service deployment by Docker
## Description
The repository contains Dockerfiles which you can use to build 2 images. To simplify the deployment, ready images are available on DockerHub. Therefore, you can immediately run necessary containers (see _Quick Start_). 

The first container starts Postgres daemon to provide access to database that contains directors and storage groups data.

The second one provides the RestAPI for database analysis reports using Sping Framework and Hibernate requests inside. 

## Quick start
You can run containers in 2 ways.
1. If you have Docker Compose tool: 
* download `docker-compose.yml` from this repo 
* go to the folder where the file is located
* run the following command: `docker-compose up`
2. Or you can run two containers separately in the specified order:
* `docker run -it --rm --name db sashadock/postgres_database`
* `docker run -it --rm -p 127.0.0.1:8080:8080 --link db --name app sashadock/rest_service_application`

## Link to the images
Docker downloads images itself when you run containers for the first time, but you can download images manually from DockerHub:
* [Postgres database image](https://hub.docker.com/r/sashadock/postgres_database/)
* [Rest service image](https://hub.docker.com/r/sashadock/rest_service_application/)

## How to use Rest Service application
### Charts
Open `dbAnalysisReport.html` from this repo in your browser. The page displays results of database queries on the charts.

Possible values for the _DirectorID_:
* <sub>FA-1D</sub>
* <sub>FA-2D</sub>
* <sub>FA-3D</sub>
* <sub>FA-4D</sub>

Possible values for the _StorageGroupID_:
* <sub>VHDC2DBESX_SG</sub>
* <sub>VHDC2DBESX_GOLD_SG</sub>
* <sub>VHDC1DBESX_SG</sub>
* <sub>VSEMPPRDEMC03_GK</sub>
* <sub>PRDDC2SNWN01_SG</sub>
* <sub>SVALBPRDTPD01_SG</sub>
* <sub>SVALBPRDTPS04_SG</sub>
* <sub>SVALBZWESX_SG</sub>
* <sub>SVALBZNESX_SG</sub>
* <sub>SVALBRGESX_SG</sub>
* <sub>SVALBPRDWCM01_SG</sub>
* <sub>SVALBPRDTPX01_SG</sub>
* <sub>SVALBPRDTPS03_SG</sub>
* <sub>SVALBPRDTPD04_SG</sub>
* <sub>SVALBPRDTPD03_SG</sub>
* <sub>SVALBPRDTPD02_SG</sub>
* <sub>SVALBPRDLTS02_SG</sub>
* <sub>SVALBPRDLKD01_SG</sub>
* <sub>SVALBPRDDBS30_SG</sub>
* <sub>SVALBMGESX_SG</sub>
* <sub>SVALBBCVDI_SG</sub>
* <sub>SVALBBCESX_SG</sub>
* <sub>PZRDC2SESX_SG</sub>
* <sub>PRDDC2ETPD02_SG</sub>
* <sub>PRDDC2ETPD01_SG</sub>
* <sub>GCPDWP00_SG</sub>
* <sub>CLALBPRDBS01_SG</sub>
* <sub>ALB_VPLEX_0466_BE_SG</sub>

### Json format
Go to [localhost:8080](http://localhost:8080). Make Rest request for one of the reports to see json result of the query.

For example, [localhost:8080/reporting?report=AllDirectors](http://localhost:8080/reporting?report=AllDirectors).

Available reports:
* AllDirectors
* AllStorageGroups
* ProblemDirectors
* ProblemIntervals
* SlowStorageGroups

## Author
Aleksandra Zhuravleva, guravleva.aleksandra@gmail.com
