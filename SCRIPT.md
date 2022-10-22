# 部署脚本

部署脚本有多个参数，皆带有默认值，在生产环境中大都需要通过环境变量进行替换。

## 主机名`DEPLOY_SERVER`
默认为空，将使用本机作为目标服务器
```sh
DEPLOY_SERVER=modoth.cn ./deploy
```

## 用户名`user_name`与密码`user_pwd`
默认分别为`adm`与`123456`,务必替换
```sh
user_name=myname user_pwd=mypassword ./deploy
```

## 应用名`app_name`
默认为`modlogie`,将作为数据存储的文件夹及数据库等名称，你可以为不同的网站实例设置不同应用名

## https证书
网址使用nginx兼容的证书，脚本将在`.local.certs/${app_name}/`目录下寻找证书文件`cert.pem`,若不存在则生成自签名证书。

> 包括证书文件在内的私有数据将在部署时添加到生成的容器镜像中，请妥善处理容器镜像以保证数据安全

## 其他参数：请直接阅读部署脚本`deploy`

> 也可以手动部署或自编脚本部署，脚本中使用的容器镜像也可以通过源码编辑