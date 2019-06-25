# Android触摸事件相关 #
![](https://upload-images.jianshu.io/upload_images/623378-4c56f31ce1e37b0e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/987/format/webp)
# Android中View的继承体系 #
![](https://i.imgur.com/keKfcSv.jpg)
`Androidsdk源码解析系列:` [https://github.com/LittleFriendsGroup/AndroidSdkSourceAnalysis](https://github.com/LittleFriendsGroup/AndroidSdkSourceAnalysis)
# Android开发中的字节码操控:Javassist#

# RecyclerView高度wrap\_content和match\_parent(或者固定高度)的区别 #
    这个暂时还没有具体的答案,但是通过开发中遇到的问题,证明两者是有区别的.

# Android完整开源项目 #
### 小说阅读器 ###
[https://github.com/smuyyh/BookReader](https://github.com/smuyyh/BookReader)
# Android Library gradle配置不生成BuildConfig.java #
    libraryVariants.all {
        it.generateBuildConfig.enabled = false
    }

# Android布局中的空格以及占一个汉字宽度的空格,实现不同汉字字数对齐 #
### 布局中的空格 ###
- 空格：`&#160;`（普通的英文半角空格但不换行）
- 窄空格：`&#8201;`
- `&#12288;`（中文全角空格 （一个中文宽度））
- `&#8194;`（半个中文宽度，但两个空格比一个中文略大）
- \u3000\u3000（首行缩进）
- \u3000（全角空格(中文符号)）
- \u0020（半角空格(英文符号)）
- `&#8230;`（省略号）

	所以如果想要实现文字对齐，那么可以考虑下面的方案：

	方案一：一个汉字宽度的空格：`&#12288;`

	方案二：一个汉字宽度的空格：`&#160;&#160;&#8201;`【用两个空格（`&#160;&#160;`）占一个汉字的宽度时，两个空格比一个汉字略窄，三个空格（`&#160;&#160;&#160;`）比一个汉字略宽】；使用`&#160;&#160;&#8210;`时候部分机型转译后不是空格，而是“-”；而且在不同机型有不同表现。

	方案三：一个汉字宽度的空格：`&#8194;&#8194;`【比一个中文略大】

	方案四：一个汉字宽度的空格：`&#8195;`【比一个中文略大】