在github上构建maven库的步骤：
1、在项目的pom.xml增加如下代码
	<distributionManagement>
		<repository>
			<id>internal.repo</id>
			<name>Temporary Staging Repository</name>
			<url>file://${project.build.directory}/mvn-repo</url>
		</repository>
	</distributionManagement>
  执行mvn clean deploy,将目录file://${project.build.directory}/mvn-repo下面的代码提交到https://github.com/wuzhong290/mavenrepo.git下面

2、在其他项目中应用如下代码
        <dependency>
            <groupId>com.dangdang</groupId>
            <artifactId>config-toolkit-redis</artifactId>
            <version>3.1.3-RELEASE</version>
        </dependency>

        <repository>
            <id>wuzhongtuniu-maven-repo</id>
            <url>https://raw.githubusercontent.com/wuzhong290/mavenrepo/master/mvn-repo</url>
        </repository>