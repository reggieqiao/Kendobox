# Kendobox
Kendo UI Components Plugins Custom alert, confirm, dialog, validator, notice

# Examples
[Visit examples](https://reggieqiao.github.io/kendobox)

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

kendobox custom alert:
```javascript
$('#btn-custom-alert').click(function () {
  $.kendobox.alert('Hello world', function() {
    $.kendobox.notice_info('Hello world callback');
  },{
    width: 600,
    title: 'Custom Alert'
  });
});
```

kendobox confirm:
```javascript
$('#btn-confirm').click(function () {
  $.kendobox.confirm('Are you sure?', function() {
    $.kendobox.notice_info('Confirm result: yes');
  });
});
```

kendobox custom confirm:
```javascript
$('#btn-custom-confirm').click(function () {
  $.kendobox.confirm('Are you sure?', function() {
    $.kendobox.notice_info('Custom Confirm result: yes');
  },{
    width: 600,
    title: 'Custom Confirm',
    button: [{
      name: 'Yes',
      class: 'yes',
      focus: true,
      callback: function() {
        $.kendobox.notice_success('Custom Confirm result: yes');
        $.kendobox.close();
      }
    },{
      name: 'No',
      class: 'no',
      callback: function() {
        $.kendobox.notice_error('Custom Confirm result: no');
        $.kendobox.close();
      }
    },{
      name: 'Cancel',
      class: 'cancel',
      callback: function() {
        $.kendobox.close();
      }
    }]
  });
});
```

kendobox dialog:
```javascript
$('#btn-dialog').click(function () {
  $.kendobox.dialog($('#tpl-dialog').html(), function() {
    $.kendobox.validator('form[name=dialog]', function(){
      var data = $('form[name=dialog]').serializeArray();
      $.kendobox.notice_info('Dialog result: ' + data[0].value);
      $.kendobox.close();
    });
  });
});
```

kendobox custom dialog:
```javascript
$('#btn-custom-dialog').click(function () {
  $.kendobox.dialog($('#tpl-dialog').html(), function() {
    $.kendobox.validator('form[name=dialog]', function(){
      var data = $('form[name=dialog]').serializeArray();
      $.kendobox.notice_info('Dialog result: ' + data[0].value);
      $.kendobox.close();
    });
  },{
    width: 600,
    title: 'Custom Dialog',
    button: [{
      name: 'Submit',
      class: 'submit',
      focus: true,
      callback: function() {
        $.kendobox.validator('form[name=dialog]', function(){
          var data = $('form[name=dialog]').serializeArray();
          $.kendobox.notice_info('Dialog result: ' + data[0].value);
          $.kendobox.close();
        });
      }
    },{
      name: 'Reset',
      class: 'reset',
      callback: function() {
        $('form[name=dialog]').find('input').val('');
        $.kendobox.notice_info('Dialog result: reset');
      }
    },{
      name: 'Cancel',
      class: 'cancel',
      callback: function() {
        $.kendobox.close();
      }
    }]
  });
});
```