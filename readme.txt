LOL官方外挂指南（手动狗头）   

初衷：
最开始只是因为现在找工作闲的发慌，想再做个数据项目练练手充充门面，然后想到LOL那么多英雄有着很多数据可以用，本S5老玩家DNA动了，就去尝试搜了一下，发现riot对开发者很友好，很轻松就下载到了资源包，看了一圈发现除了常规的英雄title，介绍和装备的情况之外，还有官方的allytips和enemytips，想起来原来看登入界面时候的小知识看的不亦乐乎，又想起来原来一起打游戏的人，就决定做一个网站整理一下，也缅怀一下这段岁月。

You may want to know:
1.我最开始学做网页的时候用的是dreamweaver和Visual studio，现在电脑换了也没再装，仗着找到了合适的网站模板之后，索性全程用记事本修改的网页文件哈哈哈。
2.截至这个项目完成的时候，英雄联盟已经推出了158个英雄，最新的renata glasc 烈娜塔· 戈拉斯克 虽然预告片和技能介绍已经出来了但是还没有正式上线，不过资源包里已经有各方面的介绍了，所以也很荣幸，加入到了这个网站里面，合计159位英雄。
3.其中，只有144位英雄有完整的官方编写的allytips和enemytips，阿克尚没有enemytip, 剩下14位两者都没有，所以我就按照自己的体验，手动补充了一些，就当个彩蛋给大家看看吧。
4.从原始json文件里提取关键信息，我用的是jupter python的regular expression正则表达式批量操作的，提取出了id,name,title,allytips和enemytips五个list,然后再用Python的for循环，批量制作了159位英雄介绍的html代码。
5.官方资料包里包含了所有英雄的所有皮肤的图片。来是想为了减小项目尺寸只保留最小尺寸的那张，然后发现最大最小相差的一般就差几k无伤大雅，就转而为了辨识度只保留原画了。也是用的python，去批量删除照片，又因为很多图片名称里有0（例如皮肤很多的英雄往往有第10张）而只有原画名称里有_0,所以关键词的选择用了if '_0' not in tilename:的语句，完成了照片的批量操作。
6.整个网站的立项，找资料，编代码，搭建，调试，运行，测试，花了一整个下午。
7.建议拳头尽快和font awesome合作出一个专属图标，可以是拳头可以是lol小地图，完全是win-win嘛。

技术步骤：
1.riot官网下载最新资料文件 https://developer.riotgames.com/docs/lol
2.Json文件转化为txt文件方便读取
3.正则表达式提取关键句（id,name,title,allytips和enemytips），清洗并组成list
4.找合适的网站模板
5.python批量提取英雄头像和原图备用
6.python批量制造html代码
7.编辑网站内容
8.上传github并deploy网页

遇到问题：
1.python编码的时候  输入\一个是\\ 两个也是\\ 然后发现文件路径里就算两个也无所谓 windows可以试别
2.正则表达式里的？greedy和ungreedy问题浪费了我三个小时😀giao
3.提取学名的时候，用name发现皮肤的类别也是name会重复，所以正则表达式向前延伸了加上了key作为区分


感谢html5up提供好看的网站模板 thanks to html5up for the free and wonderful website template.
感谢南京大学的大壮老师在coursera上的《用python玩转数据》给我启蒙，课程免费，干货很多，推荐大家感兴趣都去听一听 https://www.coursera.org/learn/hipython?
感谢youtube上的Alex The Analyst建议我做个portfolio，才有了这个网站
感谢雷霆，米兰，翠花，壮壮原来一起和我打游戏。
