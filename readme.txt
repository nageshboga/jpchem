Build Process :

navigate to directory where the pom.xml exists.

execute the commands as below for different enviornments

production : mvn install -Pprod
test : mvn install -Ptest
development : mvn install -Pdev

war will created in the target folder.


if PKIX path error :
My company IT policies blocked maven repo https because the certificate expired date is short. Importing certificate is painful. So I used this way to fix it:

change to latest maven (verified on version 3.6.3)
add those parameters


-Dmaven.wagon.http.ssl.insecure=true -Dmaven.wagon.http.ssl.allowall=true


example : mvn clean package -Dmaven.wagon.http.ssl.insecure=true -Dmaven.wagon.http.ssl.allowall=true



From jenkins if you come across issues in maven plug-ins

create batch file and execute if you see PKIX path issues...

cd C:\WINDOWS\system32\config\systemprofile\AppData\Local\Jenkins.jenkins\workspace\listprice\listprice
mvn clean install -Dmaven.wagon.http.ssl.insecure=true -Dmaven.wagon.http.ssl.allowall=true -DskipTests=true