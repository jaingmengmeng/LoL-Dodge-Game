# LoL-Dodge-Game

A LoL Dodge Game developed with Unity.

### 1 Abstract

参照 [loldodgegame](https://loldodgegame.com/) 写的英雄联盟走位小游戏。通过躲避技能来获取分数，空格暂停，鼠标右键控制游戏角色的移动，esc 键退出游戏。

### 2 Problems

1、音频的加入：音频的加入只需要在某个物体上加 Audio Source 组件即可，另外可以通过一些事件来控制音频的播放和暂停。

2、canvas 的视角：按钮和文字这些都是在 canvas 上的组件，canvas 的视角可以选定为 world space，方便自己调整画面中各个组件之间的的大小比例。另外可以调整 canvas 的分辨率来优化画面的清晰度。

3、鼠标右键点击：鼠标右键点击位置是屏幕的坐标，要转换成 Unity 中的 World Space 才能让游戏主角移动到目标位置，所以采用的是射线法，从相机位置朝鼠标点击的方向，发射一条射线，在射线碰撞到地板时，碰撞点即为目标位置。

4、碰撞检测：碰撞检测是通过在游戏主角身上设置 Collider Trigger 来实现的，同时让游戏主角和火球都设置为碰撞体 Collider，另外主角设置为刚体 Rigidbody（至少碰撞中的两个物体有一个是刚体才能在碰撞时触发相应的事件）。Collider Trigger 的机制是，当发生碰撞时就会通过 OnEnterTrigger 函数来触发一些事件，比如游戏结束。

### 3 Get Started

- dist: windows 的打包之后的文件，在 windows 环境下可以直接双击 LoL Dodge Game.exe 运行。
- mac-dist: mac 环境的打包后文件，在 mac 下直接双击 LoL Dodge Game.app 运行。
- materials: 资源文件夹，包括图片、音频、模型等。
- src: 源代码文件夹，可以使用 unity 或者 unity-hub 打开这个文件夹，修改源代码。修改代码时可以选择 Visual Studio 来进行 C# 代码的编译。
