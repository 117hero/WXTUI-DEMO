## h5puzzle.js的说明
#### 1. 在当前页面对h5puzzle.js的引入
```
const Puzzle = require("./h5puzzle.js");
```
#### 2. Puzzle的使用
```
Page({
  data: {
    imgPoints: [],
    imgArr: ['../../src/images/quanyecha.jpg', '../../src/images/haidao.jpg', '../../src/images/mingren1.jpg', '../../src/images/qilongzhu1.jpg','../../src/images/quanye.jpg'],
    imgUrl: '../../src/images/quanyecha.jpg',
    levelArr: [{id: 2,text: '弱智'},{id: 3,text: '简单'},{id: 4,text: '普通'},{id: 5,text: '困难'},{id: 6,text: '变态'},{id: 7,text: '无语'},{id: 8,text: '天才'},{id: 9,text: '疯子'},{id: 10,text: '想死'},{id: 11,text: '已死'}],
    WIDTH: 0,
    HEIGHT: 0,
    width: 0,
    height: 0,
    status: false,
    trans: 0,
    currentX: 0,
    currentY: 0,
    currentPX: 0,
    currentPY: 0,
    type0: 4
  },
  onReady(){
    let _this = this;
    
    new Puzzle(this);
  },
  getType(e){
    this.setData({
      trans: -this.data.WIDTH,
      type0: e.currentTarget.dataset.type
    })
    this.puzzle = new Puzzle(this, {
      type: e.currentTarget.dataset.type
    })
  },
  getUrl(e){
    this.setData({
      trans: -this.data.WIDTH * 2,
      imgUrl: e.currentTarget.dataset.url
    })
  }
})
```
#### 参数说明
> type: 拼图的矩阵数

## luck.js的说明
#### 1. 在当前页面对luck.js的引入
```
const Luck = require("./luck.js");
```
#### 2. Luck的使用

```
Page({
  data:{
    width: '',
    height: ''
  },
  onLoad(){
    this.luck = new Luck(this,{
      canvasId: 'luck',
      width: 300,
      height: 150,
      maskColor: '#dddddd',
      size: 10,
      scale: 0.2
    });
  }
})
```
#### 参数说明

>1. canvasId: 刮刮乐canvas的canvas-id值
>2. width: 刮刮乐canvas的宽度
>3. height: 刮刮乐canvas的高度
>4. maskColor: 刮刮乐canvas的涂层颜色
>5. size: 刮去部分的半径
>6. scale: 刮去部分占整体的百分比，大于就去掉涂层

## h5lock.js的说明
#### 1. 在当前页面对h5lock.js的引入
```
const Locker = require("./h5lock.js");
```
#### 2. Luck的使用

```
Page({
  data: {
    title: '请绘制您的图形密码'
  },
  onReady(){
    this.lock = new Locker(this,{
      id: 'canvas',
      cleColor:'rgba(0,136,204,1)',
      cleCenterColor:'rgba(0,136,204,1)',
      chooseType: 3
    });
  },
  resetPwd() {
    this.lock.updatePassword();
  }
})
```
#### 参数说明

>1. id: 手势锁canvas的canvas-id值
>2. width: 手势锁canvas的宽度
>3. height: 手势锁canvas的高度
>4. cleColor: 手势锁canvas的锁圆颜色
>5. cleCenterColor: 手势锁canvas的解锁路线颜色
>6. chooseType: 手势锁的矩阵

## TUI微信小程序DEMO
1. accordion（折叠面板）

> 采用微信小程序的view组件和WXSS配合，通过判断状态值，确定激活的状态栏实现折叠面板。

2. actionsheet（操作表）

> 采用微信小程序的原生API接口wx.showActionSheet(OBJECT)，唤醒操作列表，然后对操作列表进行配置。

3. button（按钮）

> 采用微信小程序的button原生组件实现。

4. cardview（卡片视图）

> 文字配合图片的一种展现形式，采用view和text组件实现。

5. checkbox（复选框）

> 采用checkbox组件实现。

6. radio（单选框）

> 采用radio组件实现。

7. date time（日期时间）

> 采用picker组件，然后自定义时间数据实现。

8. dialog（消息框）

> 调用微信小程序原生API接口showToast和showModal实现，当然部分不全面的，可以采用自定义样式完成。

9. gallery slider（图片轮播）

> 采用swiper组件实现图片的轮播。

10. gallery table（图文表格）

> 采用微信小程序的原生组件view利用display：table样式布局。

11. grid（9宫格）

> 采用微信小程序的原生组件view利用display：table样式布局。

12. icon（图标）

> 配合阿里巴巴矢量图标库实现的外部图库引入使用。

13. list（列表）

> 单纯的文字列表，采用view组件实现。

14. media list（图文列表）

> 采用图片浮动，剩余部分文字的样式，overflow实现。

15. nav bar（导航栏）

> 导航栏透明渐变。

16. number box（数字输入框）

> 购物车商品加减样式的实现。

17. off canvas（侧滑导航）

> 隐藏导航的滑出样式，实现原理是保持主题不动，导航滑出，同时给主题添加遮罩层。

18. picker（选择器）

> 多级联动的选择器，定义个性数据，采用picker组件进行展示。

19. progress bar（进度条）

> 采用原生的progress组件，设置不同的属性，实现的炫彩效果。

20. pull to refresh（下拉刷新和上拉加载更多）

> 调用onPullDownRefresh方法和onReachBottom方法实现下拉刷新和上拉加载更多。

21. range（滑块）

> slider组件实现滑块滑动。

22. switch（开关）

> switch组件实现开关。

23. tab bar（选项卡）

> WXSS控制样式，JS判断当前展示的项目

24. indexed list（索引列表）

> scroll-view组件配合view组件实现，主要是采用了scroll-view组件的滚动以及定位。

25. locker（手势图案锁屏）

> 自定义插件lock，通过canvas实现手势图案锁屏。

26. image viewer（图片预览）

> 调用原生接口previewImage，实现图片的预览。

27. scroll nav （YDUI的滚动导航）

> scroll-view组件实现，布局和样式不同。

28. scroll tab （YDUI的滚动选项卡）

> scroll-view组件实现，布局和样式不同。

29. map （地图）

> map组件配合高德地图的接口实现，比原生接口更快。

30. loading （自定义加载图标）

> 自定义各种加载图标，适用于各个场景。

31. luckdraw（刮刮乐抽奖）

> 制作luck插件，实现刮刮乐抽奖。

32. puzzle（拼图游戏）

> 制作puzzle插件，实现拖拽拼图游戏。

33. countDown (团购或者秒杀的批量倒计时)

> 利用微信小程序的变量属性，将活动结束时间提取，做批量处理渲染，实现批量倒计时。