## 第5章

---
### 51 表单的应用

文本框得到失去焦点
![文本框得到失去焦点](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/5/shiqujiaodian.gif)

```javascript
 $(function(){
		$(":input").focus(function(){
			  $(this).addClass("focus");
			  if($(this).val() ==this.defaultValue){  
                  $(this).val("");           
			  } 
		}).blur(function(){
			 $(this).removeClass("focus");
			 if ($(this).val() == '') {
                $(this).val(this.defaultValue);
             }
		});
    });
```

---
多行文本框高度变化
![多行文本框高度变化](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/5/xiangshang.gif)
```javascript
$(function(){
	    var $comment = $('#comment');//获取评论框
	    $('.up').click(function(){ //向上按钮绑定单击事件
		   if(!$comment.is(":animated")){//判断是否处于动画
				$comment.animate({ scrollTop  : "-=50" } , 400);
			}
		})
		$('.down').click(function(){//向下按钮绑定单击事件
		   if(!$comment.is(":animated")){
				$comment.animate({ scrollTop  : "+=50" } , 400);
			}
		});
	});
```

---

![复选框全选反选](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/5/quanxuanyufanxuan.gif)
```javascript
$(function(){
     //全选
     $("#CheckedAll").click(function(){
			//所有checkbox跟着全选的checkbox走。
			$('[name=items]:checkbox').attr("checked", this.checked );
	 });
	 $('[name=items]:checkbox').click(function(){
				//定义一个临时变量，避免重复使用同一个选择器选择页面中的元素，提升程序效率。
				var $tmp=$('[name=items]:checkbox');
				//用filter方法筛选出选中的复选框。并直接给CheckedAll赋值。
				$('#CheckedAll').attr('checked',$tmp.length==$tmp.filter(':checked').length);

			/*
				//一行做过多的事情需要写更多注释。复杂选择器还可能影响效率。因此不推荐如下写法。
				$('#CheckedAll').attr('checked',!$('[name=items]:checkbox').filter(':not(:checked)').length);
			*/
	 });
	  //输出值
	$("#send").click(function(){
		var str="你选中的是：\r\n";
		$('[name=items]:checkbox:checked').each(function(){
			str+=$(this).val()+"\r\n";
		})
		alert(str);
	});
});
```
---

![下拉框左右选择](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/5/zuoyou.gif)
```javascript
$(function(){
	//移到右边
	$('#add').click(function() {
	//获取选中的选项，删除并追加给对方
		$('#select1 option:selected').appendTo('#select2');
	});
	//移到左边
	$('#remove').click(function() {
		$('#select2 option:selected').appendTo('#select1');
	});
	//全部移到右边
	$('#add_all').click(function() {
		//获取全部的选项,删除并追加给对方
		$('#select1 option').appendTo('#select2');
	});
	//全部移到左边
	$('#remove_all').click(function() {
		$('#select2 option').appendTo('#select1');
	});
	//双击选项
	$('#select1').dblclick(function(){ //绑定双击事件
		//获取全部的选项,删除并追加给对方
		$("option:selected",this).appendTo('#select2'); //追加给对方
	});
	//双击选项
	$('#select2').dblclick(function(){
	   $("option:selected",this).appendTo('#select1');
	});
});
```
---

![表单验证](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/5/biaodanyanzheng.gif)
```javascript
$(function(){
		//如果是必填的，则加红星标识.
		$("form :input.required").each(function(){
			var $required = $("<strong class='high'> *</strong>"); //创建元素
			$(this).parent().append($required); //然后将它追加到文档中
		});
         //文本框失去焦点后
	    $('form :input').blur(function(){
			 var $parent = $(this).parent();
			 $parent.find(".formtips").remove();
			 //验证用户名
			 if( $(this).is('#username') ){
					if( this.value=="" || this.value.length < 6 ){
					    var errorMsg = '请输入至少6位的用户名.';
                        $parent.append('<span class="formtips onError">'+errorMsg+'</span>');
					}else{
					    var okMsg = '输入正确.';
					    $parent.append('<span class="formtips onSuccess">'+okMsg+'</span>');
					}
			 }
			 //验证邮件
			 if( $(this).is('#email') ){
				if( this.value=="" || ( this.value!="" && !/.+@.+\.[a-zA-Z]{2,4}$/.test(this.value) ) ){
                      var errorMsg = '请输入正确的E-Mail地址.';
					  $parent.append('<span class="formtips onError">'+errorMsg+'</span>');
				}else{
                      var okMsg = '输入正确.';
					  $parent.append('<span class="formtips onSuccess">'+okMsg+'</span>');
				}
			 }
		}).keyup(function(){
		   $(this).triggerHandler("blur");
		}).focus(function(){
	  	   $(this).triggerHandler("blur");
		});//end blur

		
		//提交，最终验证。
		 $('#send').click(function(){
				$("form :input.required").trigger('blur');
				var numError = $('form .onError').length;
				if(numError){
					return false;
				} 
				alert("注册成功,密码已发到你的邮箱,请查收.");
		 });

		//重置
		 $('#res').click(function(){
				$(".formtips").remove(); 
		 });
})
```
---
### 52表格应用

