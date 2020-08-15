
# Setup Azkaban for Solo server 

## Install Git and Java 

    yum install git java -y 

## Install java developement package 

    yum install 


Install Gradle

  wget 

Install gradlew 





## Clone the repo:
  run 
  
    git clone https://github.com/azkaban/azkaban.git
    
## Build Azkaban and create an installation: run 

    cd azkaban; ./gradlew build installDist
    
## Start the server: run 

    cd azkaban-solo-server/build/install/azkaban-solo-server; bin/azkaban-solo-start.sh

## Stop server: run 

    bin/azkaban-solo-shutdown.sh from within the azkaban-solo-server installation directory

