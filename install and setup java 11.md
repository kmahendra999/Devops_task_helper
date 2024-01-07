java -version
yum install java-11-openjdk-devel
yum install java-11-openjdk


sudo alternatives --config java
alternatives --config javac
java -version
echo $JAVA_HOME


update-alternatives --config java
**copy the java path from output


vim ~/.bash_profile
source ~/.bash_profile 
echo $JAVA_HOME

Refrence : https://sysadminxpert.com/steps-to-upgrade-java-8-to-java-11-on-centos-7/
