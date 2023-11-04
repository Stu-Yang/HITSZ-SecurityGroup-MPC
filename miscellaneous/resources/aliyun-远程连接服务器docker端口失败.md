# 远程连接服务器docker端口失败

## 1. 背景介绍

### 1.1 阿里云服务器背景

该阿里云实例（实例ID为`i-wz91kwffr62f5fg8m4q8`，公网IP为`119.23.49.73`）是基于共享镜像构建，该共享镜像是通过另一台阿里云服务器的快照构建。今年，由于另一台阿里服务器到期，且该服务器账号是个人持有，公司决定更改账号，改为公司负责人持有，因此新创建了阿里云账号并在此下单新阿里云服务器。新阿里云服务器是基于旧阿里云服务器的快照构建共享镜像来构建的，而旧阿里云服务器使用正常，一切下述功能都能支持，但在新阿里云服务器出现了远程连接服务器docker端口失败的情况

### 1.2 为什么会出现docker端口连接的需求？

旧服务器是购买以提供linux服务器给公司职员使用，为避免各职员使用的linux环境相关干扰，故在宿主机新建若干个dokcer镜像提供给大家使用（尽管这样会使得各位职员无法在服务器上使用docker服务），且通过调试能够完成下述操作，而后根据旧服务器创建的新服务器能够登陆，其软件环境都存在有效，但无法进行远程连接docker操作。

创建命令为（我确保该端口没有被占用）：

```bash
# docker run -itd --name=cyy -p 23110:22 -p 23111-23115:23111-23115 -h cyy ubuntu20.04_ssh:demo /home/startup.sh
```

下面是关于docker，以及新创建镜像的信息的一些信息

```bash
root@iZwz91kwffr62f5fg8m4q8Z:~# docker -v
Docker version 20.10.12, build e91ed57
root@iZwz91kwffr62f5fg8m4q8Z:~# docker ps --format "{{.ID}}: {{.Ports}}\t{{.Names}}"
f3062fac56c7: 0.0.0.0:23111-23115->23111-23115/tcp, :::23111-23115->23111-23115/tcp, 0.0.0.0:23110->22/tcp, :::23110->22/tcp    cyy
```

### 1.3 远程连接错误

目前能够通过正常连接宿主机，例如通过Vscdoe远程连接宿主机，在本机的`/Users/xxx/.ssh/config`中有

```txt
Host Crypto
    HostName 119.23.49.73
    User root
```

进入宿主机后，确保刚刚新创建的镜像f3062fac56c7启动，但想通过通过VsCode、Powershell、Mac终端和Xshell均显示进行远程连接docker端口，均显示无法连接，其报错信息如下：

#### 1.3.1 通过Vscode远程连接

首先在本机的`/Users/xxx/.ssh/config`中添加

```bash
Host cyy
    HostName 119.23.49.73
    Port 23110
    User root
```

然后进行连接，VsCode界面显示`无法与"cyy"建立连接:操作已超时.`，相关日志显示

