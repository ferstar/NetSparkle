# NetSparkle

Fork from netsparkle/trunk/NetSparkle commit 105790 from [http://netsparkle.codeplex.com](http://netsparkle.codeplex.com)
--
## ʹ�÷���

1.��build�õ���AppLimit.NetSparkle.Net40.dll��ӽ�Ŀ����Ŀreference��

2.��Ŀ����Ŀ������cs�߼��м������´���:

    /// <summary>
    /// App.xaml �Ľ����߼�
    /// </summary>
    public partial class App : Application
    {
        private Sparkle _sparkle;
        ......
        // ������
        Console.WriteLine("check update...");
        string UpdateUrl = spph.Properties.Settings.Default.DbServer;   // ��ȡserver��ַ
        _sparkle = new Sparkle("ftp://" + UpdateUrl + "/spph/versioninfo.xml"); // ��������ļ���ַ
        //_sparkle.ShowDiagnosticWindow = true;     // ���³�����Դ���,��־��%temp%\spph_update.log
        _sparkle.StartLoop(true, true);
        ......
        // ֹͣ������
        _sparkle.StopLoop();
        ......
    }
3.������������sampleλ��NetSparkle\Extras\Sample Update AppCast\Server Root