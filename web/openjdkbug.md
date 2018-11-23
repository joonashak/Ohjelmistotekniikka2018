## Bugi OpenJDK:n uusimmassa versiossa (marraskuu 2018)

OpenJDK:n uusimmassa versiossa on bugi, joka saattaa estää ohjelman ja/tai testien ajamisen tarkastettaessa. 

Helpottaaksesi tarkastajien työtä lisää pom.xml tiedostoon maven-surefire-plugin:

```
<plugin>
  <groupId>org.apache.maven.plugins</groupId>
  <artifactId>maven-surefire-plugin</artifactId>
  <version>2.16</version>
  <configuration>
    <argLine>-Djdk.net.URLClassPath.disableClassPathURLCheck=true</argLine>
  </configuration>
</plugin>
```

Jos olet jo määrittänyt ko. pluginin, lisää sen `<configuration>` -tagien sisään seuraava rivi:

`<argLine>-Djdk.net.URLClassPath.disableClassPathURLCheck=true</argLine>`
