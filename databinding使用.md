####databinding使用方法
1. class文件
	1.导入databinding文件
		import android.databinding.DataBindingUtil;
         ActivityMainBinding binding = DataBindingUtil.setContentView(this, R.layout.activity_main);
        User user = new User("lllazy","100");
        binding.setUser(user);

2. xml文件

	1.方式一
		<?xml version="1.0" encoding="utf-8"?>
        <layout xmlns:android="http://schemas.android.com/apk/res/android">

        <!--type中声明的就是我们的用户实体类User，一定要写全，带着包名，我们给这个实体类命名为user-->
            <data>
                <variable
                    name="user"
                    type="loonggg.net.databinding.bean.User" />
            </data> 
            <LinearLayout>
             ……
            </LinearLayout>
        </layout>
      2.方式二
        <data> 
          <import type="xxx.User" alias="MyUser"> 
          <import type="xxx.xx.User"> 

           <variable 
                    name="user" 
                    type="User" /> 
            <variable 
                    name="myUser" 
                    type="MyUser"/> 
        </data> 
        <TextView xxx:@{myUser.getName()}> 
        <TextView xxx:@{user.getName()}>
