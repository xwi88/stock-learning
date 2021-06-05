# 自創均線乖離率EMAB(客制副圖指標)

- 當BIAS乖離率為正25以上的時候，代表股價處於長中短期均線之上，EMA多頭排列。
- 當BIAS乖離率為負25以下的時候，代表股價處於長中短期均線之下，EMA空頭排列。
- 當BIAS乖離率處於正25至負25之間的時候，代表股價處於均線密集區域，震盪整理。
- 乖離率正40以上和負40以下，都是很極端的數值，值得留意。

## ref

- https://q.futunn.com/feed/106009781141508#!

## 设置

### 指标属性

- 编码: EMAB
- 全名: 均线乖离率
- 对象: 副图

```txt
EMAB (EMA BIAS)
利用短中長期EMA和目前平均K線股價AP(開盤+收
盤+最高+最低)/4，計算和均線之間的乖離率BIAS。
BIAS的数值介正50至負50之間。
```

### 参数

|参数名|参数值|最大值|最小值|
|--|--|--|--|
|S|20|30|5|
|M|60|90|31|
|XL|120|240|91|
|AVG|3|5|1|

## 编码

```txt
AP:=(O+C+H+L)/4
SM:=ABS(EMA(AP,S)-EMA(AP,M))
CS:=AP-EMA(AP,S)
ML:=ABS(EMA(AP,M)-EMA(AP,XL))
CM:=AP-EMA(AP,M)
BIAS_S:=CS/(ABS(CS)+SM)*50
BIAS_M:=CM/(ABS(CM)+ML)*50
BIAS:EMA(BIAS_M+BIAS_S,AVG)/2,COLORSTICK
HIGH40:40
LOW40:-40
```
