һ����дĿ��
    1.�ֹ���������ļ��嵥�����ӹ�������������������ʡ�
        a.��������嵥����ʵsvn�Ѿ��Զ���¼�ˡ�
        b.��������ǿ���ȫ�Զ����ģ�����Ҫ�ֹ���Ԥ��
    2.ÿ�µķ�壬����ʹ�÷�֧��ʽ������������е��Զ����汾������ƣ������˹����롣
        a.ÿ�µķ���ֱ�Ӵ�svn���ɽ�����֧��
        a.�������ڷ����bug�޸�ֻ���ύ����֧���ֳ�����������Ҳֻ��ӷ�֧��ȡ��
        b.���¶Ȱ汾�ȶ���Ϊ��֧�����¶�tag���γ�ֻ���汾��ǣ�������֧�ϲ������ɣ�
        c.���ɡ���֧��tag���ο���http://panfuy.iteye.com/blog/1278865��
    3.Ŀǰ���ڶ���Э����̨�����������Ƶİ汾����������ơ�
        a.���ñ��ű���ʵ�ֵ�����������������������̨�����ͳһ�����ʹܴ��������
        
����Ant
    1.���ű�ʹ��apache ant����ִ�С�
      Ant��һ����������롢���ԡ�����Ȳ�����ϵ��һ������Զ�����һ�����ߡ����������в�ѯ���硣
    2.Ant�İ�װ
        a.Ant��һ��java���ߣ�����JRE��JRE����ػ������ã������в�ѯ���硣
        b.Ant����汾1.9.3(���ű����ڴ˰汾�±�д�ģ������汾δ����)�����ص�ַ��
          http://archive.apache.org/dist/ant/binaries/apache-ant-1.9.3-bin.zip
        c.���ű�ʹ�ö�������������������jar��ant_plugins�ļ��С�
          ��װʱ���뽫ant_plugins�µ�����jarֱ�Ӹ��Ƶ�${ANT_HOME}/lib��(�������ļ��У�ֻ����jar)��

�����ű�����
    1.���ű���Ϊ����J2EE������J2SE���࣬����ű��ֿ����ú�ִ�С�
    2.ÿ��ű������������ļ���
      build.xml --- ���ű��ļ�
      build.properties --- �ű������ļ�
    3.������Ҫ�޸ĵ����þ�λ��build.properties
    4.֧���������ͬһ��svn url�Ĳ�ͬrevision�Ĵ���
        ʾ����
            #------------------------------SVN���--------------------------------
            #���svn��ַ
            new.svn.url=http://xxxx:81/svn/bx_java/Axxxx
            #���svn�޶���
            new.svn.revision=HEAD
            #�ȶ�svn��ַ
            old.svn.url=http://xxxx:81/svn/bx_java/Axxxx
            #�ȶ�svn�޶���
            old.svn.revision=316483
            
    5.֧���������svn ���ɺͷ�֧����ͬurl������ͬ��ͬrevision�Ĵ���
        ʾ����
            #------------------------------SVN���--------------------------------
            #���svn��ַ
            new.svn.url=http://xxxx:81/svn/bx_java/Axxxx
            #���svn�޶���
            new.svn.revision=HEAD
            #�ȶ�svn��ַ
            old.svn.url=http://xxxx:81/svn/bx_java/Axxxx_branch2
            #�ȶ�svn�޶���
            old.svn.revision=HEAD

��.ʹ��˵��
    1.�ڰ�װ��ant֮����Խ�${ANT_HOME}/bin���뻷��������������������ʹ�á���μ��뻷���������������������硣
      �粻��ӻ���������ִ��ant�������ʱ����ʹ�þ���·��������������ʾ������������ӻ���������
    2.Ant������ʹ��(����build.xml��·��F:\workspace\AutoVR\J2EE��)��
        ֱ��ִ�У�
        ~$> ant -f F:\workspace\AutoVR\J2EE\build.xml svn_log
        ��buildĿ¼ִ�У�
        ~$> cd F:\workspace\AutoVR\J2EE
        ~$> ant svn_log
    2.����ű��ļ�Ĭ��target��Ϊ�������(��package_increment)
      �����г��ű���Ҫtarget:
      target                ����            ����ʾ��
      -------------------------------------------------------------------------
      checkout              �������        ~$> ant checkout
      package_full	        ȫ�����	    ~$> ant package_full
      package_increment	    �������	    ~$> ant package_increment ��ֱ��ant
      svn_log	            ���SVN Log	    ~$> ant svn_log

�塢SVN LOG
    1.ÿ��ű���֧�ֻ�ȡSVN LOG��
    2.���F:\workspace\SVNAnt>ant svn_log
    
    ��ȡ��svn log������
    
    ------------------------------------------------------------------------
    r321075 | zhangzhiqiang | Fri Sep 18 15:48:12 CST 2015Changed paths:
       M /Axxxx/WebRoot/test2.jsp


    �����ⵥ�š���xxx
    ������������������Ϊ�˽��yyy����
    ------------------------------------------------------------------------
    r320902 | zhangzhiqiang | Fri Sep 18 09:24:16 CST 2015Changed paths:
       M /Axxxx/WebRoot/admin/app/patrol/Ŀ¼˵��


