[![Build Status](https://img.shields.io/travis/damianszczepanik/maven-cucumber-reporting/master.svg)](https://travis-ci.org/damianszczepanik/maven-cucumber-reporting)
[![Maven Central](https://img.shields.io/maven-central/v/net.masterthought/maven-cucumber-reporting.svg)](http://search.maven.org/#search|gav|1|g%3A%22net.masterthought%22%20AND%20a%3A%22maven-cucumber-reporting%22)
[![Maven Dependencies](https://www.versioneye.com/user/projects/55cf4ca815ff9b001400006d/badge.svg)](https://www.versioneye.com/user/projects/55cf4ca815ff9b001400006d?child=summary)


Maven mojo for the cucumber-reporting - put this into your pom.xml and run mvn clean install or mvn clean test and cucumber reports will be generated in target/cucumber-html-reports

Read more about the project and configuration here: [maven-cucumber-reports](https://github.com/damianszczepanik/cucumber-reporting)

Run with: mvn clean install

     <build>
            <plugins>
                <plugin>
				    <groupId>org.apache.maven.plugins</groupId>
				    <artifactId>maven-surefire-plugin</artifactId>
				    <configuration>
				        <testFailureIgnore>true</testFailureIgnore>
				    </configuration>
				</plugin>
                <plugin>
                    <groupId>net.masterthought</groupId>
                    <artifactId>maven-cucumber-reporting</artifactId>
                    <version>0.0.5</version>
                    <executions>
                        <execution>
                            <id>execution</id>
                            <phase>verify</phase>
                            <goals>
                                <goal>generate</goal>
                            </goals>
                            <configuration>
                                <projectName>cucumber-jvm-example</projectName>
                                <outputDirectory>${project.build.directory}/cucumber-html-reports</outputDirectory>
                                <cucumberOutput>${project.build.directory}/cucumber.json</cucumberOutput>
                                <enableFlashCharts>false</enableFlashCharts>
                            </configuration>
                        </execution>
                    </executions>
                </plugin>
            </plugins>
        </build>

You may also need the maven dependency:

        <dependency>
            <groupid>net.masterthought</groupid>
            <artifactid>maven-cucumber-reporting</artifactid>
            <version>0.2.1</version> <!-- check version with https://github.com/damianszczepanik/cucumber-reporting -->
        </dependency>

You may also need to add the sonatype repository if it has not yet been synced with the maven central repository:

           <repositories>
                <repository>
                    <id>sonatype-releases</id>
                    <url>https://oss.sonatype.org/content/repositories/releases/</url>
                </repository>
            </repositories>

