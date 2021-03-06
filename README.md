# RoundProgressBar
Android圆形倒计时控件，采用Canvas绘制外加ValueAnimator实现计时效果,可以自定义文字，文字大小，文字颜色，外弧的宽度，颜色，外弧扫过的方向等

## 效果图

![此处输入图片的描述][1]

## Gradle
```groovy
compile 'com.qfxl:roundProgressBar:1.0.0'
```
## code
```java
  RoundProgressBar roundProgressBar = new RoundProgressBar(this);
        roundProgressBar.setCenterTextSize(40);
        roundProgressBar.setCenterText("清风徐来");
        roundProgressBar.setCenterTextColor(Color.BLUE);
        roundProgressBar.setCountDownTimeMillis(5000);
        roundProgressBar.setPadding(10,10,10,10);       
        roundProgressBar.setCenterBackground(Color.WHITE);
        roundProgressBar.setStartAngle(-90);
        roundProgressBar.setStrokeWidth(10);
        roundProgressBar.setAutoStart(true);
        roundProgressBar.setDirection(RoundProgressBar.Direction.REVERSE);      
```

## layout
```xml
<com.qfxl.view.RoundProgressBar
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:padding="10dp"
        app:rpb_centerBackgroundColor="#808080"
        app:rpb_centerText="跳过"
        app:rpb_centerTextColor="#fff"
        app:rpb_centerTextSize="14sp"
        app:rpb_countDownTimeInMillis="5000"
        app:rpb_progressDirection="forward"
        app:rpb_sweepStartAngle="-90"
        app:rpb_autoStart="true"
        app:rpb_sweepStrokeColor="@color/colorPrimaryDark"
        app:rpb_sweepStrokeWidth="2dp" />
```

## 自定义属性

|属性|属性说明|类型|默认值|
|:--:|:--:|:--:|:--:|
|rpb_sweepStrokeWidth|外弧线的宽度|dimension|5|
|rpb_sweepStrokeColor|外弧线的颜色|color|Color.BLACK|
|rpb_sweepStartAngle|外弧线的起始扫描角度|integer|-90|
|rpb_centerText|中间文本|string|-|
|rpb_centerTextSize|中间文本的文字大小|dimension|12sp|
|rpb_centerTextColor|中间文本的文字颜色|color|Color.BLACK|
|rpb_centerBackgroundColor|中间区域的背景色|color|Color.GRAY|
|rpb_countDownTimeInMillis|倒计时的时间|integer|3000(ms)|
|rpb_progressDirection|外弧扫过的方向|enum[forward(0),reverse(1)]|forward(0)|
|rpb_autoStart|是否自动开启倒计时|boolean|true|

## 其他
### 如何监听

```java
        RoundProgressBar mRoundProgressBar = (RoundProgressBar) findViewById(R.id.rpb_1);
        mRoundProgressBar.setProgressChangeListener(new RoundProgressBar.ProgressChangeListener() {
            @Override
            public void onFinish() {
               
            }

            @Override
            public void onProgressChanged(int progress) {
             
            }
        });
```
### 如何手动开启计时
```java
mRoundProgressBar.start();
```
### 如何停止
`倒计时结束自动停止，当然也可以强制停止`
```java
mRoundProgressBar.stop();
```

### 如何设置为百分比计时

只需要rpb_centerText为空，则默认开启百分比计时效果


  [1]: https://github.com/qfxl/RoundProgressBar/blob/master/gif/demo.gif
