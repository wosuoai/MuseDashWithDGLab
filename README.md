# MuseDashWithDGLab

最近在研究DGLab传感器的组网玩法，碰巧看到了[原作者](https://www.bilibili.com/video/BV1fYb6eCEVn/?spm_id_from=333.999.0.0&vd_source=2fd3ba55680b068513b405805ac658cf)的DGLab和游戏的组合，利用Melon Loader加载游戏mod实现

自己现在只学到APP逆向，dll有点看不懂，只能先搁置一下，后续做做优化

但是看到有python的项目配套otc控制器，这边就随缘了吧，最多应某人要求改改判定规则，毕竟我不敢反抗QAQ

记录一下配置需求避免忘了


## mod载入
下载[Melon Loader](https://github.com/LavaGang/MelonLoader/releases)并安装到MuseDash游戏所在文件夹

将Mod文件下的MuseDashMirror.dll与MuseDashXDGLab.dll复制到\Muse Dash\Mods

将Mod\Dependencies\中的所有文件复制到\Muse Dash\UserLibs

更改完成后 通过Melon Loader载入MuseDash游戏所在文件夹

## 配置
安装打开游戏后，在Muse Dash\UserData\MelonPreferences.cfg中修改配置，主要是将ip地址修改成自己的

自行安装[Node.js](https://nodejs.org/en)

在`websocketNode.js`文件上一级输入指令`npm i npx -g`和`npm i pm2 -g`

随后执行`npx pm2 start websocketNode.js `  如果一直处于stop状态 不妨执行一下`node websocketNode.js`看看是否有Error: Cannot find module 'xxx' 如果有则`npm i xxx` 再执行`npx pm2 start websocketNode.js `  

**注意：**结束游戏休息的时候记得`npx pm2 stop websocketNode.js`不然node的进程一直在后台

**！！！**如果不想看到弹窗 可以进入steam——库——属性——通用——`--melonloader.hideconsole` 关闭弹窗



最后感谢[作者大大](https://github.com/M1zukiQAQ1/MuseDashWithDGLab)，也希望后续可以有更多的玩法出现
