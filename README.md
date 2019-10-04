# Linux-novice-one-click-script-summary
### 减少敲指令的繁琐  (Only Centos , Debian and Ubuntu)(需要Root权限)
### 本文可能非常长,请妥善运用页面搜索功能(Ctrl + F) / 前往 [Wiki](https://github.com/ECIAP/Linux-novice-one-click-script-summary/wiki) 
### 本存储库主要给萌新看 大佬还请手下留情! 如有不对/希望补充 请发布Issues 谢谢
--------------

#### 非常基础的检查 与 一键脚本

* 查看当前Linux系统

  *    lsb_release -a

     * 正常情况下可看见
     
           Distributor ID: Debian 此处Debian可以为其他系统
           
        * 运行此命令出现 -bash: lsb_release: command not found 时 
         
               Debian:apt-get -y install wget
               Ubuntu:apt-get -y install wget
               Centos:yum -y install wget
                           
* 查看VPS虚拟化技术

  * 安装virt-what
   
        Debian:apt -y install virt-what
        Ubuntu:apt -y install virt-what
        Centos:yum -y install virt-what
        
      * 输入virt-what等待输出 输出内容通常为:kvm/openvz/xen/Hyper-v/... 代表意义请自行Google / Baidu / Bing 
      
* 简单查看内存(包含Mem 与 Swap)
  
      free -h
      
     * 等待输出 通常为以下格式
                  
                     total(总量)  used(已占用)free(空闲)  shared  buff/cache   available
      Mem:             1G         0M          1G          0K         0M          0M
      Swap:            2G         0M          2G

* 简单查看硬盘

      df -h
      
     * 等待输出
     
       * 硬盘与实际大小不符时可运行(参考:https://mengniuge.com/vps-resize2fs.html) 
     
             resize2fs /dev/vda1   /dev/vda1替换为你要修正的硬盘
             
* 简单查看磁盘分区

      fdisk -l
      
     * 等待输出
     
* 简单查看CPU
 
      lscpu

    * 等待输出
    
--------------

* 一键添加swap脚本 (from:https://www.moerats.com/archives/722/)
  
       wget https://raw.githubusercontent.com/ECIAP/Linux-novice-one-click-script-summary/master/swap.sh && bash swap.sh
    
     * 运行此脚本出现 -bash: wget: command not found时
    
            Debian:apt-get -y install wget
            Ubuntu:apt-get -y install wget
            Centos:yum -y install wget
      
---------------
    
  * bbr 原版/魔改/plus+锐速 四合一脚本 (from:https://github.com/chiakge/Linux-NetSpeed)
   
          wget -N --no-check-certificate "https://raw.githubusercontent.com/chiakge/Linux-NetSpeed/master/tcp.sh"
          chmod +x tcp.sh
         ./tcp.sh
    
    * 如果运行此脚本出现证书错误时
    
          Debian:   apt-get -y install ca-certificates
          Ubuntu:   apt-get -y install ca-certificates
          Centos:   yum -y install ca-certificates
