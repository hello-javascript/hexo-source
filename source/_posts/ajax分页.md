title: ajax分页
date: 2014-05-13 17:27:21
tags: js
category: javascript
---
代码蛮漂亮的，我第一次写这么好看的代码，留下来记录下
```javascript
//数据展示分页
	var pagging={
		//查询初始化、首页
		initpaging:function (index){
			if($("#supname").val()==""){
				alert("请输入公司名称,再点击查询");
				return;
				}
			$(".sup_list").html("");
			$("#sup_query").attr("disabled",true);
			$("#sup_query").css("background","#999");
			var supname=$("#supname").val();
			$.ajax({
				url:"ajaxOrder.do?method=doQuerysupList",
				type:"post",
				data:{"supname":supname,"pageSize":5,"pageNo":index},
				success:function(data){
				$("#sup_query").removeAttr("disabled");
				$("#sup_query").css("background","#e11919");
				//alert(typeof(data));
				var data=data.split("||");
				var data0=data[0];
				$("#onpag").val(data0);
				var data1=data[1];
				$("#count").text(data1);
				var suptol=parseInt(data1/5)+1;
				$("#sup_tol").text(suptol);
				//alert(data[2]);
				var data2=data[2];
				var data2=data2.substr(1);
				var data2=data2.substring(0,data2.length-1);
				var dataObj=eval("("+data2+")");
				//alert(dataObj);
				for(var i=0;i<dataObj.length;i++){
						//alert(dataObj[i][1]);
					$(".sup_list").append("<ul><li><input type=\"radio\" name=\"gys\" value=\""+dataObj[i][2]+"\"/>"+dataObj[i][1]+"</li></ul>");
					}
					}
				})

		},
			//末页
		pag_mo:function(){
				var tol=$("#sup_tol").text();
				this.initpaging(tol);
				},
			//上一页
		pag_firlt:function(){
			var pageNo=$("#onpag").val();
			if(pageNo==1){
			alert("没有上一页了");
			return;
				}
			pageNo2=parseInt(pageNo)-1;
			this.initpaging(pageNo2);
			},
			//下一页
		pag_last:function(){
					var pageNo=$("#onpag").val();
					var tol=$("#sup_tol").text();
					if(pageNo==tol){
					alert("已经是最后一页了");
					return;}
					pageNo2=parseInt(pageNo)+1;;
					this.initpaging(pageNo2);
					}
			}
```

