"Android插件化和动态加载框架"

---
携程App的插件化和动态加载框架已上线半年，经历了初期的探索和持续的打磨优化，新框架和工程配置经受住了生产实践的考验。
Android DynamicApk 框架实现了多APK动态加载和HotFix解决方案，通过对aapt的修改实现资源分区，各个模块可以单独的配置资源的PackageID，做到真正的独立APK模块化。

#Benifit
- 插件化架构适应开发节奏需求，不但从代码层面，更从项目控制层面做到了高内聚低耦合，极大降低了沟通成本，提高了工作效率。
- 拆分成多个小的插件后，dex从此告别方法数天花板。
- HotFix为app质量做好最后一层保障方案，再也没有无法挽回的损失了。
- ABTesting脱离古老丑陋的if/else实现，多套方案随心挑选按需加载。
- 编译速度大大提高，各BU只需使用宿主的编译成果更新编译自己子工程部分，分分钟搞定。
- App宿主apk大大减小，各业务模块按需后台加载或者延迟懒加载，启动速度优化，告别黑屏和启动ANR。
#Build
To build:
$ git clone https://github.com/CtripMobile/DynamicAPK.git
$ cd DynamicAPK/
$ gradle assembleRelease bundleRelease repackAll 
