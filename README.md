Handy Commands
==============

Maven
-----
For those who would like to know how to retrieve the maven coordinate information from pom file. This will come handy to check whether application is using master pom for the build.

To retrieve maven coordinate for <parent> tag:
mvn help:evaluate –Dexpression=project.parent.groupId
mvn help:evaluate –Dexpression=project.parent.artifactId
mvn help:evaluate –Dexpression=project.parent.version

To retrieve maven coordinate for the project:
mvn help:evaluate –Dexpression=project.groupId
mvn help:evaluate –Dexpression=project.artifactId
mvn help:evaluate –Dexpression=project.version

mvn deploy:deploy-file -Durl=https://artifactory.mycompany.com:8080/snapshots/ -DrepositoryId=artifactory -Dfile=libvisacrypto.so -DgroupId=com.visa.cbp.sdk.arxan.libs.armeabi -DartifactId=libvisacrypto -Dversion=1.0-SNAPSHOT -X -e

# attempt to delete the local repository files but it always goes and fills up the local repository after things have been removed
mvn dependency:purge-local-repository

# avoids the re-resolving of the dependencies but seems to still go to the network at times
mvn dependency:purge-local-repository -DreResolve=false

# empty local repo
mvn dependency:purge-local-repository -DactTransitively=false -DreResolve=false


Bash
----
find /usr/mware/was/.m2/repository/com/visa -type f -mtime +90 | xargs rm -vf
find . -type f -mtime +30 | xargs rm -vf
find . -type f -mtime +120
du -sk * | sort -nr | more
tar xvjf filename.tar.bz2
sudo systemctl stop firewalld
-- SSL Peer not authenicated exception
1. Run the following command, replace $ADDRESS with the URL, minus the "https://":

echo -n | openssl s_client -connect $ADDRESS:443 | sed -ne '/-BEGIN CERTIFICATE-/,/-END CERTIFICATE-/p' > /tmp/$ADDRESS.cert

2. Run the following command, replace $ALIAS a short name for the key, $ADDRESS with the cert name from above, $PATH with the path to cacerts in your JRE.

sudo keytool -importcert -alias "$ALIAS" -file /tmp/$ADDRESS.cert -keystore $PATH/cacerts -storepass changeit

get the contents of the first occurrence of someTag in file
cat file | grep '<someTag>' | head -1 | sed "s/.*<someTag>\([^<]*\)<\/someTag>.*/\1/"
netstat -tulpn

echo -e "\e[0;32mTHIS TEXT IS GREEN\e[0m"

-- random string
cat /dev/urandom | tr -dc 'a-zA-Z0-9' | fold -w 32 | head -n 1


Oracle
------
Oracle version:
select * from v$version;

