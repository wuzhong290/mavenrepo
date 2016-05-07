在github上构建maven库的步骤：
1、在项目的pom.xml增加如下代码
	<distributionManagement>
		<repository>
			<id>internal.repo</id>
			<name>Temporary Staging Repository</name>
			<url>file://${project.build.directory}/mvn-repo</url>
		</repository>
	</distributionManagement>
  执行mvn clean deploy,将目录file://${project.build.directory}/mvn-repo下面的代码提交到https://github.com/hengyunabc/maven-repo.git下面


