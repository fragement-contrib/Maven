# [Maven](https://github.com/fragement-contrib/Maven)
Maven学习和代码练习

## 如何运行？

首先，需要进行打包：

```
mvn clean package
```

然后，命令行进入```target/classes```后执行：

```
java io.github.zxl20070701.maven.App
```

## 创建 Java 项目

```
mvn archetype:generate "-DgroupId=io.github.zxl20070701.start" "-DartifactId=myProject" "-DarchetypeArtifactId=maven-archetype-quickstart" "-DinteractiveMode=false"
```

## 创建 Java Web 项目

mvn archetype:generate "-DgroupId=io.github.zxl20070701.start" "-DartifactId=myProject" "-DarchetypeArtifactId=maven-archetype-webapp"

### 借助jetty运行

首先，在```pom.xml```文件中修改配置：

```html
</project>
    ......
    <build>
        <finalName>myProject</finalName>
        <pluginManagement>
            <!--配置Jetty-->
            <plugins>
                <plugin>
                    <groupId>org.mortbay.jetty</groupId>
                    <artifactId>maven-jetty-plugin</artifactId>
                </plugin>
            </plugins>
        </pluginManagement>
    </build>
</project>
```

然后直接运行：

```
mvn jetty:run
```

现在就可以在8080端口上访问应用了。

## 版权

MIT License

Copyright (c) [zxl20070701](https://zxl20070701.github.io/notebook/home.html) 走一步，再走一步
