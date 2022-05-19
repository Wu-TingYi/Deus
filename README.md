# 探勘者:人工意識

## 戰鬥

### 攻擊判定
在玩家攻擊動畫部分幀數期間做Trace判斷命中偵測

![1](https://user-images.githubusercontent.com/92261914/169288821-63445e1d-c1b6-4b99-9707-bea0d6e65669.png)
<p align="center">
  使用AnimNotifyState在Notify_Tick做射線追蹤判斷
</p>  

![2](https://user-images.githubusercontent.com/92261914/169289633-a035a640-874b-4d85-85f2-4f5e586b3ae4.png)
<p align="center">
    Trace Debug顯示圖示
</p>

![5](https://user-images.githubusercontent.com/92261914/169289864-ac4e05c8-da9a-45b3-a51d-6d89d9e7ffa9.png)
<p align="center">
    SphereTrace做射線追蹤判斷Pawn(敵人)和(Destructible)場景破壞物
</p>

### 模型打擊斗動
![3](https://user-images.githubusercontent.com/92261914/169292229-11c1729b-0556-4936-9c8a-67fe6a6a622a.png)
 - Transform(Modify):
   主要控制模型骨架的偏移
 - Apply a Percentage of Rotation:
   連帶選定的骨頭位置做一定程度的連帶位移
![Boss打擊抖動_AdobeCreativeCloudExpress](https://user-images.githubusercontent.com/92261914/169293426-b437cf88-639c-461e-8ef8-e0b396de152c.gif)
<p align="center">
    實際演示效果
</p>


## AI
### 行為樹

![7](https://user-images.githubusercontent.com/92261914/169292456-5c9a8f12-257b-42f6-8722-9a40481052c0.png)
<p align="center">
    Boss行為邏輯
</p>

![8](https://user-images.githubusercontent.com/92261914/169292713-3e938004-598d-41c5-8f2c-0df6440c5b80.png)
<p align="center">
    小怪行為邏輯
</p>

