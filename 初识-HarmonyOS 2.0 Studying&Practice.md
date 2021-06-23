# 初识-HarmonyOS 2.0 Studying&Practice

## 一、introduction&install

### (一)2021年5月31日  

> [HarmonyOS2.0鸿蒙系统应用开发环境搭建](https://www.bilibili.com/video/BV1eA411E7aM/?spm_id_from=333.788.recommend_more_video.1)

>[鸿蒙0S 2.0 最全面教学](https://www.bilibili.com/video/BV1uT4y1w7DZ)

>[HarmonyOS2.0鸿蒙系统应用开发环境搭建](https://www.bilibili.com/video/BV1eA411E7aM)

>[Windows环境搭建视频教程](https://developer.harmonyos.com/cn/docs/documentation/doc-guides/software_install-0000001053582415)

>[真有那么香吗？HarmonyOS全家桶体验来了！](https://www.bilibili.com/video/BV17h411e7Na?from=search&seid=14610139818384178704)

### (二)学习总结

> 1. 通过B站和官网 下载HarmonyOS的ide，devecostudio-windows-tool-2.1.0.303（ds），配置环境（包括node.js.org的js包，与需要的SDK），运行第一个工程（hello world）
>
> 2. 构思组件学习鸿蒙的几个步骤：一、通过B站途途IT学堂，跟着先行者初步了解鸿蒙并跟着做简单的演示，同时辅佐官方的DS说明书进行操作。二、通过充分学习Ability进行拓展。三、通过软件或Up主进一步请教如何学习和学习什么的问题。

> 地址：
>
> [devecostudio-windows-tool-2.1.0.303.zip](C:\Users\iamda\Desktop\考研\资源\学习软件安装包)
>
> [node-v14.17.0-x86.msi](C:\Users\iamda\Desktop\考研\资源\学习软件安装包)

### (三)心得分享

>  合格的程序员一定具备高敏的技术嗅觉，HarmonyOS是面相全景的分布式微内核的操作系统，即将成为第三大移动应用生态。根据我国十四五规划和纲要的顶层规划，为基本实现"新四化"，互联网、大数据、人工智能和实体经济必将深度融合。弯道超车，学好技术，宜早不宜迟。熟练使用HarmonyOS平台势在必行，精通java与js语言势在必行！

## 二、初识鸿蒙-HarmonyOS 2.0 途途IT学堂

* ==主要对entry>src>main>slice>MainAbilitySlice进行操作,MainAbilitySlice在第一课中会讲到，这是一个显示UI框架的类。AbilitySlice通过setUIContent（）为界面设置布局。==
* entry>src>main>resources>base>graphic(图解)
* entry>src>main>resources>base>layout(布局)
* entry>src>main>resources>base>media (多媒体)
* entry>src>main>resources>base>element (字符串)
* [Ability与AbilitySlice](https://blog.csdn.net/Calvin_zhou/article/details/111854791)
* 想要使用某组件或者想对某组件使用某种方法，惯例在Slice里面创建向相应Slice，然后在Layout里面用xml进行具体设定

### 第一章鸿蒙UI框架

#### （一）[第01课 HarmonyOS 2.0 鸿蒙UI框架：组件和布局](https://www.bilibili.com/video/BV1wt4y1q7jn)

>#### 时间：2021年6月6日17:11:07
>
>#### B站Up主 途途IT课堂
>
>#### 学习总结 
>
>> ##### 1.组件与布局
>>
>> >1.0介绍组件与布局
>> >
>> >* 关系：树状结构，唯一root结点，组件有唯一容器 
>> >
>> >![](C:\Users\iamda\Desktop\考研\资源\图片\组件与布局的关系.png)
>> >
>> >* Component 组件（文本 按钮 图片 列表）
>> >
>> >* ComponentContainer 布局-容器 （DirectionalLayout 与DependentLayout）
>> >
>> >* LayoutConfig-修改参数 
>> >
>> >* MainAbilitySlice-显示UI界面的
>> >
>> >1.1使用组件和布局开发
>> >
>> >* HarmonyOS提供了Ability和AbilitySlice两个基础类。有界面的Ability绑定了系统的Window进行UI展示，且具有生命周期。AbilitySlice主要用于承载Ability的具体逻辑实现和界面UI，是应用显示、运转和跳转的最小单元。AbilitySlice通过setUIContent（）为界面设置布局。
>> >
>> >* setUIContent（ComponententContainer root）-接口声明
>> >
>> >* 两种方法创建布局（通过代码、通过XML） 
>> >
>> >* 内含很多通过XML去实现的代码，写一个页面类似（HTML）
>> >
>> >
#### （二）[第02课 HarmonyOS 2.0 鸿蒙UI框架：DirectionLayout布局](https://www.bilibili.com/video/BV1xf4y1D7gv/?spm_id_from=333.788.recommend_more_video.-1)

>#### 时间：2021年6月6日21:15:11
>
>#### B站Up主 途途IT课堂
>
>#### 学习总结 
>
>>##### 1.常用组件
>>
>>1.0组件分类
>>
>>![](C:\Users\iamda\Desktop\考研\资源\图片\组件分类.png)
>>
>>1.1布局类组件
>>
>>1.1.1DirectionalLayout-线性布局
>>
>>> * 一组Component水平或者垂直排列
>>>
>>> * DirectionalLayout不会自动换行，超过部分不会显示
>>>
>>>   | 属性名称         |                        功能叙述                        |
>>>   | :--------------- | :----------------------------------------------------: |
>>>   | orientation      | 排列方式：设定方向垂直（vertical）、水平（horizontal） |
>>>   | layout_alignment |          对齐方式：控制自身在布局中的对齐方式          |
>>>
>>>   * 对齐方式与排列方式一致时，对齐方式不会生效，
>>>
>>>     | 参数              | 作用                 | 可搭配排列方式      |
>>>     | ----------------- | -------------------- | ------------------- |
>>>     | left              | 左对齐               | vertical            |
>>>     | right             | 右对齐               | vertical            |
>>>     | top               | 顶部对齐             | horizontal          |
>>>     | bottom            | 底部对齐             | horizontal          |
>>>     | horizontal_center | 水平方向居中         | vertical            |
>>>     | vertical_center   | 垂直方向居中         | horizontal          |
>>>     | center            | 水平和垂直方向都居中 | vertical/horizontal |
>>>
>>>     * 权重（weight，父布局可分配宽度=父布局宽度-所有子组件width之和；组件宽度=组件weight/所有组件weight之和*父布局可分配宽度，实际操作中，建议使用==width=0==来按比例分配父布局的宽度。）

#### （三）[第03课 HarmonyOS 2.0 鸿蒙UI框架：DependentLayout布局](https://www.bilibili.com/video/BV1b54y117uP/?spm_id_from=autoNext)

>>#### 时间：2021年6月6日21:57:59
>>
>>#### B站Up主 途途IT课堂
>>
>>#### 学习总结 (接着第二课的常用组件)
>>
>>1.1.2DependentLatout-相对布局
>>
>>* 是相对于其他同级组件或者父组件的位置进行布局
>>
>>* 记得给子组件id、有关DirectionalLayout的不能用
>>
>>  | （同级）位置布局 | 描述               |
>>  | ---------------- | ------------------ |
>>  | above            | 处于同级组件上侧   |
>>  | below            | 处于同级组件下侧   |
>>  | start_of         | 处于同级组件起始侧 |
>>  | end_of           | 处于同级组件结束侧 |
>>  | left_of          | 处于同级组件的左侧 |
>>  | right_of         | 处于同级组件的右侧 |
>>
>>  * ```text
>>    ohos:below="$id:btn_one"
>>    ```
>>
>>  | （父组件）位置布置  | 描述             |
>>  | ------------------- | ---------------- |
>>  | align_parent_left   | 处于父组件左侧   |
>>  | align_parent_right  | 处于父组件右侧   |
>>  | align_parent_start  | 处于父组件起始侧 |
>>  | align_parent_end    | 处于父组件结束侧 |
>>  | align_parent_top    | 处于父组件上侧   |
>>  | align_parent_bottom | 处于父组件下侧   |
>>  | center_in_parent    | 处于父组件中间   |
>>
>>  * ``` text
>>    align_parent_right="ture"//可以多个叠加
>>    ```

（四）[第04课 HarmonyOS 2.0 鸿蒙UI框架：TableLayout布局](https://www.bilibili.com/video/BV1mk4y1k7eg)

>>#### 时间：2021年6月6日22:32:37
>
>>#### B站Up主 途途IT课堂
>
>>#### 学习总结 (接着第三课的常用组件)
>
>>1.1.3TableLayout-表格布局
>
>>| 属性名称     | 功能说明 |
>>| ------------ | -------- |
>>| column_count | 列数     |
>>| row_count    | 行数     |
>
>>* solid-固体  stroke-边框

#### （五）[第05课 HarmonyOS 2.0 鸿蒙UI框架：Text文本组件](https://www.bilibili.com/video/BV1WV4111782)

>>#### 时间：2021年6月8日17:07:13
>
>>#### B站Up主 途途IT课堂
>
>>#### 学习总结 
>
>>1.2显示类组件
>>
>>1.2.1text
>
>>> * text-文本 image-图像 clock-按钮
>>> * 显示字符串的组件 
>>>
>>> | 属性名称                   | 功能说明                                            |
>>> | -------------------------- | --------------------------------------------------- |
>>> | id                         | id属性，唯一                                        |
>>> | width                      | 组件宽                                              |
>>> | height                     | 组件高                                              |
>>> | text                       | 文本内容                                            |
>>> | background_element         | 背景，可以设颜色值或xml背景                         |
>>> | text_color                 | 文字颜色                                            |
>>> | text_weight                | 文字粗细                                            |
>>> | italic                     | 斜体                                                |
>>> | text_size                  | 文字尺寸 单位：fp                                   |
>>> | text_font                  | 字体如：Microsoft YaHei 黑体、SimSun宋体、KaiTi楷体 |
>>> | text_alignment             | 文字内容对齐方式                                    |
>>> | left_margin/right_margin   | 左/右外间距                                         |
>>> | top_magin/bottom_margin    | 上/下外间距                                         |
>>> | left_padding/right_padding | 左/右内间距                                         |
>>> | top_padding/bottom_padding | 上/下内间距                                         |
>>> | multiple_lines             | 文本内容换行                                        |
>>> | max_text_lines             | 最大文本显示行数                                    |
>>> | auto_font_size             | 自动调节文字大小                                    |
>>>
>>> * match_content 自适应
>>>
>>> * match_parent 继承父组件
>>>
>>>   ``` text
>>>   ohos:background_element="$graphic:shape_text_bg"//shape_text_bg.xml为xml文件名
>>>   ```
>>>
>>>   ``` text
>>>   //shape_text_bg.xml
>>>   <?xml version-"1.0" encoding="ut-8"?>
>>>   <shapre xmlnns:ohos="http://schemas.huawei.com/res/ohos" 
>>>   ohos:shape="rectangle">
>>>   <solid
>>>   ohos:color="#ffa500"/>
>>>   <stroke ohos:width="3vp" ohos:color="#00800"/>
>>>   </shape>
>>>   ```

#### （六）[第06课 HarmonyOS 2.0 鸿蒙UI框架：Image图像组件](https://www.bilibili.com/video/BV1x54y1m7gC)

>>>#### 时间：2021年6月8日17:34:18
>>
>>>#### B站Up主 途途IT课堂
>>
>>>#### 学习总结 
>>
>> 1.2.2image
>>
>>* 用于显示图片资源的组件 
>>
>>``` text
>>//DirectionalLayout里面的Image组件
>><Image
>>ohos:id="$+id:img"
>>ohos:width="200vp"
>>ohos:height="200vp"
>>ohos:image_src="$media:poc01"//为media文件下的图片名字
>>/>
>>```
>>
>>| 方法名         | 功能说明                                       |
>>| -------------- | ---------------------------------------------- |
>>| setClipGravity | 设置剪切对齐模式                               |
>>| setScaleMode   | 当图像和组件的大小不同时，此方法缩放或剪辑图像 |
>>
>>>* ``` text
>>>  img.setScaleMode(Image.ScaleMode.INSIDE);//把图片缩放到背景里面
>>>   img.setScaleMode(Image.ScaleMode.CENTRE);//把图片放到背景中央
>>>   img.setScaleMode(Image.ScaleMode.STRETCH);//把图片拉伸
>>>  ```
>>
>>* 通过findComponentById得到对象，然后组件里面提供的方法进行操作和设置
>>
>>![](C:\Users\iamda\Desktop\考研\资源\图片\ImageSlice.png)

#### （七）[第07课 HarmonyOS 2.0 鸿蒙UI框架：TickTimer计时器组件](https://www.bilibili.com/video/BV1N54y1y7kt)

>>#### 时间：2021年6月8日18:15:16
>
>>#### B站Up主 途途IT课堂
>
>>#### 学习总结 
>
>1.2.3TickTime 计时器组件
>
>* slice>TickTimeSlice
>* 在resources>layout>ticktimer_layout.xml
>
>| 方法名  | 功能说明   |
>| ------- | ---------- |
>| start() | 启动计时器 |
>| stop()  | 暂停计时器 |
>
>![](C:\Users\iamda\Desktop\考研\资源\图片\TickTimer.png)

#### (八)[第08课 HarmonyOS 2.0 鸿蒙UI框架：ProgressBar显示进度组件](https://www.bilibili.com/video/BV1FA411J7ys)

>>#### 时间：2021年6月8日18:39:53
>
>>#### B站Up主 途途IT课堂
>
>>#### 学习总结 
>
>1.2.4ProgressBar显示进度组件
>
>* 同理创建ProgressBarSlice，然后在MainAbility中引入
>
>* ``` text
>  //在MainAbility中引入
>   sur.setMainRoute(ProgressbarSlice.class.getName());
>  ```
>
>
>
>| 属性名称                     | 功能说明           |
>| ---------------------------- | ------------------ |
>| progress_color               | 进度条颜色         |
>| progress_width               | 进度条宽度         |
>| progress                     | 进度值             |
>| max                          | 进度最大值         |
>| progress_hint_text           | 进度条文字         |
>| progress_hint_text_color     | 进度条文字颜色     |
>| progress_hint_text_alignment | 进度条文字对齐方式 |
>
>![Progressbar-每点一次进度条增加](C:\Users\iamda\Desktop\考研\资源\图片\Progressbar-每点一次进度条增加.png)

#### (九)第09课 HarmonyOS 2.0 鸿蒙UI框架：Clock数字时钟组件

>>#### 时间：2021年6月8日18:58:02
>
>>#### B站Up主 途途IT课堂
>
>>#### 学习总结 
>
>1.2.5Clock数字时钟组件
>
>* 用来显示时间的
>
>| 属性名称  | 功能说明                                    |
>| --------- | ------------------------------------------- |
>| time      | 时间戳                                      |
>| time_zone | 时区GMT(格林威治标准时)、UTC、CST、DST、PDT |
>
>| 方法名               | 功能说明                                          |
>| -------------------- | ------------------------------------------------- |
>| set24HourModeENabled | 设置是否按照24小时制显示，(设为False即为12小时制) |
>
>* 时间戳的概念就是把传统表示方式的时间转化为编译器识别的一串数字
>* Clock组件是Text组件的子类
>* 如果要对组件进行操作（方法），就需要在对应的Slice里面进行得到（findComponentById），然后进行对应方法的操作。
>* 

#### (十)[第10课 HarmonyOS 2.0 鸿蒙UI框架：Button按钮组件](https://www.bilibili.com/video/BV1ot4y1i7xX)

>>#### 时间：2021年6月8日18:58:02
>
>>#### B站Up主 途途IT课堂
>
>>#### 学习总结 
>
>1.3交互类组件
>
>>1.3.1Button按钮组件
>
>>* 惯例在Slice里面创建ButtonSlice，然后在Layout里面用xml进行具体设定。
>
>>* Button组件是text组件的子类,有区别的是可以触发事件
>
>>* ``` text
>>  //为Button设置背景resources>graphic>shape_button_bg.xml
>>   <stroke ohos:width="3vp" ohos：cloor="#008000"/>//stroke表示边框
>>   <corners ohos:radius="20"/>//圆角
>>  ```
>
>>* ``` text
>> //button_layout.xml
>>  <?xml version-"1.0" encoding="ut-8"?>
>>  <DirectionalLayout *****>
>>  <Button
>>  ohos:id="$+id:btn"
>>*****
>> ohos:background_element="graphic:"shape_button_bg"
>> />
>> </DirectionalLayout>
>>
>> ```
>
>>* setClipGravity（设置激活）与setClickedListener（监听器、触发器）
>
>>* ![](C:\Users\iamda\Desktop\考研\资源\图片\Button之setClickedListener.png)

#### (十一)[第11课 HarmonyOS 2.0 鸿蒙UI框架：TextField文本输入框组件](https://www.bilibili.com/video/BV1kV411m7XM)

>>#### 时间：2021年6月8日19:25:39
>
>>#### B站Up主 途途IT课堂
>
>>#### 学习总结 
>
>1.3.2TextField文本输入框组件
>
>>* 登录的时候输入账号和密码的输入框
>>* 相同Slice+Layout
>>* 同样是text组件的子类
>>* 点击以后弹出虚拟键盘，然后输入（即输入框）
>>
>>| 属性名   | 功能说明     |
>>| -------- | ------------ |
>>| basement | 输入框下划线 |

#### (十二)[第12课 HarmonyOS 2.0 鸿蒙UI框架：Slider滑块组件](https://www.bilibili.com/video/BV1LA41177Mz)

>>#### 时间：2021年6月8日19:30:46
>
>>#### B站Up主 途途IT课堂
>
>>#### 学习总结 
>
>1.3.3Slider滑块组件
>
>>* 一般用于播放的进度条呀（滑动移动监听事件）
>>
>>* Slider继承AbsSlider组件，而AbsSlider继承ProgressBar(ProgressBar,之前学过是显示进度的显示类组件)
>>
>>* 就是播放器里面的播放条，可以推动
>>
>>* ``` text
>>  //setValueChangedListener是设置进度值，有三个回调函数
>>   //onProgressUpdated当前滑块的进度
>>   //onTouchStart鼠标拖动的时候触发
>>   //onTouchEnd鼠标离开的时候触发
>>   slider.setValueChangedListener(new Slider.ValueChangedListener(){
>>   @Override
>>   public void onProgressUpdated(Slider slider, int i,boolean b){}
>>   @Override
>>   public void onTouchStart(Slider slider){}
>>   @Override
>>   public void onTouchEnd(Slider slider){}
>>   })
>>  ```
>>
>>* 技巧通过系统告知判断是否执行（System.out.println("***"))

#### (十三)[第13课 HarmonyOS 2.0 鸿蒙UI框架：ScrollView滚动视图组件](https://www.bilibili.com/video/BV1My4y1C7Rn)

>>#### 时间：2021年6月8日19:45:26
>
>>#### B站Up主 途途IT课堂
>
>>#### 学习总结 
>
>1.3.4ScrollView滚动视图组件
>
>>* 文本过长要把文本放在resources>base>element>string.json，然后通过
>>
>>  ````text
>>  ohos:text="$string:XXX"
>>  ````
>>
>>* 
>>
>>  ``` text
>>  //string.json,通过修改name进行标签化，通过修改value进行字符串（文本）的修改
>>  {
>>  "string":[
>>  {
>>  "name":"XXX",
>>  "value":"XXXXX"
>>  }
>>  ]
>>  }
>>  ```
>>
>>* 多行形式
>>
>>  ``` text 
>>  ohos:multiple_lines="true"
>>  ```
>>
>>* 如果要滑动文本的话就要使用Scrollview（是一个组件容器继承StackLayout（堆栈）-只会显示最新的一个组件），相当于把文本放在ScrollView这样的一个滚动式的组件
>>
>>

>| 属性名         | 功能说明                       |
>| -------------- | ------------------------------ |
>| rebound_effect | 容器触底或触顶时是否有回弹效果 |

### 第二章 鸿蒙应用开发核心框架

#### （十四）[第14课 HarmonyOS 2.0 鸿蒙应用开发核心框架：什么是Ability](https://www.bilibili.com/video/BV1V54y1k7tq)

> >#### 时间：2021年6月22日21:45:15
>
> >#### B站Up主 途途IT课堂
>
> >#### 学习总结 
>
> 1.Ability的类型
>
> * Ability是应用所具有的能力的抽象，也是应用程序的重要组成部分。（一个应用可以包含多个Ability）-通过type的属性-page、service、data（在config.json里）来指定Ability模板类型
> * Ability（FA-Feature Ability、PA-Practice Ability）
> * FA支持（Page Ability，是FA唯一支持的模板，就是页面）
> * PA（Service Ability-后台运行任务的能力和Data Ability用于对外部提供统一的数据访问抽象）

#### （十五）[第15课 HarmonyOS 2.0 鸿蒙应用开发核心框架：同一Page中AbilitySlice间导航](https://www.bilibili.com/video/BV1qZ4y157pn)

> >#### 时间：2021年6月22日22:19:29
>
> >#### B站Up主 途途IT课堂
>
> >#### 学习总结 
>
> 2.FA（Feature Ability）
>
> * 2.1Page与AbilitySlice的关系
>
> * * page是FA唯一支持的模板，一个Page实例可以包含一组相关页面，每个页面用一个AbilitySlice实例表示，AbilitySlice主要用于承载Ability的具体逻辑实现和界面UI，是应用显示、运转和跳转的最小单元。AbilitySlice通过setUIContent（）为界面设置布局。通过SetMainRoute加载。
>   * Slice是切片的意思，一个Page实例中的多个Slice应具有高度相关性。
>
> * 2.2AbilitySlice间导航
>
> * * 两种适用情况，同一Page里，与不同Page里。
>
> * 2.3.1AbilitySlice路由配置
>
> * * 虽然一个Page可以包含多个AbilitySlice，但Page进入前台时界面默认只展示一个AbilitySlice（是setMainRoute（）方法指定的）。
>   * 如果要修改默认展示的Slice，可以通过addActionRoute（）方法为此Ability配置一条路由规则。此时，当其他Page实例期望导航到此AbilitySlice时，可以在Intent中指定Action。
>
> * 2.3.2同一Page内导航
>
>   * 
>
>     ``` text
>     ////第一种是跳转不返回数据，
>     present void：onClick（Component component）{
>     present（new ProductDetailSlice（）.new Intent（））；}
>     ```
>
>     
>
>   * ``` text
>     ////第二种导航方式，跳转返回数据
>     present void：onClick（Component component）{
>     presentForResult（new ProductDetailSlice（）.new Intent（），0）；}
>     ```
>
>   * ``` text
>     ////接收返回的数据
>      @Override
>         protected void onResult(int requestCode， Intent resultIntent) {
>         super.onResult(requestCode， resultIntent);
>         }
>     ```
>
>   * ``` text
>     //设置返回的数据，按返回键时才会有效
>     Intent = new Intent（）；
>     in.setParam（"id"，123）；
>     setResult（in）；
>     ```

#### （十六）[第16课 HarmonyOS 2.0 鸿蒙应用开发核心框架：不同Page中AbilitySlice间导航](https://www.bilibili.com/video/BV18i4y1E7RD)

>>#### 时间：2021年6月22日23:08:39
>
>>#### B站Up主 途途IT课堂
>
>>#### 学习总结 
>
>2.3.3不同Page中AbilitySlice间导航
>
>* 创建新的Ability的时候要在config.json注册一下
>* 然后在被跳转的Page Ability中通过addActionRoute（）配置路由规则，在其中的的Slice下匹配action
>* 不能通过press（）和pressForResult（）方法直接导航到其他Page的AbilitySlice。AbilitySlice作为Page的内部单元，以Action的形式对外暴露，因此可以通过配置Intent的Action导航到目标的AbilitySlice。即startAbility（）或startAbilityResult（）方法。
>* 获得返回结果的回调为inAbilityResult（）。在Ability中调用setResult（）可以设置返回结果。
>* 在按钮（button）里进行暴露in.setAction（“注册的XXX”），即先暴露再导航

## 

