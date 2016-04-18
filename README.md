# MyBatis Generator auto comment plugin


Generate comment from database column's comment.

table's comment must set useInformationSchema = true

## Using the plugin

First things first, clone this repository locally and run:

    mvn clean install

Then, in your MyBatis Generator configuration, include the plugin:

    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE generatorConfiguration
            PUBLIC "-//mybatis.org//DTD MyBatis Generator Configuration 1.0//EN"
            "http://mybatis.org/dtd/mybatis-generator-config_1_0.dtd">

    <generatorConfiguration>
        <context id="example"
                 targetRuntime="MyBatis3Simple"
                 defaultModelType="flat">
            <!-- include the plugin -->
            <plugin type="com.blackcowx.mybatis.generator.plugins.CommentPlugin"/>
            <commentGenerator>
                <property name="suppressAllComments" value="true" />
                <property name="suppressDate" value="true"/>
            </commentGenerator>
            <!-- other configurations -->

        </context>
    </generatorConfiguration>

If you run MyBatis Generator from Maven, you can add the plugin as a dependency
for mybatis-generator-maven-plugin:

    <plugin>
        <groupId>org.mybatis.generator</groupId>
        <artifactId>mybatis-generator-maven-plugin</artifactId>
        <version>${mybatis.generator.version}</version>
        <configuration>
            <overwrite>true</overwrite>
        </configuration>
        <dependencies>
            <dependency>
                <groupId>com.blackcowx</groupId>
                <artifactId>mybatis-generator-auto-comment-plugin</artifactId>
                <version>1.0-SNAPSHOT</version>
            </dependency>
        </dependencies>
    </plugin>

If use Gradle:

        mybatisGenerator (
                "org.mybatis.generator:mybatis-generator-core:$mybatisGeneratorVersion",
                "mysql:mysql-connector-java:$mysqlDriverVersion",
                "com.blackcowx:mybatis-generator-auto-comment-plugin:1.0-SNAPSHOT"
        )

## Author

[blackcowx](https://github.com/blackcowx)
