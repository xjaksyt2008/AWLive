
[blog点这里](http://www.jianshu.com/u/1240d2400ca1)

介绍
---
最近在做iOS直播，研究了相关直播技术，主要包含两方面：推流，播放。

因为之前使用cocos2dx做过一个视频游戏（[恋爱公寓](https://itunes.apple.com/cn/app/lian-ai-gong-yu-shi-pin-yang/id1149280715?mt=8)），用ffmpeg+sdl+cocos2dx实现过视频播放器。

游戏中的视频是hevc(h265)+aac合成mp4文件，使用aes加密。视频播放的时候，需要使用ffmpeg中的crypt模块进行aes解密后播放视频，解析出来的yuv图片数据直接送给OpenGL显示。

所以这次主要研究推流技术。并将[代码开源](https://github.com/hardman/AWLive)。

其实直播技术中不论播放还是推流，更多的应该算是技术整合，就是将前人做好的协议和实现，整合成我们自己想要的功能。

而这次做这个项目也并不是做了什么技术创新，github里面已经有着很多直播源代码，可能比我写的更好更完整。而我的代码，特点就是简单直接，直奔主题。

我会在[我的博客](http://www.jianshu.com/u/1240d2400ca1)里做一些简单的解析，目的是希望让更多的人了解直播技术，能够了解直播内部的一些简单的原理，不再知其然不知其所以然。

功能范围
---
- 视频捕获：系统方法捕获，GPUImage捕获，CMSampleRef解析
- 美颜滤镜：GPUImage，
- 视频变换：libyuv
- 横屏直播
- 软编码：faac，x264
- 硬编码：VideoToolbox(aac/h264)
- libaw：C语言函数库
- flv协议及编码
- 推流协议：librtmp，rtmp重连，rtmp各种状态回调

代码使用及注意
---
代码使用方法见Demo。后续会根据上述功能的每一点对源代码进行解析。

如果有什么疑问或者问题，请评论指出,希望能够给愿意了解直播技术的人抛出一块好砖。

注1：项目中所有相关的文件名，类名，全局变量，全局方法都会加AW/aw作为前缀。
注2：项目中关键代码都使用c语言编写，理论上可以很容易地移植到android中。
