# Proxy

emmm，你好，陌生人。如你所见，这个项目是用于代理的，它改编自[EdgeGo](https://github.com/bannedbook/fanqiang)，我剔除了其中的默认导航以及默认替换用户数据，你也可以自己更改这些东西

下面是改编实例

IF EXIST %~dp0Browser\msedge.exe (
    start msedge.exe  --proxy-server="socks5://127.0.0.1:20808" https://public.sqrx.com/where-am-i  这里是启动的默认设置，我删除了替换用户数据以及首页
) ELSE (
        %SystemRoot%\System32\reg.exe query "HKLM\Software\Microsoft\Windows\CurrentVersion\App Paths\msedge.exe" >nul 2>&1
        IF  not errorlevel 1 (
    start msedge.exe  --proxy-server="socks5://127.0.0.1:20808" https://public.sqrx.com/where-am-i  这里是启动的默认设置，我删除了替换用户数据以及首页
	) else (
                echo Chrome浏览器不存在或没有正确安装，请尝试重新安装Chrome浏览器
                echo 或者采用以下办法：
                echo 右键点桌面的Microsoft Edge图标，再点属性，找到msedge.exe文件的路径，然后打开那个目录，把msedge.exe 连同那个目录下的所有子文件夹和文件，一起拷贝到EdgeGo文件夹下的Browser目录里面，然后重新启动EdgeGo的翻墙脚本。
        )
)

