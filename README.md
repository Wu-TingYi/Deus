# 探勘者:人工意識
 - #### 專案簡介
 - #### 核心系統

## 專案簡介
    一款使用Unreal Engine4製作的第三人稱類魂遊戲，大多功能以藍圖完成，少部分用到C++，Ex:Loading介面
## 核心系統 
### 戰鬥

- ### 攻擊判定
      在玩家攻擊時的部分幀數做Trace判斷命中偵測，追蹤到的Pawn會記錄在陣列做排除的動作，避免一下攻擊對同一個敵人造成二次傷害

![1](https://user-images.githubusercontent.com/92261914/169288821-63445e1d-c1b6-4b99-9707-bea0d6e65669.png)
<p align="center">
  使用AnimNotifyState在Notify_Tick做射線追蹤判斷
</p>  

![2](https://user-images.githubusercontent.com/92261914/169289633-a035a640-874b-4d85-85f2-4f5e586b3ae4.png)
<p align="center">
  Trace Debug顯示圖示
</p>

![5-1](https://user-images.githubusercontent.com/92261914/169296830-c8029e98-ecc6-4237-b7e5-c9583301147e.png)
<p align="center">
    SphereTrace做射線追蹤判斷Pawn(敵人)和(Destructible)場景破壞物
</p>

### 模型打擊斗動
![11](https://user-images.githubusercontent.com/92261914/169312292-f9c6a6e4-0725-4261-b65e-b491569f7628.png)
![3](https://user-images.githubusercontent.com/92261914/169292229-11c1729b-0556-4936-9c8a-67fe6a6a622a.png)
 - **Transform(Modify)**:
   主要控制模型骨架的偏移
 - **Apply a Percentage of Rotation**:
   連帶選定的骨頭位置做一定程度的連帶位移
![12](https://user-images.githubusercontent.com/92261914/169313210-52abd141-72a8-473c-a5e1-0bc0e3e48950.png)
根據Boss在Physical Asset中設定的Physical Material與玩家攻擊射線得到PhysicalMaterial來判斷出擊中哪一個部位，來播放該部位的CachedPose(以實作過Transform Bone)
![2022-05-19_22-33-45_AdobeCreativeCloudExpress10](https://user-images.githubusercontent.com/92261914/169323349-9552c2f9-4db2-41a2-a0e1-48377d74ade9.gif)
<p align="center">
    實際演示效果
</p>


## AI
### 行為樹

![7](https://user-images.githubusercontent.com/92261914/169297080-c695cf94-cebc-46a5-b7d9-7039abef5ffc.png)
<p align="center">
    Boss行為邏輯
</p>

![8](https://user-images.githubusercontent.com/92261914/169297260-fca2d295-48fc-4199-aa7e-dd8c25edb47d.png)
<p align="center">
    小怪行為邏輯
</p>