```bash
[11:23:58.260] Log Level: 2
[11:23:58.270] SSH Resolver called for "ssh-remote+cyy", attempt 1
[11:23:58.271] "remote.SSH.useLocalServer": true
[11:23:58.271] "remote.SSH.useExecServer": false
[11:23:58.271] "remote.SSH.path": undefined
[11:23:58.271] "remote.SSH.configFile": undefined
[11:23:58.271] "remote.SSH.useFlock": true
[11:23:58.271] "remote.SSH.lockfilesInTmp": false
[11:23:58.271] "remote.SSH.localServerDownload": auto
[11:23:58.271] "remote.SSH.remoteServerListenOnSocket": false
[11:23:58.272] "remote.SSH.showLoginTerminal": false
[11:23:58.272] "remote.SSH.defaultExtensions": []
[11:23:58.272] "remote.SSH.loglevel": 2
[11:23:58.272] "remote.SSH.enableDynamicForwarding": true
[11:23:58.272] "remote.SSH.enableRemoteCommand": false
[11:23:58.272] "remote.SSH.serverPickPortsFromRange": {}
[11:23:58.272] "remote.SSH.serverInstallPath": {}
[11:23:58.276] VS Code version: 1.83.1
[11:23:58.276] Remote-SSH version: remote-ssh@0.106.5
[11:23:58.276] darwin arm64
[11:23:58.277] SSH Resolver called for host: cyy
[11:23:58.277] Setting up SSH remote "cyy"
[11:23:58.279] Acquiring local install lock: /var/folders/n2/0czsld552v995pg3g544kchh0000gn/T/vscode-remote-ssh-f960bfd8-install.lock
[11:23:58.282] Looking for existing server data file at /Users/yangpeng/Library/Application Support/Code/User/globalStorage/ms-vscode-remote.remote-ssh/vscode-ssh-host-f960bfd8-f1b07bd25dfad64b0167beb15359ae573aecd2cc-0.106.5-tr/data.json
[11:23:58.282] Using commit id "f1b07bd25dfad64b0167beb15359ae573aecd2cc" and quality "stable" for server
[11:23:58.285] Install and start server if needed
[11:23:58.286] PATH: /Users/yangpeng/miniconda3/bin:/Users/yangpeng/miniconda3/condabin:/opt/homebrew/bin:/opt/homebrew/sbin:/usr/local/bin:/System/Cryptexes/App/usr/bin:/usr/bin:/bin:/usr/sbin:/sbin:/var/run/com.apple.security.cryptexd/codex.system/bootstrap/usr/local/bin:/var/run/com.apple.security.cryptexd/codex.system/bootstrap/usr/bin:/var/run/com.apple.security.cryptexd/codex.system/bootstrap/usr/appleinternal/bin:/Library/TeX/texbin:/Users/yangpeng/.cargo/bin
[11:23:58.286] Checking ssh with "ssh -V"
[11:23:58.297] > OpenSSH_9.3p2, LibreSSL 3.3.6

[11:23:58.299] askpass server listening on /var/folders/n2/0czsld552v995pg3g544kchh0000gn/T/vscode-ssh-askpass-93816adb62ff46ba471e2b61a98ecef4e357ae4f.sock
[11:23:58.299] Spawning local server with {"serverId":1,"ipcHandlePath":"/var/folders/n2/0czsld552v995pg3g544kchh0000gn/T/vscode-ssh-askpass-6f5df7f13c41eb3a8800f77e6b3bda9677152b8c.sock","sshCommand":"ssh","sshArgs":["-v","-T","-D","60415","-o","ConnectTimeout=15","cyy"],"serverDataFolderName":".vscode-server","dataFilePath":"/Users/yangpeng/Library/Application Support/Code/User/globalStorage/ms-vscode-remote.remote-ssh/vscode-ssh-host-f960bfd8-f1b07bd25dfad64b0167beb15359ae573aecd2cc-0.106.5-tr/data.json"}
[11:23:58.299] Local server env: {"SSH_AUTH_SOCK":"/private/tmp/com.apple.launchd.j499onAcT4/Listeners","SHELL":"/bin/zsh","DISPLAY":"1","ELECTRON_RUN_AS_NODE":"1","SSH_ASKPASS":"/Users/yangpeng/.vscode/extensions/ms-vscode-remote.remote-ssh-0.106.5/out/local-server/askpass.sh","VSCODE_SSH_ASKPASS_NODE":"/Applications/Visual Studio Code.app/Contents/Frameworks/Code Helper (Plugin).app/Contents/MacOS/Code Helper (Plugin)","VSCODE_SSH_ASKPASS_EXTRA_ARGS":"--ms-enable-electron-run-as-node","VSCODE_SSH_ASKPASS_MAIN":"/Users/yangpeng/.vscode/extensions/ms-vscode-remote.remote-ssh-0.106.5/out/askpass-main.js","VSCODE_SSH_ASKPASS_HANDLE":"/var/folders/n2/0czsld552v995pg3g544kchh0000gn/T/vscode-ssh-askpass-93816adb62ff46ba471e2b61a98ecef4e357ae4f.sock"}
[11:23:58.300] Spawned 76178
[11:23:58.425] > local-server-1> Running ssh connection command: "-v -T -D 60415 -o ConnectTimeout=15 cyy"
[11:23:58.427] > local-server-1> Spawned ssh, pid=76185
[11:23:58.433] stderr> OpenSSH_9.3p2, LibreSSL 3.3.6
[11:24:13.439] stderr> ssh: connect to host 119.23.49.73 port 23110: Operation timed out
[11:24:13.440] > local-server-1> ssh child died, shutting down
[11:24:13.451] Local server exit: 0
[11:24:13.452] Received install output: local-server-1> Running ssh connection command: "-v -T -D 60415 -o ConnectTimeout=15 cyy"
local-server-1> Spawned ssh, pid=76185
OpenSSH_9.3p2, LibreSSL 3.3.6
ssh: connect to host 119.23.49.73 port 23110: Operation timed out
local-server-1> ssh child died, shutting down

[11:24:13.458] Resolver error: Error: 操作已超时
```

### 1.3.2 通过Mac终端连接

Mac终端使用ssh服务正常，且能正常连接其他服务器，连接命令和报错信息如下：

```bash
yp@MacBook-Air ~ % ssh -p 23110 root@119.23.49.73
ssh: connect to host 119.23.49.73 port 23110: Operation timed out
```

### 1.3.3 通过Xshell连接

按照用户：ccy，SSH协议，主机 119.23.49.73，端口23110进行设置，然后连接，报错信息如下：

```bash
Connecting to 119.23.49.73:23110...
Could not connect to '119.23.49.73' (port 23110): Connection failed.
```

### 1.4 目前尝试的解决方法

根据[无法连接Linux实例的排查方法](https://help.aliyun.com/zh/ecs/support/troubleshooting-guidelines-when-you-cannot-remotely-log-on-to-a-linux-instance-through-ssh?spm=a2c4g.11186623.0.i1)，我尝试了【**检查端口和安全组**】，确保在安全组规则中有：

- 方式一：快速添加安全组规则
  - **授权策略****：**允许
  - **端口范围****：**SSH（22）
  - **授权对象****：**0.0.0.0/0（代表所有IP访问）
- 方式二：手动添加安全组规则
  - **授权策略****：**允许
  - **优先级****：**1（代表安全规则中优先级最高，数字越小优先级越高）
  - **协议类型****：**自定义（TCP）
  - **端口范围****：**SSH（22）
  - **授权对象****：**0.0.0.0/0（代表所有IP访问，也可根据需要，自定义设置授权对象）



进一步地，我确保宿主机的docker和ssh服务器都正常，但是仍然无法正常连接，想问一下这个如何解决？