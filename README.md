# iOS 自动编译打包shell脚本
**[详情请看简书：iOS shell脚本实现xcodebuild编译打包+curl上传蒲公英、App Store+上传dSYM到Bugly](https://www.jianshu.com/p/bc1c38486887)**

###实现功能：
*  自动编译出`xcarchive`文件。
*  自动打包导出`ipa`文件。
*  自动将`ipa`上传App Store、蒲公英。
*  自动压缩、上传`dYSM`（[什么是dYSM？](https://bugly.qq.com/docs/user-guide/symbol-configuration-ios/?v=20181014122344#dsym_1)）文件到[Bugly](https://bugly.qq.com/v2/index)。
*  三种设置`version`和`build`版本号模式：
1、不做修改，保留当前版本。
2、`build`号自动+1。
3、随心设置`version`和`build`号。

###准备工作：
*  **下载shell脚本**
首先请在这里下载文件shell文件，然后将文件夹里的`b.sh`、`ADHOCExportOptionsPlist.plist`和`AppStoreExportOptionsPlist.plist`放到你的工程根目录下(和你`.xcodeproj`文件同级)。
*  **重新配置属于你项目的ExportOptionsPlist文件**
最简单的配置方式是用你自己项目的`ExportOptionsPlist`文件替换刚刚放到你项目根目录中的`ADHOCExportOptionsPlist.plist`和`AppStoreExportOptionsPlist.plist`文件。至于生成`ExportOptionsPlist`文件，**你可以配置好项目证书后，使用Xcode分别用Debug和Release模式Archive，然后导出`ipa`包，在`ipa`包同级文件夹中就可以找到相应模式的ExportOptionsPlist文件**。
*  **配置属于你的脚本**
 替换**b.sh**脚本中的变量值，详情请看shell脚本。
###执行脚本：
*  打开终端`cd`到你的项目根目录。
*  使用`./b.sh`指令执行脚本。
*  选择编译环境`Place enter the number you want to export ? [ 1:app-store 2:ad-hoc]`
*  设置version和build版本号`Do you want to set a new version for xxxxx ? [ 1:NO 2:Build version + 1 3:YES ] `。

设置完编译环境和版本号后静待编译打包和上传，脚本默认将`xxxxxx.xcarchive`和`xxxxxx.ipa`导出到`~/Desktop`桌面`Build`和`IPAs`文件夹中。
#

**[详情请看简书：iOS shell脚本实现xcodebuild编译打包+curl上传蒲公英、App Store+上传dSYM到Bugly](https://www.jianshu.com/p/bc1c38486887)**