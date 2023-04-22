## Wireguard自动更新密钥脚本
**使用本脚本的前提为你已正确安装配置Wireguard**
对于使用代理方式科学上网的人来说，被封是比较麻烦的事。但如果是使用Wireguard被封，只需要换一个公钥私钥对即可，本脚本可自动更新密钥对，生成的客户端密钥文件路径为默认的/etc/wireguard
### 使用方法
拉取代码，赋予脚本文件可执行权限：
```shell
sudo chmod +x wireguard_key_update.sh
```

将该脚本执行加入crontab定时任务：

```shell
crontab -e
```

使用VIm编辑加入一行(脚本路径为/home)：

```shell
35 3 * * * bash /home/wireguard_key_update.sh
```

然后保存退出crontab即可。

此时服务端的脚本会每天定时更新，再定时传文件到本地即可。
