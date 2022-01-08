# Nginx缓存配置样例

1. 访问 127.0.0.1,第一次访问可以看到响应头中有 `Nginx-Proxy-Cache: MISS`,这表示没有缓存.
2. 第二次访问可以看到 `Nginx-Proxy-Cache: HIT`,表示已经缓存了.
3. 进入 `/var/cache/nginx` 查看缓存文件.
4. 性能测试,安装wrk测试工具 `brew install wrk`.
```bash
#并发10,5秒测试
wrk -c 10 -d 10 http://127.0.0.1
```
配置缓存前测试结果:
![](https://tva1.sinaimg.cn/large/008i3skNly1gy6ripskobj30r40asdhb.jpg)

配置缓存后测试结果:
![](https://tva1.sinaimg.cn/large/008i3skNly1gy6roh6z8uj30ru0aojsu.jpg)

