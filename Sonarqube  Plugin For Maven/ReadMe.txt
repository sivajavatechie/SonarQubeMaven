			SonarQube Plugin for Maven Project
                         ----------------------------------------------------------------------------------------------------


1) Download the latest SonarQube Server : https://www.sonarqube.org/downloads/  
Maven from: http://maven.apache.org/download.cgi, 
Java: It requires Java 8 : http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html

Install Java 8 and Maven on your computer and Set the JAVA_HOME in environment variables

2) Extract the SonarQube server zip file and navigate to bin folder 

3) Open the Command Prompt and navigate to SonarQube bin folder and execute StartSonar.bat file

4) Create maven project and add below dependency in pom.xml file

<!-- https://mvnrepository.com/artifact/org.codehaus.mojo/sonar-maven-plugin -->
<dependency>
    <groupId>org.codehaus.mojo</groupId>
    <artifactId>sonar-maven-plugin</artifactId>
    <version>3.4.0.905</version>
    <type>pom</type>
</dependency>

5) Add below profile in Pom.xml file

 <profiles>
        <profile>
            <id>sonar</id>
            <activation>
                <activeByDefault>true</activeByDefault>
            </activation>
            <properties>
                <!-- Optional URL to server. Default value is http://localhost:9000 -->
                <sonar.host.url> http://localhost:9000 </sonar.host.url>
	<--Uncomment below few lines if you are using external databases(Oracle/DB2/Mysql) -->
 <!--  <sonar.jdbc.url>your database url</sonar.jdbc.url>
<sonar.jdbc.driver>your DB driver</sonar.jdbc.driver>
<sonar.jdbc.username>DB username</sonar.jdbc.username>
<sonar.jdbc.password>DB password</sonar.jdbc.password>        -->              

            </properties>
        </profile>
     </profiles>

6) Run maven command mvn clean package 

7) Run maven command mvn sonar:sonar

8) Open the web browser and access the http://localhost:9000
