### USB Install CentOS 7
1. 首先从官方网站下载CentOS 7，版本为 [CentOS-7-x86_64-DVD-1511.iso](http://mirrors.aliyun.com/centos/7/isos/x86_64/CentOS-7-x86_64-DVD-1511.iso)
2. 下载安装[UltraISO](http://www.ezbsystems.com/ultraiso/download.htm)
3. 使用UltraISO写镜像到U盘  
   **注意**：U盘容量最好>=8G， 因为镜像就4.33G
   * UltraISO试用即可，参考如下：  
   **Step1**  
   ![Step 1](file:///Users/jason/Documents/centos001.jpg)  
   **Step2**  
   ![Step 1](file:///Users/jason/Documents/centos002.jpg)  
   关于选项**隐藏驱动分区** 默认 **无** 即可，写入时间较长，慢慢等待
4. BIOS设为U盘启动  
   设置U盘启动过程中，貌似不是UEFI（我也不懂），参考别人教程打开BIOS CSM（Compatibility Support Module 即兼容性支持模块); 重启。
   如果能够进入CentOS 7安装界面就不需要打开CSM，供参考。
5. 主要需要修改安装镜像所在位置，即U盘，修改包含以下两步    
   1） vmlinuz initrd=initrd.img linux dd quiet （查看U盘设备符号，然后重启）  
   2） vmlinuz initrd=initrd.img inst.stage2=**hd:/dev/sdc4** quiet（镜像位置设置为U盘，再重启）  
   加粗的为自己的U盘设备标识符，偷个懒，本来也是参考该文作者的，链接见http://www.augsky.com/599.html
   
完成第5步后就能进入真正的安装界面了。