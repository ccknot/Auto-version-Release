一、编写目的
    1.手工管理更新文件清单，增加工作量，增加误操作机率。
        a.这个更新清单，其实svn已经自动记录了。
        b.增量打包是可以全自动化的，不需要手工干预。
    2.每月的封板，可以使用分支方式，充分利用已有的自动化版本管理机制，减少人工参与。
        a.每月的封板可直接从svn主干建立分支。
        a.开发对于封板后的bug修改只需提交到分支，现场后续补丁包也只需从分支获取。
        b.当月度版本稳定后，为分支打上月度tag，形成只读版本标记，并将分支合并到主干，
        c.主干、分支、tag，参考：http://panfuy.iteye.com/blog/1278865。
    3.目前对于多人协作后台程序尚无完善的版本打包发布机制。
        a.利用本脚本可实现单命令增量打包，后续此类后台程序可统一交由质管打包发布。
        
二、Ant
    1.本脚本使用apache ant工具执行。
      Ant是一个将软件编译、测试、部署等步骤联系在一起加以自动化的一个工具。具体请自行查询网络。
    2.Ant的安装
        a.Ant是一个java工具，依赖JRE。JRE的相关环境配置，请自行查询网络。
        b.Ant建议版本1.9.3(本脚本是在此版本下编写的，其他版本未测试)，下载地址：
          http://archive.apache.org/dist/ant/binaries/apache-ant-1.9.3-bin.zip
        c.本脚本使用多个第三方插件，插件相关jar见ant_plugins文件夹。
          安装时，须将ant_plugins下的所有jar直接复制到${ANT_HOME}/lib下(不包含文件夹，只复制jar)。

三、脚本配置
    1.本脚本分为适用J2EE和适用J2SE两类，两类脚本分开配置和执行。
    2.每类脚本均包含两个文件，
      build.xml --- 主脚本文件
      build.properties --- 脚本配置文件
    3.所有需要修改的配置均位于build.properties
    4.支持增量打包同一个svn url的不同revision的代码
        示例：
            #------------------------------SVN相关--------------------------------
            #检出svn地址
            new.svn.url=http://xxxx:81/svn/bx_java/Axxxx
            #检出svn修订号
            new.svn.revision=HEAD
            #比对svn地址
            old.svn.url=http://xxxx:81/svn/bx_java/Axxxx
            #比对svn修订号
            old.svn.revision=316483
            
    5.支持增量打包svn 主干和分支（不同url）的相同或不同revision的代码
        示例：
            #------------------------------SVN相关--------------------------------
            #检出svn地址
            new.svn.url=http://xxxx:81/svn/bx_java/Axxxx
            #检出svn修订号
            new.svn.revision=HEAD
            #比对svn地址
            old.svn.url=http://xxxx:81/svn/bx_java/Axxxx_branch2
            #比对svn修订号
            old.svn.revision=HEAD

四.使用说明
    1.在安装了ant之后可以将${ANT_HOME}/bin加入环境变量，方便命令行下使用。如何加入环境变量，请自行搜索网络。
      如不添加环境变量，执行ant相关命令时均需使用绝对路径。（以下命令示例均假设已添加环境变量）
    2.Ant命令行使用(假设build.xml在路径F:\workspace\AutoVR\J2EE下)：
        直接执行：
        ~$> ant -f F:\workspace\AutoVR\J2EE\build.xml svn_log
        在build目录执行：
        ~$> cd F:\workspace\AutoVR\J2EE
        ~$> ant svn_log
    2.两类脚本文件默认target均为增量打包(即package_increment)
      以下列出脚本主要target:
      target                描述            命令示例
      -------------------------------------------------------------------------
      checkout              检出代码        ~$> ant checkout
      package_full	        全量打包	    ~$> ant package_full
      package_increment	    增量打包	    ~$> ant package_increment 或直接ant
      svn_log	            检出SVN Log	    ~$> ant svn_log

五、SVN LOG
    1.每类脚本均支持获取SVN LOG。
    2.命令：F:\workspace\SVNAnt>ant svn_log
    
    获取的svn log样例：
    
    ------------------------------------------------------------------------
    r321075 | zhangzhiqiang | Fri Sep 18 15:48:12 CST 2015Changed paths:
       M /Axxxx/WebRoot/test2.jsp


    【问题单号】：xxx
    【问题描述】：这是为了解决yyy问题
    ------------------------------------------------------------------------
    r320902 | zhangzhiqiang | Fri Sep 18 09:24:16 CST 2015Changed paths:
       M /Axxxx/WebRoot/admin/app/patrol/目录说明


