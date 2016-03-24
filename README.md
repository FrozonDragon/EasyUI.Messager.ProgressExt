# EasyUI.Messager.ProgressExt
A improvement on Messager component of EasyUI framework. New option to show endless Progressbar

When using Messager with progressbar of EasyUI framework to indicate the background work is on-going, it is hard and troublesome to tell user that loading is 100% completed. 

Hence, need the progressbar to be endless looping before .ajax done is triggerred. 

## How to use

```javascript
<script type="text/javascript" src="./easyui/jquery.easyui.min.js"></script>
<script type="text/javascript" src="./lib/easyui/custom/jquery.progressbar.custom.js"></script>
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
