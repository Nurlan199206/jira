# Jira Data Center


```Ubuntu 24.04 LTS```

```PostgreSQL: 14```

```Java: 17```

```Jira: 10.4.1```




```
wget https://product-downloads.atlassian.com/software/confluence/downloads/atlassian-confluence-7.19.5-x64.bin

bash tlassian-jira-software-10.4.1-x64.bin

sudo mkdir /opt/atlassian/atlassian-agent

sudo chown -R confluence:confluence /opt/atlassian/atlassian-agent

cp atlassian-agent.jar /opt/atlassian/atlassian-agent

add on the start the line /opt/atlassian/jira/confluence/bin/setenv.sh
export JAVA_OPTS="JAVA_OPTS="-javaagent:/opt/atlassian/jira/atlassian-agent/atlassian-agent.jar -Dcom.sun.jndi.ldap.object.disableEndpointIdentification=true -Djira.autoexport=false -Dplugin.version.check.enabled=false" ${JAVA_OPTS}"

apt install postgresql

su - postgres
psql
create role confluence_user login superuser password '123';
create database confluence_db;

bash /opt/atlasian/confluence/bin/startup.sh

take key from http://yourserver.com:8090 and put in the script
```






```java -jar /opt/atlassian/atlassian-agent/atlassian-agent.jar -mail 'my@email.com' -n userName -o CompanyName -p conf -s XXXX-XXXX-XXXX-XXXX```
