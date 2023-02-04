# SlateViewerAPP
尝试了在UnrealEngine4.27版本下将SlateViewer提取出来

# SlateViewer剥离的初衷
SlateViewer是虚幻下一个独立应用，之前一直想知道如何将这个应用提取出来，因为在一些情况下我并不知道如何用虚幻以外的框架开发一个独立的桌面应用，并且调用虚幻的库。
并且尝试将他从虚幻中剥离出来。  
# 2023/02/04初步成果
前期获得的初步成果，也是为自己提供一个思路。 
（1）它可以脱离虚幻的框架（参考SwitchboardListener），参考一个参数。  
![image](https://user-images.githubusercontent.com/39860733/216771143-ceaa1a64-ad30-4510-87ae-26b042afe4e8.png)
（2）它的独立是有依赖文件的。以slateviewer为例，它使用了虚幻编辑的Slate思路，所以它使用的按键，包括图片同样是依赖“content/slate”这个文件夹里的内容。
（3）其次是如果有依赖第三库这类非虚幻框架下的内容，是要单独包含的。比如slateviewer下的“浏览器“部分，它依赖的是"\Engine\Binaries\ThirdParty\CEF3"这样一个组件。
同理在使用非浏览器部分，但是同样借用了第三库的情况。就需要按照编译前配置的文档位置将目录拷贝过去。

# 下一步要做到的是查找虚幻是否已经提供了，类似虚幻分发二进制版本时提供的脚本配置，来导出自己想要的”独立应用“。

