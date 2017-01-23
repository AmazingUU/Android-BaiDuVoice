# Android 基于百度语音的语音交互功能
## 简介
项目利用百度语音的
- 语音唤醒
- 语音识别
- 语音听写

组成一套完整的语音交互系统。

## 效果图
<img src="http://img.blog.csdn.net/20170123231758117" width = "300" height = "500" alt="BaiDuVoice" align=left /><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
效果图里没有声音，实际上唤醒成功后，会有语音合成的“唤醒成功，请说出指令”女声。语音识别成功后同样会有语音合成的女声，具体参见代码。

## 使用方法
clone后，语音合成第一次使用需要联网，显示出auth success后表示语音合成授权成功，之后就可以离线使用了。语音唤醒和语音识别可以离线使用。
说出唤醒词即可唤出语音识别，在线情况下可以识别任意词语，离线情况只能识别特定词语。(唤醒词和离线识别词语可以去官网[百度语音](http://yuyin.baidu.com/)自定义，然后修改下面的代码即可)

`
params.put("kws-file", "assets:///WakeUpDemo.bin"); // 设置唤醒资源, 唤醒资源请到 http://yuyin.baidu.com/wake#m4 来评估和导出,将导出的文件放在assets目录下，将代码中的文件名替换即可。
`

`
intent.putExtra("grammar", "asset:///baidu_speech_grammardemo.bsg"); // 设置离线的授权文件(离线模块需要授权), 该语法可以用自定义语义工具生成, 链接http://yuyin.baidu.com/asr#m5,将导出的文件放在assets目录下，将代码中的文件名替换即可。
`

语音识别若不成功，可以再次说出唤醒词，这样整套语音交互系统就避免了手动控制。
## 注意事项
项目里的APPID，APIKey，SecretKey只是为了让项目正常运行，实际使用过程中请替换成自己的APPID，APIKey，SecretKey。