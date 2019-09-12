### 编译PHP 7.2版本
> 特性：
1) 基于官方镜像php:7.2-fpm
2) 默认调优好PHP-FPM配置
3) 默认设置容器中文
4) 添加宋体字体防止个别应用乱码
5) 设置上海时区,防止时间不正常
6) 设置容器默认163源，阿里源用于php会部分找不到依赖包
> 目录说明：
1) PHP配置路径 /usr/local/etc
> 其他说明：
1) 默认创建www用户组与用户
2) PHP-FPM 默认运行用户组与用户 www
3) 如遇权限问题，请将项目授权chown -R www:www 项目目录
4) 具体PHP优化可以参考config目录下文件
#### 1、使用方法
```
git clone https://gitee.com/G-Akiraka/Docker-php_7.2.git && cd Docker-php_7.2
```
#### 2、开始构建Docker PHP镜像 
```
docker build -f Dockerfile -t php:7.2-fpm .
```
#### 3、运行PHP容器
```
docker run -d -p 9000:9000 --name myphp php:7.2-fpm
```
#### 4、查看PHP容器是否运行
```
docker ps
```
#### 5、 调试容器，如果需要的话
docker exec -it myphp /bin/bash