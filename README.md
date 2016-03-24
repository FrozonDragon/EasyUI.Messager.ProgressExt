# EasyUI.Messager.ProgressExt
A improvement on Progressbar component of EasyUI framework. 

When using Messager with progressbar of EasyUI framework to indicate the background work is on-going, it is no need to tell user exact percentage. Most of time, we just use gif image file as an indicator.

Since messager already integrates with progress options, what need to do is to show the endless looping before .ajax is completed. 

## How to use

```javascript
<script type="text/javascript" src="../lib/easyui/jquery.easyui.min.js"></script>
<script type="text/javascript" src="../lib/easyui/custom/jquery.progressbar.custom.js"></script>
```

```javascript
$.ajax({
		url: "./get_data.php?prod="+prod+"&time="+d.getTime(), //add time to too force refresh
		type: "GET",
		dataType: "text",
		beforeSend: function( xhr ) {
			var win = $.messager.progress({	title:'Please wait', msg:'Retrieving data from database...'});
		},
		success: function(rep) {
			$.messager.progress('close');
		},
		error : function(XMLHttpRequest, textStatus, errorThrown) {		
			$.messager.progress('close');				
			alert("ERROR: "+textStatus + ": " + errorThrown);
		}	
	});
```
 

![Alt text](demo.gif?raw=true "Result")
