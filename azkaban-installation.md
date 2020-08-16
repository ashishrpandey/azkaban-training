
# Setup Azkaban for Solo server 

## Install Git  

    yum install git -y 

## Install java developement package 

    yum install java-1.8.0-openjdk-devel
    java -version


## Install Gradle

      wget https://services.gradle.org/distributions/gradle-5.0-bin.zip -P /tmp
      sudo unzip -d /opt/gradle /tmp/gradle-5.0-bin.zip
      ls /opt/gradle/gradle-5.0
      vim /etc/profile.d/gradle.sh
  
- Initialize the PATH and GRADLE_HOME in gradle.sh 

      export GRADLE_HOME=/opt/gradle/gradle-5.0
      export PATH=${GRADLE_HOME}/bin:${PATH}
      
- Execute gradle.sh 

        sudo chmod +x /etc/profile.d/gradle.sh
        source /etc/profile.d/gradle.sh
    
- Verify gradle installation 

        gradle -v

Install gradlew 

        gradle wrapper --gradle-version 5.0



## Clone the repo:
  run 
  
    git clone https://github.com/azkaban/azkaban.git
    
## Build Azkaban and create an installation: run 

    cd azkaban; ./gradlew build installDist
    
## Start the server: run 

    cd azkaban-solo-server/build/install/azkaban-solo-server; bin/azkaban-solo-start.sh

## Stop server: run 

    bin/azkaban-solo-shutdown.sh from within the azkaban-solo-server installation directory

