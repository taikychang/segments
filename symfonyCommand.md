
# Symfony2 常用命令

### 查看所有服务

```
app/console debug:container
```

### 生成 Bundle

```
app/console generate:bundle --namespace=Acme/BlogBundle
```

### 生成 Controller

```
app/console generate:controller --controller=Acme/BlogBundle:Post
```

### 新建数据库

```
app/console doctrine:database:create
```

### 生成实体对象 getter && setter

```
app/console doctrine:generate:entities Acme/BlogBundle
```

### 生成数据表
```
app/console generate:doctrine:form Acme/BlogBundle:Post
```

### 根据已存在的数据表生成实体

```
app/console doctrine:mapping:import --force AppBundle xml
```

### 装载数据

```
app/console doctrine:fixtures:load
```

### 创建静态资源的快捷方式到 web 目录

```
app/console assets:install web --symlink
```

### 导出 FOSJsRoutingBundle 下的路由到 web 目录

```
app/console fos:js-routing:dump
```

### 合并资原文件

```
app/console assetic:dump --env=prod
```

### 优化自动加载

```
composer dump-autoload --optimize
```

### Reset

```
rm -rf ./app/cache/dev;
rm -rf ./app/cache/prod;
rm -rf ./app/logs/*.log;
rm -rf ./web/bundles;
rm -rf ./web/css;
rm -rf ./web/images;
rm -rf ./web/js;

app/console assets:install web --symlink;
app/console fos:js-routing:dump;
app/console assetic:dump --env=prod;

chmod 0777 -R ./app/cache;
chmod 0777 -R ./app/logs;

composer dump-autoload --optimize;
```