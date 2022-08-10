# IDA_sdk_tools

ida77_sdk_tools 来自：https://bbs.pediy.com/thread-271101.htm

ida8.0_sdk_tools 来自: https://bbs.pediy.com/thread-273986.htm

# IDA pro
IDA PRO 7.7.220118 (SP1) (x86, x64, ARM64) By Dr.FarFar
> https://www.dr-farfar.com/hex-rays-ida-professional-advanced-and-decompiler/
> 
> https://www93.zippyshare.com/v/UgQ4pdA8/file.html
> 
> https://pan.baidu.com/s/1uQvdu08cpxuymWAePVtI-A  提取码：e00w 

IDA 7.7 sp1 Think-Cell 泄露版 + 激活文件，飘云阁分享
> 原文件下载：https://pan.baidu.com/s/18JVkgOkz3nhS7nLX6dhRvw 提取码：0321 

Hex-Rays IDA Pro v7.6 SP1 with all Decompilers - Restored Version
> 链接：https://pan.baidu.com/s/1WXwxeACnVOOTT8xO1phktA 提取码：woo4 
> 

www.52pojie.cn IDA 包含 5.x 、6.x 、7.x 
> 链接: https://pan.baidu.com/s/1bdBhVTBYMk0lNIOtCxIjPw 提取码: w28g


# IDA 绿化设置
首先安装 python 并将 python 移动到 IDA 的目录，然后运行下列脚本。其中脚本中 PYTHON_BASE 根据自己的 python 目录进行更改即可。

```bat
rem 获取 python 环境
set PATH=%~dp0
set PYTHON_BASE=%PATH%Python39
set PYTHON_PATH=%PYTHON_BASE%\python.exe
set PYTHONW_PATH=%PYTHON_BASE%\pythonw.exe
set PYTHON_LIB=%PYTHON_BASE%\Lib
set PYTHON_DLL=%PYTHON_BASE%\DLLs

rem  设置 python 环境
@reg add HKEY_CURRENT_USER\SOFTWARE\Python\PythonCore\3.9\InstallPath /t REG_SZ /d %PYTHON_BASE% /f
@reg add HKEY_CURRENT_USER\SOFTWARE\Python\PythonCore\3.9\InstallPath /v "ExecutablePath" /t REG_SZ /d %PYTHON_PATH% /f
@reg add HKEY_CURRENT_USER\SOFTWARE\Python\PythonCore\3.9\InstallPath /v "WindowedExecutablePath" /t REG_SZ /d %PYTHONW_PATH% /f
@reg add HKEY_CURRENT_USER\SOFTWARE\Python\PythonCore\3.9\PythonPath /d %PYTHON_LIB%;%PYTHON_DLL% /f

rem  设置 Python3TargetDLL 环境
set PYTHON39_DLL=%PYTHON_BASE%\python39.dll
reg.exe add "HKCU\SOFTWARE\Hex-Rays\IDA" /v "Python3TargetDLL" /t REG_SZ /d %PYTHON39_DLL% /f

rem  禁止自动更新
reg.exe add "HKCU\SOFTWARE\Hex-Rays\IDA" /v "AutoCheckUpdates" /t REG_DWORD /d 0 /f
reg.exe add "HKCU\SOFTWARE\Hex-Rays\IDA" /v "AutoRequestUpdates" /t REG_DWORD /d 0 /f
reg.exe add "HKCU\SOFTWARE\Hex-Rays\IDA" /v "AutoUseLumina" /t REG_DWORD /d 0 /f

echo "Greening is completed, please press any key to exit"
pause
```
参考：http://scz.617.cn:8/python/202011182246.txt

