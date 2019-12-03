# Auto CI for Jenkins on a Linux Machine
Shell script to automatically download and install all required tools to kickstart a basic CI pipeline

## Basic Setup
Clone this repository using `git clone https://github.com/pjw6193/jenkins-ci-linux.git`.
Give run permissions to this file with: `chmod 111 auto-ci.sh`
Run the script with `sh auto-ci.sh`

## Setup Jenkins 
Navigate to your Jenkins with http://your.aws.ip:8080/jenkins
Follw their instructions there.

## Tools Installed
You will have OpenJDK 8, Maven 3.3.3, Git, and Jenkins latest running on Tomcat 8.5.40.

## Tomcat Maven Plugin
You will find an example pom.xml which shows the build configuration for using Continuous Deployment to the Tomcat server. The script adds a manager-script user with username `maven` in the `tomcat-users.xml` which is also configured for POM use in the Maven `settings.xml` in the `<server>` tag. This way we do not have to put Tomcat username/password credentials directly into the POM file. You can then build the project with:

`mvn tomcat7:deploy`

For more information, goto http://tomcat.apache.org/maven-plugin-trunk/tomcat7-maven-plugin/usage.html


