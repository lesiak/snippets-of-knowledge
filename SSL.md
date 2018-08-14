## New Nexus Repo - Ocean wide [browsable url](https://nexus.ocean.tech.lastmile.com/#browse/)



### Command-line Maven Cert Installation (if needed)
#### OSX
download the cert:
```
wget http://aaa.com/certs/aaa.pem -O /usr/local/share/ca-certificates/aaa.crt
```

Add to keystore:
```
keytool -importcert -trustcacerts -alias lastmile -file /usr/local/share/ca-certificates/aaa.crt -keystore $JAVA_HOME/jre/lib/security/cacerts
```

#### Windows
download the certs:
```
wget http://aaa.com/certs/aaa.pem -O %HOME%/aaa.pem
```
Alternatively download the certificates by opening the http addresses directly.

Add to keystore:  
You may need to run Cmd as Admin:
```
keytool -importcert -trustcacerts -alias aaa -file %HOME%/aaa.pem -keystore "%JAVA_HOME%\jre\lib\security\cacerts" -storepass changeit -noprompt
```
If Windows complains about keytool not existing you need to add your Java bin directory to the PATH environment variable.

Java 9 and above may not have the jre folder inside their home directory.  In this case find the security folder within the java directory and use that address.

Addresses can be entered manually if you are using multiple versions of Java for whatever reason, or if you did not download the certificates to the %HOME% directory.  If you still get errors when running maven enter the command "mvn --version" and double check you have added the certificates to the correct version of Java.

When running gradle make sure you restart the gradle daemon after adding the certificates, otherwise it will not pick up the changes.

### IDEA/IntelliJ

Under File -> Settings -> Build, Execution, Deployment -> Remote Jar Repositories, add to the "Artifactory or Nexus Service URLs" the appropriate repository eg https://aaa.com/repository/maven-releases/ and 'test'. You will be asked to accept and store the certificate in IntelliJ's certificate cache.