![表格变色](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/5/biaogebianse.gif)
```javascript
 $(function(){
		$("tbody>tr:odd").addClass("odd");
		$("tbody>tr:even").addClass("even");
		$('tbody>tr').click(function() {
			//判断当前是否选中
			var hasSelected=$(this).hasClass('selected');
			//如果选中，则移出selected类，否则就加上selected类
			$(this)[hasSelected?"removeClass":"addClass"]('selected')
				//查找内部的checkbox,设置对应的属性。
				.find(':checkbox').attr('checked',!hasSelected);
		});
		// 如果复选框默认情况下是选择的，则高色.
		$('tbody>tr:has(:checked)').addClass('selected');
  });
```
---

![表格展开伸缩](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/5/biaogezhankai.gif)
```javascript
$(function(){
	$('tr.parent').click(function(){   // 获取所谓的父行
			$(this)
				.toggleClass("selected")   // 添加/删除高亮
				.siblings('.child_'+this.id).toggle();  // 隐藏/显示所谓的子行
	}).click();
});
```
---

![表格内容过滤](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/5/neirongguolv.gif)
```javascript
  $(function(){
       $("#filterName").keyup(function(){
	      $("table tbody tr")
					.hide()
					.filter(":contains('"+( $(this).val() )+"')")
					.show();
	   }).keyup();
  });
```
---
### 53其他应用

![控制字体大小](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/5/xiangshangxiangxia.gif)
```javascript
	$(function(){
		$("span").click(function(){
			var thisEle = $("#para").css("font-size"); 
			var textFontSize = parseInt(thisEle , 10);
			var unit = thisEle.slice(-2); //获取单位
			var cName = $(this).attr("class");
			if(cName == "bigger"){
				   if( textFontSize <= 22 ){
						textFontSize += 2;
					}
			}else if(cName == "smaller"){
				   if( textFontSize >= 12  ){
						textFontSize -= 2;
					}
			}
			$("#para").css("font-size",  textFontSize + unit);
		});
	});
```
---

![选项卡](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/5/xuanxiangka.gif)
```javascript
$(function(){
	    var $div_li =$("div.tab_menu ul li");
	    $div_li.click(function(){
			$(this).addClass("selected")            //当前<li>元素高亮
				   .siblings().removeClass("selected");  //去掉其它同辈<li>元素的高亮
            var index =  $div_li.index(this);  // 获取当前点击的<li>元素 在 全部li元素中的索引。
			$("div.tab_box > div")   	//选取子节点。不选取子节点的话，会引起错误。如果里面还有div 
					.eq(index).show()   //显示 <li>元素对应的<div>元素
					.siblings().hide(); //隐藏其它几个同辈的<div>元素
		}).hover(function(){
			$(this).addClass("hover");
		},function(){
			$(this).removeClass("hover");
		})
	})
```
---

![网页换肤](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/5/shiqujiaodian.gif)
```javascript
$(function(){
			var $li =$("#skin li");
			$li.click(function(){
				switchSkin( this.id );
			});
			var cookie_skin = $.cookie( "MyCssSkin");
			if (cookie_skin) {
				switchSkin( cookie_skin );
			}
		});
		function switchSkin(skinName){
				 $("#"+skinName).addClass("selected")                 //当前<li>元素选中
							  .siblings().removeClass("selected");  //去掉其它同辈<li>元素的选中
				$("#cssfile").attr("href","css/"+ skinName +".css"); //设置不同皮肤
				$.cookie( "MyCssSkin" ,  skinName , { path: '/', expires: 10 });
		}
```

