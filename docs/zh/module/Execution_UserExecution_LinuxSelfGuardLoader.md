# 自守护免杀ShellcodeLoader(Linux)

生成免杀elf,进程会监控自身,异常退出时会在3秒钟后重新启动

## 操作方法

+ 新建监听(linux)
+ 打开模块,选择对应的监听
+ 运行模块后即会在`文件管理`中生成一个zip文件,包含免杀的elf载荷及对应的C++代码

## 注意事项

模块当前只适配以下载荷:

linux/x86/meterpreter/reverse_tcp

linux/x86/meterpreter/bind_tcp

linux/x64/meterpreter/reverse_tcp

linux/x64/meterpreter/bind_tcp


