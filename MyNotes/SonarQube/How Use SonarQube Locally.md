The easiest way to use SonarQube is to use a local version.

# Installation
To install local version of Sonarqube with docker you can launch this command:  

```bash
docker run -d -p 9000:9000 sonarqube
```

In case you have new Apple processors, from **M1** onwards you can use the following command:

```sh
docker run -d -p 9000:9000 mwizner/sonarqube:8.7.1-community
```

In fact, the official image of Sonarqube is not yet supported by the new Apple processors

# How use SonarQube

To use Sonarqube you need to add its dependency in your project.

## Maven
If you use Maven you can add the following plugin:

```html
<plugin>  
    <groupId>org.scoverage</groupId>  
    <artifactId>scoverage-maven-plugin</artifactId>  
    <version>1.4.11</version>  
</plugin>
```

### Launch analysis
To launch the analysis and obtain report with maven you can launch the following script:

```sh
#!/bin/sh  
# utility script to use Scoverage with a local version of SonarQube in sbt project
# need to update login, project key and port value with yours

# @author Giovanni Brunetti (https://github.com/GB1609) 

# need to update login key, project name and port value with yours

key=eed1f56524d501ed58ea52e4d9defed1c67de1e5  
port=9000  
project=gemini  
  
# pls note that you need mvn version used for the project,  
# '/Library/Developer/apache-maven-3.6.3/bin/mvn' is my personal one  
mvn clean  
mvn scoverage:report -f pom.xml  
mvn sonar:sonar \  
  -Dsonar.projectKey=$project \  
  -Dsonar.sources=src/main/scala \  
  -Dsonar.tests=src/test/scala \  
  -Dsonar.host.url=http://localhost:$port \  
  -Dsonar.login=$key \  
  -Dsonar.scala.coverage.reportPaths="target/scoverage.xml"
```


## Sbt

If you use Sbt you can add the following plugin:

```html
addSbtPlugin("org.scoverage" % "sbt-scoverage" % "1.6.1")
```

### Execute 
To launch the analysis and obtain report with sbt you can launch the following script:

```sh
#!/bin/sh
# utility script to use Scoverage with a local version of SonarQube in a mvn project
# @author Giovanni Brunetti (https://github.com/GB1609) 
gcsConnector=src/main/scala/path/package/GCSConnector.scala
dataConfigPathsConnector=src/main/scala/path/package/DataConfigPathsConnector.scala

#toExclude=$gcsConnector,$dataConfigPathsConnector

sbt clean coverage test coverageReport

# need to update login and project key value with yours

sonar-scanner \
  -Dsonar.projectKey=dpf-etl \
  -Dsonar.sources=src/main/scala \
  -Dsonar.host.url=http://localhost:9000 \
  -Dsonar.login=sqp_826c244054b34e8a134c3ac3ee059f54e0ee257a \
  -Dsonar.tests=src/test/scala -Dsonar.scala.coverage.reportPaths=target/scala-2.12/scoverage-report/scoverage.xml #\
  #-Dsonar.exclusions=$toExclude
```

---

**Tag Obsidian:** #SonarQube #Apple #cleancode #Sonar #docker 