# NetSparkle

Fork from netsparkle/trunk/NetSparkle commit 105790 from [http://netsparkle.codeplex.com](http://netsparkle.codeplex.com)
--
## 使用方法

1.将build得到的AppLimit.NetSparkle.Net40.dll添加进目标项目reference中

2.在目标项目主窗口cs逻辑中加入如下代码:

    /// <summary>
    /// App.xaml 的交互逻辑
    /// </summary>
    public partial class App : Application
    {
        private Sparkle _sparkle;
        ......
        // 检查更新
        Console.WriteLine("check update...");
        string UpdateUrl = spph.Properties.Settings.Default.DbServer;   // 获取server地址
        _sparkle = new Sparkle("ftp://" + UpdateUrl + "/spph/versioninfo.xml"); // 传入更新文件地址
        //_sparkle.ShowDiagnosticWindow = true;     // 更新程序调试窗口,日志在%temp%\spph_update.log
        _sparkle.StartLoop(true, true);
        ......
        // 停止检测更新
        _sparkle.StopLoop();
        ......
    }
3.服务器端配置sample位于NetSparkle\Extras\Sample Update AppCast\Server Root