# Landscape_mask v1.0.2
### 横屏遮罩（主要移动端使用）

文件结构：
-------------
1. landscape_mask.js放入项目文件夹jq中
2. landscape_mask.min.css、landscape_mask.min.css.map、landscape_mask.png 放入项目文件夹inc中

页面引用：
-------------
1. 页面底端引用最新版 Jquery.min.js#1.x.x 或 zepto.js
2. Jquery/zepto 之后引用 /jq/landscape_mask.js

功能配置及启用：
--------------
1. 在页面中引用 landscape_mask.js 后则代表页面启用
2. 在可能弹出键盘的input/select/textarea标签中，写入class="landscape_mask_no_focus"，可以在该控件拥有页面焦点时，阻止横屏遮罩。


效果
--------------
[http://twedding.cn/test/landscape_mask](http://twedding.cn/test/landscape_mask)


更新日志
--------------
v1.0.2

		修改弹出层的定位为fixed
