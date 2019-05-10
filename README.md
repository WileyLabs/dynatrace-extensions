
# Custom dynatrace extensions
## Hikari Connection Pool
Hikari is a default Connection Pool used in Spring Boot 2. In order to enable monitoring Hikari's MBeans have to be [registered first](https://github.com/brettwooldridge/HikariCP/wiki/MBean-%28JMX%29-Monitoring-and-Management). For Spring Boot 2 set  `spring.datasource.hikari.register-mbeans: true`
Once application is configured and MBeans are registered new charts under "HikariCP" section would appear at the Process "Further Details" page.
## Apache ActiveMQ Artemis
Artemis is JMS2.0-compatible message broker. This dynatrace extension adds few new charts:

 - High level broker health as the key metric at primary process and Further Details pages
 - Health metrics for each queue/topic configured on broker on Further Details page

In order to enable monitoring [role-based authorization has to be configured](https://activemq.apache.org/components/artemis/documentation/latest/management.html#role-based-authorisation-for-jmx) to enable at least read access without credentials for Dynatrace.
