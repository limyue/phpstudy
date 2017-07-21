# phpstudy
***************************************************
apache环境配置：
1.首先下载 64位Apache2.4.3版本下载地址：http://www.apachelounge.com/download/ 到某一文件夹
（我以D:apache2为例，将下载的压缩包解压到当前文件夹，名为Apache24）
2.打开Apache24\conf下httpd.conf 文件，用记事本打开即可。赋值到sublime中，找到相应行并修改，之再复制到记事本中保存即可
或者用vi 打开 httpd.conf文件修改
（1）第37行  ServerRoot "c:/Apache24"  改为  ServerRoot "D:\apache2\Apache24"
  //Apache程序的位置。
（2）第222行  找到  #ServerName www.example.com:80这行  改为  （去掉前面的#号）  ServerName 127.0.0.1:80
  //改主机名
（3）第246行  DocumentRoot "c:/Apache24/htdocs"  改为  DocumentRoot "d:/apache2/Apache24/htdocs"
  //网站的根目录
（4）第280行  DirectoryIndex index.html  改为  DirectoryIndex index.html index.php index.htm  
  //支持更多的默认页
（5）第363行  ScriptAlias /cgi-bin/ "c:/Apache24/cgi-bin/"  改为   ScriptAlias /cgi-bin/ "d:/apache2/Apache24/cgi-bin/"
3.验证，启动Apache。
win+r，输入cmd，打开命令提示符。
d:   回车
cd apache\ Apache24\bin   回车
httpd   回车
如果httpd.conf配置正确的话，输入httpd回车后是没有任何提示的。

*(提示：VCRUNTIME140.DLL丢失的问题解决，缺少Visual Studio 2015所建立的C++应用的必要组件
下载地址
http://download.microsoft.com/download/9/E/1/9E1FA77A-9E95-4F3D-8BE1-4D2D0C947BA2/enu_INREL/vcredistd14x64/vc_redist.x64.exe
安装即可解决问题）*

4.测试。
你可以把Apache24\htdocs目录下的index.html放到D:\www目录下，用浏览器访问会出现“It works”那么就说明apache已经正确安装了。

注意：不能关掉这个命令窗口，否则apache会关闭的。

5.加入为windows的系统服务，让Apache自启动。
用管理员权限运行cmd
这里加入服务的命令为：httpd.exe -k install -n "servicename"

servicename为Apache在windows的服务中的名字。例如：httpd.exe -k install -n "Apache24"

参考网站：http://blog.csdn.net/jiangzeyun/article/details/41676639
