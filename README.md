# Kendobox
Kendo UI Components Plugins Custom alert, confirm, dialog, validator, notice

# Examples
[See examples](https://reggieqiao.github.io/kendobox)

# Dependencies 
1. Latest version of [jQuery](https://jquery.com/)
2. [Kendo UI](http://demos.telerik.com/kendo-ui/)

# Usage
1. Kendo UI style:
```html
<link rel="stylesheet" href="https://kendo.cdn.telerik.com/2016.2.714/styles/kendo.common.min.css"/>
<link rel="stylesheet" href="https://kendo.cdn.telerik.com/2016.2.714/styles/kendo.silver.min.css"/>
```

2. jQuery and Kendo UI js and kendobox:
```html
<!-- jQuery -->
<script src="https://cdn.jsdelivr.net/npm/jquery@1.9.1/jquery.min.js"></script>
<!-- Kendo UI js -->
<script src="https://kendo.cdn.telerik.com/2016.2.714/js/kendo.all.min.js"></script>
<!-- kendobox -->
<script src="assets/js/jquery.kendobox.min.js"></script>
```

kendobox alert:
```javascript
$('#btn-alert').click(function () {
  $.kendobox.alert('Hello world', function() {
    $.kendobox.notice_info('Hello world callback');
  });
});
```