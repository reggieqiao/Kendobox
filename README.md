# kendobox
Kendo UI Components Plugins Custom alert, confirm, dialog, validator, notice (Kendo UI 组件扩展插件，自定义alert, confirm, dialog, validator, notice) 

# Examples (实例)
[Examples address](https://reggieqiao.github.io/kendobox/examples/) ([演示地址](https://reggieqiao.github.io/kendobox/examples/))

# Dependencies (依赖)
1. Latest version of [jQuery](https://jquery.com/). (最新版本[jQuery](https://jquery.com/))
2. [Kendo UI](http://demos.telerik.com/kendo-ui/).

# Usage (使用)
Include the dependencies and jquery.kendobox.min.js into your page and call the following (在页面上引用依赖文件和 jquery.kendobox.min.js 文件，像下面那样调用):
```javascript
$.kendobox.alert('Hello world');
```
```javascript
$.kendobox.confirm('Are you sure?', function() {
	$.kendobox.notice_info('Confirm result: yes');
});
```
```javascript
$.kendobox.dialog($('#tpl-dialog').html(), function() {
	$.kendobox.validator('form[name=dialog]', function(){
		var data = $('form[name=dialog]').serializeArray();
		$.kendobox.notice_info('Dialog result: ' + data[0].value);
		$.kendobox.close();
	});
});
```
See more examples of usage (更多使用请看演示): https://reggieqiao.github.io/kendobox/examples/ 