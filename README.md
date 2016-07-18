# Landscape_mask v1.1.2
### 横屏遮罩（主要移动端使用）
### 兼容原生JS规范和AMD规范

更新日志
--------------
v1.1.2

		1. 解决了一下之前的bug：页面配合mobile_stop_moved时不正常，和弹出软键盘时不正常

		解决思路：

		经监听发现：在resize时，共调用了3次risize监听事件，第一次是旋转前，另两次是旋转后。
		
		so，为解决安卓软键盘resize的bug：
			打开页面时，记录朝向。发生risize时，判断记录的朝向是否等于新的朝向。
		是的话，隐藏遮罩并终止运行；否则显示遮罩（遮罩只有在横屏时才被显示，css的media）。

		为解决resize3次触发事件的问题，重置屏幕朝向后，不更新记录的朝向。也就是记录的朝向永远为0。
		也能理解为，发生resize时，判断当前朝向：如果是0，则不显示遮罩；如果不是0，则根据是否横屏显示遮罩。

		为解决横屏后高度不正确问题：resize事件通过朝向判断后，重置遮罩层高度前，让所有input,select失去焦点。

		2. 之前版本 可以阻止遮罩的class="landscape_mask_no_focus" 不再使用。现在只要横屏就会遮罩。

v1.1.1

		1. 兼容原生JS和AMD规范
		2. 修改demo

v1.0.2

		1. 修改弹出层的定位为fixed

文件结构：
-------------
		1. landscape_mask.js放入项目文件夹jq（原生规范）或widget/lib（AMD规范）中
		2. landscape_mask.min.css、landscape_mask.min.css.map、landscape_mask.png 放入项目文件夹inc中

页面引用：
-------------
原生引用

		1. 页面底端引用最新版 Jquery.min.js#1.x.x 或 zepto.js
		2. Jquery/zepto 之后引用 /jq/landscape_mask.js

requireJS引用

        依赖landscape_mask.js和(jquery.min.js#1.x 或 zepto.js)，成功后返回对象landscape_mask

调用方法：
--------------
原生引用：

		在页面中引用 landscape_mask.js 后则代表页面启用

requireJS引用：

		landscape_mask.init();


在可能弹出键盘的input/select/textarea标签中，写入class="landscape_mask_no_focus"，可以在该控件拥有页面焦点时，阻止横屏遮罩。
