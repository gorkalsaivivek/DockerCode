# DockerCode

In pom.xml


<plugin>
	<groupId>com.spotify</groupId>
	<artifactId>dockerfile-maven-plugin</artifactId>
	<version>1.4.10</version>
	<executions>
		<execution>
			<id>default</id>
			<goals>
				<goal>build</goal>
				<goal>push</goal>
			</goals>
		</execution>
	</executions>
	<configuration>
		<repository>7039402000/secondproject</repository>
		<tag>${project.version}</tag>
		<pullNewerImage>false</pullNewerImage>
		<skipDockerInfo>true</skipDockerInfo>
	</configuration>
</plugin>



Dockerfile

FROM openjdk:8-jdk-alpine
EXPOSE 8080
ADD target/*.jar dockerkubernetes.jar
ENTRYPOINT ["sh", "-c", "java -jar /dockerkubernetes.jar"]
