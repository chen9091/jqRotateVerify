# jqRotateVerify
jQuery滑动图片角度插件，仿baidu登录，用canvas画图 rotate转动
## 使用
```
var myRotateVerify = new RotateVerify('#rotateWrap',{
	initText:'滑动将图片转正',//默认
	slideImage:['image/1.jpg','image/2.jpg','image/4.jpg'],//arr  [imgsrc1,imgsrc2] 或者str 'imgsrc1'
	slideAreaNum:10,// 误差范围角度 +- 10(默认)
    getSuccessState:function (res) {//验证通过 返回  true;
	console.log('例1' + res);
    }
})
```
## 参数

 - initText  ：'滑动将图片转正',//默认
 -  slideImage ：图片的src,可以为一个图片的src,也可以是多张图片的 src 数组 
 - slideAreaNum：10,// 误差范围角度 +- 10(默认)
 - getSuccessState：验证成功回调  返回true
## 重置方法

```
resetSlide()
//myRotateVerify.resetSlide()
```
## 获取验证状态

```
verifyState  
//myRotateVerify.verifyState
```

```
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
		<script src="jquery.min.js" type="text/javascript" charset="utf-8"></script>
		<script src="jqRotateVerify.js" type="text/javascript" charset="utf-8"></script>
	</head>
	<body>
		<div id="rotateWrap" style="margin-top:50px;">
			
		</div>
		<div style="text-align: center;margin-top: 50px;">
			<button type="button" id="resetBtn" style="height: 30px;">重置</button>
			<button type="button" id="testBtn" style="height: 30px;">状态测试</button>
		</div>
		<div id="rotateWrap2" style="margin-top:50px;">
			
		</div>
		<script type="text/javascript">
			$(function(){
				//1
				var myRotateVerify = new RotateVerify('#rotateWrap',{
					initText:'滑动将图片转正',//默认
					slideImage:['image/1.jpg','image/2.jpg','image/4.jpg'],//arr  [imgsrc1,imgsrc2] 或者str 'imgsrc1'
					slideAreaNum:10,// 误差范围角度 +- 10(默认)
				    getSuccessState:function (res) {//验证通过 返回  true;
				        console.log('例1' + res);
				    }
				})
				//重置 
				$("#resetBtn").on('click',function(){
					myRotateVerify.resetSlide();
				})
				//可拿到 验证状态 
				$("#testBtn").on('click',function(){
					alert(myRotateVerify.verifyState);
				})
				
				//2
				var myRotateVerify2 = new RotateVerify('#rotateWrap2',{
					initText:'滑动将图片转正',//默认
					slideImage:'image/4.jpg',//arr  [imgsrc1,imgsrc2] 或者str 'imgsrc1'
					slideAreaNum:10,// 误差范围角度 +- 10(默认)
				    getSuccessState:function (res) {//验证通过 返回  true;
				        console.log('例2' + res);
				    }
				})
			})
		</script>
	</body>
</html>
```
