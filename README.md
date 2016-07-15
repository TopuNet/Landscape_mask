# Landscape_mask v1.1.1
### 横屏遮罩（主要移动端使用）
### 兼容原生JS规范和AMD规范

更新日志
--------------
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
