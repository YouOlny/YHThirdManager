# 一个好用的社交化组件，目前支持微信(包含支付功能和不包含支付功能)、新浪微博、QQ、支付宝(进行中)


# 该组件暂时不支持pod，请使用手动的方式集成进自己的项目中。

1、集成之前请根据自己项目的实际情况，导入对应的模块。特别注意:如果你的项目不包含支付功能，请导入不包含支付功能的模块，否则你的APP可能会被拒

2、使用之前，请导入`MBProgressHUD`,`pod 'MBProgressHUD'`

3、在使用过程中有任何bug，欢迎提出


# 各个SDK的大小:
微信:    
包含支付功能:16.3M      
不包含支付功能:16.1M

QQ：     5M

新浪:    13.4M

共计:    34.7M(34.5M)

# 如果使用友盟
1、以精简版为例

`UMCommon.framework`:5.6M

`UMShare.framework`:11.2M

QQ、微信、新浪精简版SDK合计:4.8M

共计:21.6M

2、以完整版为例

`UMCommon.framework`:5.6M

`UMShare.framework`:11.2M

QQ、微信、新浪完整版SDK合计:40.9M

共计:57.7M

# 总结
#### 1、在使用友盟精简版的情况下，貌似比使用平台SDK的包要小，减少了大约13.1M；但是一个App如果运营到后期，肯定不止分享和登录这么简单的功能。比如要集成微信支付，这个时候使用友盟自带的微信SDK是完不成的，即使使用完整版，因为APP无法调用友盟自带的微信SDK里面的API。再比如也许会增加获取我的微博列表，同样无法使用友盟自带的微博SDK完成。这个时候，即必须要再次导入微信或者微博SDK才能完成。话句话说，友盟的分享SDK，仅仅只是为分享和登录服务的，无法完成其他功能。在项目前期使用友盟确实比较方便，但是项目后期，继续使用友盟个人觉得不是很合适。
#### 2、在使用友盟完整版的情况下，要使用微信支付、获取微博列表等这些功能，也无法完成，除非自己再次导入SDK。
#### 3、在第一次打开三方应用时，iOS系统会给用户一个选项，即"是否允许打开xxx"的这个一个弹出框，这个弹出框属于系统级别，开发者无法获取到用户到底是点击了"确定"还是"取消"。如果界面上有一个按钮，点击这个按钮时，会有个loading圈显示，如果这个时候用户点击了"取消"，那么loading圈仍然在继续显示，无法取消，本人已经看到很多APP都有这个问题；另外，即使用户点击了"确定"按钮，跳转到了三方应用了，这个时候，如果用户点击屏幕左上角返回APP，loading圈仍然在加载，因为开发者仍然获取不到用户点击屏幕左上角这个事件。`YHThirdManager`完美的解决了这些问题








