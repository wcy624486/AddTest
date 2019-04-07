
﻿﻿﻿﻿﻿﻿﻿﻿﻿﻿﻿﻿﻿
## 三员大数据分析平台二开  


航天三员项目根据客户需求，主要有以下几项修改  


- 右键菜单的屏蔽      
- 固定角色“三员-系统管理员”，不能删除......   
- 三员-系统管理员 需要看系统监控数据  
- 日志同步到航天的管理系统（支持两种同步方式）  
- 取消Session过期后进入登录页面，给出提示页面  

## 修改的结构  

目前修改主要集中在三个方面  

- 前端宏：用于控制右键菜单的弹出  
- 配置部分： 设置页加入了日志收集选项（即时、定时）  
- 前端代码： Session过期取消登录页面，右键菜单  
- 插件部分： 控制三员角色不能删除  
- 单独模块： 这是一个单独的日志收集推送工具（Java开发）  

在完成标版系统部署后，完成宏设置，将本目录的 `yonyou` 文件夹替换，自动更换部分 `jsp` 文件，即可完成项目部署。  

## 登录页失效  

> http://localhost:8081/yonyou/vision/index.jsp     
 会显示 `数据分析平台操作失效，请从管理系统重新登录！`      
 如果需要登录，请使用以下两个任何页面均可登录      
 > http://localhost:8081/yonyou/vision/index.jsp?background=1      
 > http://localhost:8081/yonyou/vision/login.jsp?background=1  


2019-04-02 sunny  


## 系统监控权限  
- 给三员-系统管理员添加 系统监控的按钮并赋予权限，将修改后的2个文件替换即可  
- 修改的2个文件：sysmonitor.jsp、BannerView.js.patch  
- 文件起到的作用：  
   sysmonitor.jsp：授予三员-系统管理员 系统监控的操作权限  
   BannerView.js.patch：给三员-系统管理员添加 “系统监控”的前台按钮；所有用户都屏蔽掉 “我的设置”、“关于”、“注销”   
   
- 所修改文件的路径：  
 sysmonitor.jsp ：位于`yonyou.war`，`/vision`目录下  
 BannerView.js.patch ：位于 `UFLogo`插件包，`/vision/js/bof/baseajax/common`目录下  

2019-04-03 wucy  




































