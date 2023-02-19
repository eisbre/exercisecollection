## StackOverflow名片模仿

原名片

![](https://picbed-1312285733.cos.ap-beijing.myqcloud.com/img/202301171756845.webp)

模仿名片

![](https://picbed-1312285733.cos.ap-beijing.myqcloud.com/img/202301171756528.webp)

## B站名片模仿

最终效果

![](https://picbed-1312285733.cos.ap-beijing.myqcloud.com/img/202301172225519.webp)

## 刮一刮

实现鼠标左键按下滑动刮开上层图层的刮奖效果。

## 音乐播放器

音乐的唱片封面可以旋转，暂停状态下歌曲信息收起，播放状态显示歌曲信息，支持上一曲，暂停/播放，下一曲，音乐列表，列表右侧的播放/暂停按钮可以用于切换歌曲，暂停和播放。

暂时不支持进度条的定位和拖拽。

[图标网站]([Font Awesome，一套绝佳的图标字体库和CSS框架 (dashgame.com)](https://fontawesome.dashgame.com/))

[在线毛玻璃效果生成器]([Glass Morphism (glassgenerator.netlify.app)](https://glassgenerator.netlify.app/))

![](https://picbed-1312285733.cos.ap-beijing.myqcloud.com/cover/202302172243139.webp)

![](https://picbed-1312285733.cos.ap-beijing.myqcloud.com/cover/202302172243090.webp)

![](https://picbed-1312285733.cos.ap-beijing.myqcloud.com/cover/202302172247734.webp)

## 可控进度条

可以点击控制进度条位置，进而控制播放的位置，演示中使用音乐，视频与之类似。不支持拖拽。

使用jquery获取到进度条的初始位置x坐标，将进度条绑定鼠标点击事件，获取到鼠标的x坐标，与初始位置x坐标求差可得进度条宽度，再使用animate控制css实现进度条的变化。

已知Bug：

* 在获取元素位置信息时，由于移动或者flex布局的影响，会导致定位不准
* 在计算进度条百分比时，如果使用绝对数值，会导致在窗口大小改变后无法正确获取数值，导致显示出错。

![](https://picbed-1312285733.cos.ap-beijing.myqcloud.com/cover/202302181709054.webp)

```css
* {
    margin: 0;
}

.outer {
    width: 400px;
    height: 400px;
    display: flex;
    justify-content: center;
    align-items: center;
}

.ProgressBar {
    width: 300px;
    height: 10px;
    border-radius: 5px;
    color: white;
    backdrop-filter: blur(8px);
    background-color: rgba(10, 175, 230, 0.112);
    border-right: 3px rgba(40, 40, 40, 0.35) solid;
    transition: all .5s;
}

.ProgressBar:hover {
    box-shadow: rgba(0, 0, 0, 0.3) 2px 8px 8px;
}

.ProgressLine {
    width: 0px;
    height: 10px;
    background-color: rgba(44, 43, 49, 0.7);
    border-radius: 5px;
}
```

## 音乐播放器2.0

相对于之前的播放器更改了界面样式，原有的功能逻辑不变。增加了可控进度条，音量调节条。单击声音按钮调出音量条，再次点击关闭。

已知Bug：由于进度条使用相对值进行设置，所以在改变窗口大小后功能依然正常，但是音量条使用了绝对高度值，所以会出现改变窗口大小后取值错误，出现负值，进而导致无法正确设置声音。

![](https://picbed-1312285733.cos.ap-beijing.myqcloud.com/cover/202302191817296.webp)

![](https://picbed-1312285733.cos.ap-beijing.myqcloud.com/cover/202302191817369.webp)

![](https://picbed-1312285733.cos.ap-beijing.myqcloud.com/cover/202302191816767.webp)

