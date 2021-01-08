## 1 什么是SharedPerference存储

SP存储是一种轻量级的数据存储，通常做一些简单，单一数据的持久化缓存



## 2 SharedPerference存储的特点

SharedPreference保存的数据是简单的key--value键值对。保存的数据是以xml文件的格式存储的。可设置数据只能是当前应用读取，而别的应用不可以应用卸载时会删除此数据

## 3 SharedPerference的作用

SharedPreference存储倾向于保存用户偏好设置，比如某个Checkbox的选择状态，用户登录的状态，配置信息，实现记住密码功能等。

## 4 SharedPerference存储的数据类型

> boolean    float     int     long     String 

## 5 数据保存的路径

/data/data/packageName/shared_prefs/yyy.xml

## 6 使用介绍

**保存数据**

~~~java
        // 1 使用Activity类的getSharedPreferences方法获得SharedPreferences对象
        //  参数1  文件名
        //  参数2  模式 一般使用 MODE_PRIVATE
        SharedPreferences sp = getSharedPreferences("test_sp",MODE_PRIVATE);
        // 2 使用SharedPreferences接口的edit获得SharedPreferences.Editor对象。
        SharedPreferences.Editor editor = sp.edit();
        // 3 通过SharedPreferences.Editor接口的putXxx方法保存key-value对
		//   其中Xxx表示不同的数据类型  boolean float  int  long String
        editor.putBoolean("isLogin",true);
        editor.putString("name","zhangsan");
        editor.putInt("age",18);
        editor.putFloat("money",99.9f);
        editor.putLong("time",10000L);
		// 4 通过SharedPreferences.Editor接口的commit方法保存key-value对
        editor.commit();
         

~~~

**获取数据**

~~~java
        // 1 使用Activity类的getSharedPreferences方法获得SharedPreferences对象
        //  参数1  文件名
        //  参数2  模式 一般使用 MODE_PRIVATE
        SharedPreferences sp = getSharedPreferences("test_sp",MODE_PRIVATE);
		// 2 获取数据
		String name=preferences.getString("name", "defaultname");
		String age=preferences.getString("age", "0");

~~~



