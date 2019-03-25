---
title: 记一次 “Could not launch” 错误
date: 2019-03-18 11:29:26
categories:
- iOS 相关
tags: Xcode
---

## 问题描述
1. 免费真机运行调试
2. run app 时报错：

```
Could not launch “WXKCarousel”
filo's 7 has denied the launch request.
```
3. 导致 Xcode 无法运行 app

## 问题解决
1. 猜测是 code sign 问题，于是 Build Setting -> Code Signing，查看是否正常选择了 developer 证书，正确选择是 iOS Developer。
2. SO 上有人，Xcode，Product > Scheme > Edit Scheme > 'Info' tab > Executable:  "Ask on Launch"，尝试后，有效
3. 做尝试，和看评论，发现在 Xcode，Product > Scheme > Edit Scheme > 'Info' tab，取消 Debug executable 勾选，也能解决问题
4. 记录笔记时，重新看了证书，发现生成了一个我的 Apple ID 的开发这证书，带 Team ID 的那种，勾选之，提示报错如下：免费真机调试，自动管理签名即可。

```
WXKCarousel is automatically signed, but code signing identity iPhone Developer: 984913833@qq.com (J79WAX665X) has been manually specified. Set the code signing identity value to "iPhone Developer" in the build settings editor, or switch to manual signing in the project editor.
```

## 根因分析


## 再次尝试
由于只能找到 Debug executable 的作用，很难找到报错的原因，再次作出一些尝试

1. 重启手机
2. 创建新的scheme 和 target
3. 创建一个新的工程

**都没卵用！！！！！！！！！！**

在日志中看到这样一句话：

```
error: failed to launch '/private/var/containers/Bundle/Application/A4BAA377-0792-444E-8787-BC602FEA306E/WXKCarousel.app' -- filo's 7 has denied the launch request.
```

4. 通过个人开发者证书测试，真机调试一切正常


## 小结
1. Xcode10，免证书真机调试，会报该错误，所有的 scheme，project 都会如此
2. 通过开发者证书调试，一切正常
3. 准备用 Xcode9.4.1 尝试








