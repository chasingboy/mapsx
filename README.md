<h1 align="center">mapsx</h1>
<h3 align="center">mapsx 是一款端口扫描｜网段探测｜弱口令爆破工具</h3>
<p align="center">
  <img src="https://img.shields.io/badge/Version-V1.0.0-green?style=flat">
  <img src="https://img.shields.io/github/stars/chasingboy/mapsx?style=flat&labelColor=rgb(41%2C52%2C52)&color=green">
  <img src="https://img.shields.io/github/issues/chasingboy/mapsx">
  <img src="https://img.shields.io/github/downloads/chasingboy/mapsx/total?style=flat&labelColor=rgb(41%2C52%2C52)&color=green">
  <img src="https://visitor-badge.laobi.icu/badge?page_id=chasingboy.mapsx&left_color=green&right_color=#66ccff">
</p>

<img width="1154" alt="image" src="https://github.com/chasingboy/mapsx/blob/main/assets/mapsx.png">

### 前言
mapsx 是一款简单的端口扫描｜网段探测｜弱口令爆破工具。平时也经常使用 fscan 和 kscan 等工具，为什么还要花时间搞个 mapsx。一直有个执念，根据自己平时的思路和接触场景，完善一套常用的工具集。毕竟每个工具的作者所接触和使用场景往往是不大一样，所以平时使用过程中总有一些时候不是那么顺手。

### 功能
✅ 支持 172｜192｜10 等网段探测<br>
✅ 支持简单的端口扫描<br>
✅ 支持探测 WEB<br>
✅ 支持 ftp｜ssh｜mysql｜... 等弱口令爆破<br>

### 基本使用
**自动化过程：存活扫描-> 端口扫描-> WEB 探测-> 弱口令爆破**

🏷️ IP 格式
```bash
# 单个 IP
root$ mapsx -i 192.168.1.1

# 多个 IP
root$ mapsx -i 192.168.1.1,192.168.1.2
root$ mapsx -i 192.168.1.1/24
root$ mapsx -i 192.168.1.1-192.168.1.255

# 服务格式
root$ mapsx -i ssh://192.168.1.1:22

# 文件格式
root$ mapsx -l ip.txt

```
🏷️ 支持格式
```
192.168.1.1
192.168.1.1/24
192.168.1.1-192.168.1.255
ssh://192.168.1.1:2222
mysql://192.168.1.1:13306
```
🏷️ 指定端口
```
root$ mapsx -i 192.168.1.1 -p 21,22,80-88
```
🏷️ 输出结果
```
root$ mapsx -i 192.168.1.1 -o result.txt
```
<img width="1154" alt="image" src="https://github.com/chasingboy/mapsx/blob/main/assets/portscan.png">

### 网段探测
🏷️ 默认探测 172｜192｜10
```
root$ mapsx --netscan
root$ mapsx --netscan --range all
```
🏷️ 探测 192
```
root$ mapsx --netscan --range 192
root$ mapsx --netscan --range 192.168.1.1/16
```
<img width="1154" alt="image" src="https://github.com/chasingboy/mapsx/blob/main/assets/netscan.png">

### 弱口令爆破
✅ ftp
✅ ssh
✅ rdp
✅ telnet
✅ mysql
✅ mssql
✅ redis
✅ oracle
✅ mongodb
✅ postgres

🏷️ 爆破 ssh
```
root$ mapsx --cracker -i 192.168.1.1:22
root$ mapsx --cracker -i 192.168.1.1 -p 22
```
🏷️ 指定服务
```
root$ mapsx --cracker -i 192.168.1.1:2222 -s ssh
root$ mapsx --cracker -i 192.168.1.1 -p 2222 -s ssh
root$ mapsx --cracker -i ssh://192.168.1.1:2222
```
🏷️ ssh 执行命令
```
root$ mapsx --cracker -i 192.168.1.1:22 --cmd whoami
```
🏷️ 指定账号密码
```
# 单个
root$ mapsx --cracker -i 192.168.1.1:22 --username root --password root
root$ mapsx --cracker -i 192.168.1.1:22 --username root --password root
# 多个
root$ mapsx --cracker -i 192.168.1.1:22 --username root,admin --password root,admin
root$ mapsx --cracker -i 192.168.1.1:22 --username root,admin --password root,admin
# 文件
root$ mapsx --cracker -i 192.168.1.1:22 --ufile username.txt --pfile password.txt
```

<img width="1154" alt="image" src="https://github.com/chasingboy/mapsx/blob/main/assets/cracker.png">

### 公众号
该公众号用于编写 Xtools 系列工具使用文档和工具更新通知

<p align="center"><img width="300" alt="image" src="https://github.com/chasingboy/appsx/blob/main/assets/xsec.png"></p>

### 免责声明
请在使用本工具时遵循使用者以及目标系统所在国当地的相关法律法规，一切未授权测试均是不被允许的。对于因使用工具而引发的任何直接、间接、偶然、特殊性的损害均由**使用者承担责任**。

### 特别感谢
kscan@https://github.com/lcvvvv/kscan

fscan@https://github.com/shadow1ng/fscan

### 更新记录
[+] 2025-1-11【发布】mapsx V1.0.0
