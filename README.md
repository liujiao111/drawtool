文章地址：https://blog.csdn.net/qq_34464926/article/details/85194029
###  简介
当我们需要POI边界数据时，我们第一想法是爬取高德或者百度地图提供的数据，不过由于它们的接口都有反爬限制措施，爬取边界坐标并不是一件容易的事情，并且即便能爬，也有些POI并没有边界坐标数据，这时候只能自己手动圈选需要的范围，然后获取到边界坐标。这个工作一般情况下是使用ARCGIS等工具来完成，不过由于ARCGIS比较庞大，如果不是大规模圈选的话就没必要使用ARCGIS了，因此就想着能否提供一个比较轻量简便的工具来绘制多边形，并且能获取到对应的边界坐标数据。应此需求，特意趁工作之余写了一个浏览器端使用的多边形圈选工具，提供的功能有：根据城市名进行定位、POI搜索、多边形批量圈选并批量导出为文本数据。该工具基于HTML、Javascript开发，使用浏览器打开代码文件即可使用。
目前样式比较丑，暂且用着吧，后面我找个前端同事帮忙调下，或者有帮忙调的请联系我。
### 代码地址：https://github.com/liujiao111/drawtool.git
### 使用方法
- 如果电脑安装了git，可以直接使用命令
`git clone https://github.com/liujiao111/drawtool.git`
将代码下载到本地，进入`drawtool`文件夹，在浏览器打开文件`draw.html`即可（推荐使用谷歌浏览器）；
- 如果没有安装git,可以在代码地址中进行如下操作即可下载代码文件![在这里插入图片描述](https://img-blog.csdnimg.cn/20181222082827964.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM0NDY0OTI2,size_16,color_FFFFFF,t_70)
- 浏览器打开后，右上角可以搜索需要的城市以及POI名称，左上角是圈选工具拦，左下角是圈选的坐标展示区
![在这里插入图片描述](https://img-blog.csdnimg.cn/2018122208360697.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM0NDY0OTI2,size_16,color_FFFFFF,t_70)
- 如果需要批量圈选多边形并且批量导出为txt文件，必须先点击左下角的`开始作业`按钮，然后在点右上角的多边形工具进行圈选，圈选一个多边形后双击结束（会自动闭合），结束后再点一次多边形按钮开始下一个圈选，批量圈选结束后，点击`结束作业，并导出`按钮即可将批量圈选的多边形坐标数据在浏览器导出为txt文件。点击`移除上一个`按钮则会移除最近圈选的多边形，`全部移除`则移除所有已圈选的多边形。
- 打开的txt文件如下：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181222083501663.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM0NDY0OTI2,size_16,color_FFFFFF,t_70)
第三行开始，前面的0和1等等是一个多边形坐标数据的索引，多边形坐标由多个点坐标组成，前面是经度，后面是纬度，坐标为WGS84坐标系，如果需要修改txt文本格式，在代码中85行左右`overlaycomplete`方法中进行修改，也可以联系我帮忙。

最后附上qq：`917961898`,一如既往地义务帮忙，希望加我的时候能备注下，谢谢。
