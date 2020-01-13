由于公司开发的平台需要部署在不同的linux发行版上，在部署细节上有所区别，造成部署流程文档冗长。用docker就没有这样的问题了，搞起。
在写好dockerfile和docker-compose.yml后成功运行了项目。然而发现挂载的tomcat9/log文件夹内没有catalina.out文件。

因为docker维持运行需要terminal维持运行，所以在dockerfile里使用bash catalina.sh run来运行tomcat。catalina.out只有在bash startup.sh才会产生。

解决方案：

运行catalina.sh run时使用>>输出文件

```dockerfile
CMD ["bash", "catalina.sh", "run", ">>", "/usr/local/apache-tomcat-9.0.27/logs/catalina.out", "2>&1"]
```

