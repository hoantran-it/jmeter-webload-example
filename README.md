# JMeter Web Load Testing example

JMeter maven project Amazon Web Service client API library for Java application

## Getting Started

[Download JMeter from Apache](http://jmeter.apache.org/download_jmeter.cgi)

Fork source code to local machine. Open file [page-load.jmx](src/test/jmeter/page-load.jmx) for more detail about test scenario.

![JMeter application](https://i.imgur.com/jH46F4J.png)

### Installing

Run command to run JMeter by maven plugin
```
mvn verify
```

### Sample use caces

[Configuring Jenkins to get source code from this repository](http://hoantran-it.blogspot.com/2017/09/run-jmeter-by-using-maven-on-jenkis.html)


![Jenkins](https://i.imgur.com/s4K7kqo.png)


## Built With

* [Maven](https://maven.apache.org/) - Dependency Management
* JMeter Plug-in

```
<plugins>
  <plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-surefire-plugin</artifactId>
    <version>2.14.1</version>
  </plugin>
  <plugin>
    <groupId>com.lazerycode.jmeter</groupId>
    <artifactId>jmeter-maven-plugin</artifactId>
    <version>2.2.0</version>
    <executions>
      <execution>
        <id>jmeter-tests</id>
        <phase>verify</phase>
        <goals>
          <goal>jmeter</goal>
        </goals>
      </execution>
    </executions>
  </plugin>
  <plugin>
    <groupId>com.lazerycode.jmeter</groupId>
    <artifactId>jmeter-analysis-maven-plugin</artifactId>
    <version>1.0.6</version>
    <executions>
      <execution>
        <phase>verify</phase>
        <goals>
          <goal>analyze</goal>
        </goals>
        <configuration>
          <source>${project.build.directory}/**/*.jtl</source>
          <targetDirectory>${project.build.directory}/jmeter/results</targetDirectory>
          <processAllFilesFound>true</processAllFilesFound>
        </configuration>
      </execution>
     </executions>
  </plugin>
</plugins>
```

## Versioning

For the versions available, see the [github release](https://github.com/hoantran-it/aws-service/releases)

## Authors

* **Hoan Tran** - *Initial work* - [hoantran-it](https://github.com/hoantran-it)

See also the list of [contributors](https://github.com/hoantran-it/jmeter-webload-example/graphs/contributors) who participated in this project.

## License

This project is licensed under the Apache License - see the [LICENSE.md](LICENSE.md) file for details
