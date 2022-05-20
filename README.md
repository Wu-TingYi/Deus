# 探勘者:人工意識
 - #### 專案簡介
 - #### 核心系統

## 專案簡介
    一款使用Unreal Engine4製作的第三人稱類魂遊戲，大多功能以藍圖完成，少部分用到C++，Ex:Loading介面
## 核心系統 
## 戰鬥

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

![未命名](https://user-images.githubusercontent.com/92261914/169542035-527c1a80-70d3-43d3-b437-40f7337b693f.png)

- ## 模型打擊抖動
  - 玩家攻擊射線得到Physical Material(對應Boss在Physical Asset中設定的Physical Material)來判斷出擊中哪一個部位，來播放該部位的CachedPose(以實作過Transform Bone)
![未命名1](https://user-images.githubusercontent.com/92261914/169543002-665f6022-5498-4420-939f-12bc1030d8e0.png)
![3](https://user-images.githubusercontent.com/92261914/169292229-11c1729b-0556-4936-9c8a-67fe6a6a622a.png)
 - **Transform(Modify)**:
   主要控制模型骨架的偏移
 - **Apply a Percentage of Rotation**:
   連帶選定的骨頭位置做一定程度的連帶位移
![12](https://user-images.githubusercontent.com/92261914/169313210-52abd141-72a8-473c-a5e1-0bc0e3e48950.png)
- ## 實際效果
<p align="center">
  <img width="640" height="360" src="https://user-images.githubusercontent.com/92261914/169323349-9552c2f9-4db2-41a2-a0e1-48377d74ade9.gif">
</p>


## 敵人
![class drawio](https://user-images.githubusercontent.com/92261914/169532363-04c49354-ff19-42d0-922c-7460a738fa2b.png)
 - **敵人Base**
   - 主要負責敵人共同持有的能力和數值
      - Property : 血量、狀態、護甲、傷害
      - Fuction : 鎖定玩家、攻擊Trace追蹤、造成傷害

 - **Boss**
    - Boss才有的設定 - 受傷後累積的耐力值、二階段生成的小怪、受擊後Bone位移
      - Property : 耐力值、最大耐力值、生成方塊Actor
      - Function : 骨骼位移、創建方塊、摧毀方塊

 - **小怪**
    - 小怪有定點巡邏的功能
      - Property : 巡邏位置(TargetPoint)、巡邏點Index、發現的Actor
      - Function : 掉落道具

## 行為樹
 - ### Boss
![7](https://user-images.githubusercontent.com/92261914/169297080-c695cf94-cebc-46a5-b7d9-7039abef5ffc.png)
<p align="center">
  <img width="721" height="491" src="https://user-images.githubusercontent.com/92261914/169331793-f972341e-6878-4ad9-be45-9eeff88fd04a.png">
</p>

 - ### 小怪
![8](https://user-images.githubusercontent.com/92261914/169297260-fca2d295-48fc-4199-aa7e-dd8c25edb47d.png)

