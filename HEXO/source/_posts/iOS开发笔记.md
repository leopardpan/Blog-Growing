---
title: iOS开发笔记
category: 工具
---

iOS 日常开发笔记

<!--more-->

### 1、断点配置：【Generate Debug Symbols】     
* **描述:** 用来控制断点是否生效,关闭此功能，打包.ipa时，包体积会小很多。    
* **path:**【project/TARGETS/Build Settings/Apple LLVM7.1 - Code Genneration/Generate Debug Symbols】    
### 2、捕获全局异常：【All Exception】    
* **描述:** 用来捕捉整个项目在Xcode里执行时的异常。例如：try/catch时,catch住的异常,【All Exception】可以直接定位到具体位置。     
* **path:** 异常捕捉(commod+7)/Xcode左下角点击+/Add Exception Breakpoint/完成(回车键)      




