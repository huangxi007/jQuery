## 第5章

---
### 51 表单的应用

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
    })
    ```

![多行文本框高度变化](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/5/xiangshang.gif)

![复选框全选反选](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/5/quanxuanyufanxuan.gif)

![下拉框左右选择](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/5/zuoyou.gif)

![表单验证](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/5/biaodanyanzheng.gif)

---
### 52表格应用

![表格变色](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/5/biaogebianse.gif)

![表格展开伸缩](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/5/biaogezhankai.gif)

![表格内容过滤](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/5/neirongguolv.gif)

---
### 53其他应用

![控制字体大小](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/5/xiangshangxiangxia.gif)

![选项卡](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/5/xuanxiangka.gif)

![网页换肤](https://raw.githubusercontent.com/qianjilou/jQuery/master/images/5/shiqujiaodian.gif)

