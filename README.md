IK Analysis for Opensearch
=============================

The IK Analysis plugin integrates Lucene IK analyzer (http://code.google.com/p/ik-analyzer/) into opensearch, support customized dictionary.

Analyzer: `ik_smart` , `ik_max_word` , Tokenizer: `ik_smart` , `ik_max_word`

> fork from https://github.com/medcl/elasticsearch-analysis-ik

Versions
--------

IK version | ES version
-----------|-----------
master | 1.0.0 -> master

Build
-------
1. build with maven
    ```
    mvn clean package
    ```

2. use build package at `target/releases/opensearch-analysis-ik-1.0.0.zip`

Install
-------

1.download or compile

* optional 1 - download pre-build package

  create plugin folder `cd your-os-root/plugins/ && mkdir ik`

  unzip plugin to folder `your-os-root/plugins/ik`

* optional 2 - use opensearch-plugin to install:

    ```
    ./bin/opensearch-plugin install opensearch-analysis-ik-6.3.0.zip
    ```

2.restart opensearch

Notice
-------
如何为Opensearch重新编译该插件？ 
1. 在当前工程目录下新建lib目录，并拷贝所需的jar包到lib目录下


2. 导入依赖包到idea中  
`File -> Project Structure -> Project Settings -> Modules -> Dependencies -> + -> 选择lib目录下的所有jar包 -> OK`


3. 修改pom.xml文件   
删除dependencies下elasticsearch的依赖，为每个jar包添加如下的本地依赖配置：
    ```
    <dependency>
        <groupId>org.opensearch</groupId>
        <artifactId>opensearch</artifactId>
        <version>1.0.0</version>
        <scope>system</scope>
        <systemPath>${pom.basedir}/lib/opensearch-1.0.0-beta1.jar</systemPath>
    </dependency>
    ```