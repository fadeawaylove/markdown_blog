### 1.V2Ray搭建
> 前提：一台能访问外网的服务器。
```python
# 下载脚本
wget https://install.direct/go.sh
# 运行脚本
sudo bash go.sh 

# 相关命令
# 启动(首次安装需要手动启动)
sudo systemctl start v2ray
# 停止
sudo systemctl stop v2ray
# 重启
sudo systemctl restart v2ray
# 查看状态
sudo systemctl status v2ray
# 查看进程
ps -axu | grep v2ray
```
查看配置:
```python
cat /etc/v2ray/config.json
```
![v2ray配置截图](https://dog.fadeaway.ltd/media/2020/05/02/QQ20200501-1206272x.png)

### 2.配置客户端
[客户端下载地址](https://tlanyan.me/v2ray-clients-download/)，如果此地址失效，可以自行百度，资源应该不少。
#### 2.1 Windows客户端
> 依次点击：服务器->添加[VMess]服务器，地址填入服务器的外网ip，端口和用户id按照`config.json`中的信息填入，填完后点击确定即可，注意成功后将代理模式设置为`PAC`。          

![v2ray配置截图](https://dog.fadeaway.ltd/media/2020/05/03/572491588470086_.pic.jpg)

#### 2.2 Mac客户端
> 点击菜单中的`Configure...`选项，Address后面分别填入ip和port，User ID填入`config.json`中的id，完成后点击ok，注意成功后将代理模式设置为`PAC`。

![v2ray配置截图](https://dog.fadeaway.ltd/media/2020/05/03/572501588471082_.pic_hd.jpg)
