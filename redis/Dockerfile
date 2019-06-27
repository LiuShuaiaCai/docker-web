#基础镜像 
FROM redis 
#将自定义conf文件拷入 
COPY redis.conf /etc/redis/redis.conf 
#修复时区 
RUN ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime 
RUN echo 'Asia/Shanghai' >/etc/timezone 
#修改文件权限,使之可以通过config rewrite重写 
RUN chmod 777 /etc/redis/redis.conf 
# Redis客户端连接端口 
EXPOSE 6379 
# 集群总线端口:redis客户端连接的端口 + 10000 
# EXPOSE 16061 
#使用自定义conf启动 
CMD [ "redis-server", "/etc/redis/redis.conf" ]