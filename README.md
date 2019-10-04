# Linux-novice-one-click-script-summary
## 减少敲指令的繁琐  (Only Centos Debian Ubuntu)(Requires root privileges)

* 查看当前Linux系统

  *    lsb_release -a

     * 正常情况下可看见
     
           Distributor ID: Debian 此处Debian可以为其他系统
           
        * 运行此命令出现 -bash: lsb_release: command not found 时 
         
               Debian:apt-get -y install wget
               Ubuntu:apt-get -y install wget
               Centos:yum -y install wget
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
