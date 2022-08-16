1. centos8 yum库集成了nginx `yum install -y nginx`
2. 可能有报错
   ```
   [root@VM-8-14-centos ~]# yum install -y nginx
    Qcloud-8 - AppStream                                                                                                                                                               13 MB/s | 8.4 MB     00:00    
    EPEL for redhat/centos 8 - x86_64                                                                                                                                                 5.1 MB/s |  13 MB     00:02    
    Qcloud-8 - Extras                                                                                                                                                                  62 kB/s |  10 kB     00:00    
    Docker CE Stable - x86_64                                                                                                                                                          12 kB/s |  26 kB     00:02    
    错误：
    问题: package nginx-1:1.14.1-9.module_el8.0.0+184+e34fea82.x86_64 requires nginx-all-modules = 1:1.14.1-9.module_el8.0.0+184+e34fea82, but none of the providers can be installed
      - package nginx-all-modules-1:1.14.1-9.module_el8.0.0+184+e34fea82.noarch requires nginx-mod-http-xslt-filter = 1:1.14.1-9.module_el8.0.0+184+e34fea82, but none of the providers can be installed
      - conflicting requests
      - nothing provides libxslt.so.1()(64bit) needed by nginx-mod-http-xslt-filter-1:1.14.1-9.module_el8.0.0+184+e34fea82.x86_64
      - nothing provides libxslt.so.1(LIBXML2_1.0.11)(64bit) needed by nginx-mod-http-xslt-filter-1:1.14.1-9.module_el8.0.0+184+e34fea82.x86_64
      - nothing provides libxslt.so.1(LIBXML2_1.0.18)(64bit) needed by nginx-mod-http-xslt-filter-1:1.14.1-9.module_el8.0.0+184+e34fea82.x86_64
      - nothing provides libexslt.so.0()(64bit) needed by nginx-mod-http-xslt-filter-1:1.14.1-9.module_el8.0.0+184+e34fea82.x86_64
    (尝试添加 '--skip-broken' 来跳过无法安装的软件包 或 '--nobest' 来不只使用最佳选择的软件包)

   ```
   可知 libxslt 未安装导致的

1. 安装 libxslt:
   1. https://pkgs.org/download/libxslt 找到对应包
   2. `wget https://vault.centos.org/centos/8/BaseOS/x86_64/os/Packages/libxslt-1.1.32-6.el8.x86_64.rpm`
   3. 安装 `rpm -i libxslt-1.1.32-6.el8.x86_64.rpm`

2. 重新 `yum install -y nginx`