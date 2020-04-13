## 使用说明

本脚本用于TKE集群节点基础信息收集


## 使用方式

将脚本放置节点中`sh/bash TKE_info_check.sh `

脚本执行完毕后日志将会收集到`/tmp/tkelog/tkelog.tar.gz`

## 主要功能
收集kubelet、docker、kube-proxy、dmesg、iptables、message日志
集群ID、镜像版本、内核、主机名、SELinux状态、kubelet资源预留、内存信息、磁盘信息、网络信息、DNS、路由表、端口监听、
cpu/mem TOP10进程、巴拉多进程检查、NTP状态、node资源使用情况、kubectl版本、docker版本

 
## 效果展示
```
[root@VM_1_11_centos ~]# sh TKE_info_check.sh 
# ------------------------------------------------------------------------------
# v2020.1 ,当前集群：
# 您好！本脚本纯shell编写，用于收集系统日志以及相关服务、组件日志等，
#
# 目前兼容TKE的Ubuntu、Centos，脚本开源，您可以用编辑器打开脚本查阅里面的代码。
#
# 确认脚本无误后，放到TKE集群节点上运行。
#
# 成功后，请把/tmp/tkelog/tkelog.tar.gz打包文件发我们进行问题排查，感谢您的支持！
# ------------------------------------------------------------------------------

继续请输(y)退出请输(n)：y
[INFO] 系统基础信息:CentOS 3.10.0-1062.9.1.el7.x86_64
[INFO] kubelet CPU预留资源:60m Mem预留资源:160Mi
[INFO] 正在收集CPU基础信息...CPU型号:AMD EPYC 7K62 48-Core Processor
[INFO] 内存基本使用情况:已使用内存:361M,总内存:990M,内存使用率:36.4646%
[INFO] 正在收集磁盘基础状态...√ 部分展示：磁盘使用率:0% 卷名:/dev 
[PASS] 当前磁盘indoe数正常...√
[PASS] 当前磁盘使用率正常...√
[INFO] 基础网络信息:eth0: 10.5.1.11/24 docker0: 169.254.32.1/28 cbr0: 172.16.27.1/24 
[INFO] 正在收集路由...√
[INFO] 正在收集监听...√
[INFO] 收集内存TOP10的进程...√
[PASS] 检查是否有特殊进程... 无特殊进程√
[PASS] 检查巴拉多进程是否存在... 存在 √
[PASS] 检查Sgagent进程是否存在... 存在 √
[PASS] 检查是否含有僵尸进程...未发现僵尸进程√
[INFO] 正在收集服务状态...√
[INFO] 正在收集登录记录...√
[INFO] 正在收集用户状态...√
[INFO] 正在收集Sudoers...√
[INFO] 正在收集防火墙规则 ...√
[INFO] 正在检查NTP状态 ...√
[INFO] 正在检查已安装软件...√
[PASS] 集群运行状态正常...√
[INFO] 收集k8s基础信息...√
[INFO] 收集k8s版本号,api和基础信息...√
[INFO] 正在收集k8s组件日志...√
[INFO] 正在收集docker...√
[INFO] 正在打包日志文件~~~
[INFO] 检查结果已放置在：/tmp/tkelog/tkelog-20200413-15.56.54.tar.gz
[INFO] 详细结果可看/tmp/tkelog/tkecheck-VM_1_11_centos-20200413.log
```

## 后续

本脚本已不再更新，目前TKE已推出了集群健康检查，若有在使用TKE集群的，在运维中心即可看到此功能。
