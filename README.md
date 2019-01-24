# SvgAnimation
Svg动画，path动画


在网上找了好久svg动画相关的东西，但实现起来都不是很理想。
之前找到了https://github.com/geftimov/android-pathview 

可以直接引用svg文件，很方便，但是实现起来 动画效果比较生硬，所以被pass掉了。

后来又发现了这位大神的：
https://github.com/jaredrummler/AnimatedSvgView

动画效果完全符合我的需求，但是很纠结的是不能直接引用svg文件资源，需要自己把path以及对应的colo提炼成数组 去加载（一旦图片复杂点path 路径简直不是几百行能完的）。


后来想了想 不如在此基础上去解析svg文件，把path/colo提炼出来？

没想到经过小半天的调试，竟然真的成了，小菜鸡也是有春天的啊。


提醒：
    如果你是使用path、color数组请参照这位大神的方法即可, 不必再往下看！
    （ https://github.com/jaredrummler/AnimatedSvgView ）
    


================ 正文 ==============

使用方法：

----------
1、新建assets文件夹，将需要加载的svg文件放进去

----------

2、xml:


<com.jaredrummler.android.widget.AnimatedSvgView

    android:id="@+id/animated_svg_view"
    
    android:layout_width="180dp"
    
    android:layout_height="180dp"
    
    android:layout_gravity="center"
    
    android:layout_marginBottom="25dp"
    
    app:animatedSvgFillStart="2000"
    
    app:animatedSvgFillTime="2000"
    
    app:animatedSvgImageSizeX="500"
    
    app:animatedSvgImageSizeY="500"
    
    app:animatedSvgTraceTime="2000"
    
    app:animatedSvgTraceTimePerGlyph="1000"/>

----------

3、java:

说明： asstes_name  : assets下的svg文件名  如 "logo.svg"


 svgView.startSvgDataResource(asstes_name);
 
        svgView.setViewportSize(600, 700);
        
        svgView.setTraceResidueColor(0x22000000);
        
        svgView.rebuildGlyphData();
        
        svgView.start();



其他的东西也可以参考
https://github.com/jaredrummler/AnimatedSvgView 




=========================================================================================





License

-----------------其实这东西我也不知道有什么用，声明？许可证？ 菜鸡果然是菜鸡，我还要努力学习---------------------------



Copyright (C) 2016, Jared Rummler

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.


