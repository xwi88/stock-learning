# 换手平均成本均线指标

>指数平均

## ref

- https://q.futunn.com/hk/feed/105532045393928?lang_code=1

## 设置

### 指标属性

- 编码: HSX
- 全名: 换手均价
- 对象: 主图

### 参数

|参数名|参数值|最大值|最小值|
|--|--|--|--|

## 编码

```txt
HSL:VOL/CAPITAL*100,NODRAW
DD:SUMBARS(VOL,CAPITAL),NODRAW
HSX:EMA(C,DD),COLORGRAY,LINETHICK2
HS:MA(C,DD),COLORGRAY
```
