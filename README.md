﻿# ZoomMapView

标签（空格分隔）： Android

---
推荐阅读原文：https://www.zybuluo.com/Tyhj/note/942875

最近公司项目需要用到这样一个功能，就是有个地图，点击进入到下一级地图，地图是可以放大缩小的。地图放大缩小后点击区域就有点难判断，其实单单手势的放大缩小图片做到完美也是很难的。

我首先在GitHub上面找到一个完全符合自己要求的：[InDoorSurfaceView](https://leanclub.cn/Screenrecord20170504.mp4)
项目地址：https://github.com/karonl/InDoorSurfaceView
但是其实有一些小问题，比如图片加载前的空白，图片会平移出可视界面，还有内存泄漏问题，反正就是用不了，程序会崩，使用起来也很麻烦。

然后自己仔细想想，这个东西并不难呀，我们先获取图片的大小，图片放大后我们只要知道放大的倍数，和图片X轴和Y轴偏移的距离，点击的时候，我们获取点击点相对于图片的坐标，我们把点击的点的坐标也同样偏移一下，再缩小相同的倍数，得到的就是相当于点击原图的坐标，这样我们只需要在知道我们所标记的区域相当于图片的相对位置，其实也就是用百分比来表示，然后就可以了。

怎么获取相关信息并且做出一个很好的可缩放控件呢，刚好我之前使用过一个非常好的可缩放的ImageView控件：[PinchImageView](https://github.com/boycy815/PinchImageView)，我本来打算根据这个控件来改写，一看源码，我们要的数据它大多数已经实现了，具体就按照之前方法来写，完成后效果也不错。







