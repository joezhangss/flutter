# flutter_umeng

集成友盟推送和友盟统计

安卓配置： 需要在androidManifest.xml里填入下面的信息：

<<<<<<< HEAD

    <meta-data android:name="UMENG_APPKEY" android:value="友盟的key"/>
        <meta-data android:name="UMENG_PUSHSECRET" android:value="友盟的push secret"/>
        <meta-data android:name="com.huawei.hms.client.appid" android:value="appid=华为的id"/>
        <meta-data android:name="MI_ID" android:value="appid=小米的id"/>
        <meta-data android:name="MI_KEY" android:value="appkey=小米的key"/>
        <meta-data android:name="MZ_ID" android:value="appid=你的魅族Id"/>
        <meta-data android:name="MZ_KEY" android:value="appkey=你的魅族Key"/>
=======
    <meta-data android:name="UMENG_APPKEY" android:value="友盟的key"/>
    <meta-data android:name="UMENG_PUSHSECRET" android:value="友盟的push secret"/>
    <meta-data android:name="com.huawei.hms.client.appid" android:value="appid=华为的id"/>
    <meta-data android:name="XIAO_ID" android:value="小米的id"/>
    <meta-data android:name="XIAO_KEY" android:value="小米的key"/>
    <meta-data android:name="MZ_ID" android:value="你的ID"/>
>>>>>>> db90b428db3f6bcbf68d955c93211bfcacbf99fa
ios：需要打开对应的权限和设置。比如打开推送的功能等权限，详情参考友盟官方的说明

使用： 在main里初始化： if (Platform.isIOS){ 
	FlutterUmeng.initAnalytics(友盟的key);//友盟的统计初始化 
} 
<<<<<<< HEAD
FlutterUmeng.ready();

//点击通知后的处理
    FlutterUmeng.onPushClick((name, value){
      print("回传的value==${value}");
      Map map = new Map();
      if(Platform.isIOS){
        FlutterUmeng.removeBuffer();
      }
      map = jsonDecode(value.toString());//返回的通知消息

    });
=======
//推送前的初始化（主要用于离线推送后打开对应的页面）
FlutterUmeng.ready();

//点击通知后的处理
FlutterUmeng.onPushClick((name, value){
  print("回传的value==${value}");
  if(Platform.isIOS){
    FlutterUmeng.removeBuffer();
  }
});
>>>>>>> db90b428db3f6bcbf68d955c93211bfcacbf99fa
