
## <a id="register">vim 寄存器</a>
通过下面命令显示所有寄存器内容：

:reg
其中注意两个特殊的寄存器：”* 和 “+。这两个寄存器是和系统相通的，前者关联系统选择缓冲区，后者关联系统剪切板。通过它们可以和其他程序进行数据交换。
若寄存器列表里无”* 或 “+ 寄存器，则可能是由于没有安装vim的图形界面所致。Debian/Ubuntu下可以通过安装vim-gnome解决。

    $ sudo apt-get install vim-gnome

**晋级**         
[Vim 使用进阶：10 种寄存器剖析](http://www.codebelief.com/article/2017/03/vim-advanced-usage-10-registers-analysis/)    
[Vim 复制粘贴探秘](http://www.cnblogs.com/jianyungsun/archive/2011/03/19/1988855.html)   

### [vim 复制](http://www.cnblogs.com/hustcat/articles/1791371.html)        
* vim 常用的粘贴板有"、0、1、2、3、4、5、6、7、8、9、-、.、:、%、/，用 :reg 命令可以查看各个粘贴板里的内容；
* 在vim中简单用y只是复制到“（双引号)和0粘贴板里，同样用p粘贴的也是这个粘贴板里的内容；
* 要将vim的内容复制到某个粘贴板，需要退出编辑模式，进入正常模式后，选择要复制的内容，然后按"Ny（注意带引号）完成复制，其中N为粘贴板号(注意是按一下双引号然后按粘贴板号最后按y)，例如要把内容复制到粘贴板2，选中内容后按"2y就可以了。
> 有两点需要说明一下：    
    1， “号粘贴板（临时粘贴板）比较特殊，直接按y就复制到这个粘贴板中了，直接按p就粘贴这个粘贴板中的内容；      
    2， +号粘贴板是系统粘贴板，用"+y将内容复制到该粘贴板后可以使用Ctrl＋V将其粘贴到其他文档（如firefox、gedit）中，同理，要把在其他地方用Ctrl＋C或右键复制的内容复制到vim中，需要在正常模式下按"+p；