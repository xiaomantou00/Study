# su与su -命令的本质区别  
大部分Linux发行版的默认账户是普通用户，而更改系统文件或者执行某些命令，需要root身份才能进行，这就需要从当前用户切换到root用户。Linux中切换用户的命令是su或su -。前天我在使用useradd这个命令时，才体会到这两者的本质区别。  
如图：  
![su](images/su.jpg "su")  
**su命令和su -命令最大的本质区别就是：前者只是切换了root身份，但Shell环境仍然是普通用户的Shell；而后者连用户和Shell环境一起切换成root身份了。只有切换了Shell环境才不会出现PATH环境变量错误。su切换成root用户以后，pwd一下，发现工作目录仍然是普通用户的工作目录；而用su -命令切换以后，工作目录变成root的工作目录了。用echo $PATH命令看一下su和su -以后的环境变量有何不同。以此类推，要从当前用户切换到其它用户也一样，应该使用su -命令。**  
如图：  
![su](images/su_.PNG "su -") 
**Linux就是这样，有时候配置文件多了或者少了一个空格，服务就运行不了。细节问题一定要注意，这样才能少走弯路！**
