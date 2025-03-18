## OneClickMultiPage 一键打开多个搜索引擎进行搜索（集成一键签到）

### 此网页主要是解决批量搜索问题，有时候我使用多个搜索引擎，一个搜索词要搜好几次，特别慢，所以写了一个html网页直接进行批量搜索。

### 写完以后发现，既然可以实现批量打开多个网页不就可以一键打开多个网页签到吗？所以我在顶部直接把一键签到也加上了（现在设置成浏览器主页就不怕漏签到了）

### 一键多页 (OneClickMultiPage)为用单个html文件，非常极简（主要我也不会美化网页，这样简洁手机浏览器也可以用安慰自己）想自定义为自己的网站非常简单直接替换文件里的http链接就可以直接使用了

搜索代码`var urlAll = ["`就可以看到默认网站



### 使用请关闭浏览器弹窗拦截，否则打开一个网页以后就停了

<a href="https://www.52pojie.cn/home.php?mod=space&uid=750418" target="_blank">吾爱破解-大毛孩</a>
<a href="https://github.com/nihongvfx/OneClickMultiPage/tree/main" target="_blank">Github源码</a>
<a href="https://www.jybsf.com/" target="_blank">自用网站效果展示</a>



### 示例网站

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>批量搜索OneClickMultiPage</title>
<script>
	function openallweb() 
	{
    var j = 0;
	var timeout = document.getElementById("myInputtime").value;
	var text = document.getElementById("myInput").value;
	//需要同时签到的所有网站
	var urlAll = ["https://www.52pojie.cn","https://tieba.baidu.com","https://bbs.binmt.cc/k_misign-sign.html","https://jtzl.jtj.gz.gov.cn"
	];

	function openTimer(nextIndex) {
		//便利完成则退出循环,并关闭当前页,并取消关闭提示
		if(nextIndex >= urlAll.length) {
			window.opener = null;
			//window.open("about:blank", "_self");
			//window.close();
			return;
		};
		var urls = new Array();
		for(i = 0; i < urlAll.length; i++) {
			urls[i] = urlAll[i];
			urls[i] = urls[i].replace(/%s/g, text);//替换%s
		}

		//间隔时间（毫秒，1秒=1000毫秒）可以自行设置
		var winObj = window.open(urls[j], '_blank');
		setTimeout(function() {
			openTimer(++j);
			
		}, timeout);
	}
	openTimer(0);
  }

  function openPersonalwebpage() 
  {
    var j = 0;
	var timeout = document.getElementById("myInputtime").value;
	var text = document.getElementById("myInput").value;
	//打开个人网站
	var urlAll = ["https://www.jybsf.com","https://www.输入你的网站.com"
	];

	function openTimer(nextIndex) {
		//便利完成则退出循环,并关闭当前页,并取消关闭提示
		if(nextIndex >= urlAll.length) {
			window.opener = null;
			//window.open("about:blank", "_self");
			//window.close();
			return;
		};
		var urls = new Array();
		for(i = 0; i < urlAll.length; i++) {
			urls[i] = urlAll[i];
			urls[i] = urls[i].replace(/%s/g, text);//替换%s
		}

		//间隔时间（毫秒，1秒=1000毫秒）可以自行设置
		var winObj = window.open(urls[j], '_blank');
		setTimeout(function() {
			openTimer(++j);
			
		}, timeout);
	}
	openTimer(0);
  }

  function openWebse() 
  {
    var j = 0;
	var timeout = document.getElementById("myInputtime").value;
	var text = document.getElementById("myInput").value;
	//需要打开的搜索引擎
	var urlAll = ["https://www.bing.com/search?q=%s","https://www.google.com.hk/search?q=%s","https://www.baidu.com/s?wd=%s","http://www.zhihu.com/search?q=%s","https://yandex.com/search/?text=%s"];

	function openTimer(nextIndex) {
		//便利完成则退出循环,并关闭当前页,并取消关闭提示
		if(nextIndex >= urlAll.length) {
			window.opener = null;
			//window.open("about:blank", "_self");
			//window.close();
			return;
		};
		var urls = new Array();
		for(i = 0; i < urlAll.length; i++) {
			urls[i] = urlAll[i];
			urls[i] = urls[i].replace(/%s/g, text);//替换%s
		}

		//间隔时间（毫秒，1秒=1000毫秒）可以自行设置
		var winObj = window.open(urls[j], '_blank');
		setTimeout(function() {
			openTimer(++j);
			
		}, timeout);
	}
	openTimer(0);
  }

  function openWebcxy() 
  {
    var j = 0;
	var timeout = document.getElementById("myInputtime").value;
	var text = document.getElementById("myInput").value;
	//需要打开的程序员搜索
	var urlAll = ["https://github.com/search?utf8=✓&q=%s","http://www.zhihu.com/search?q=%s","https://stackoverflow.com/search?q=%s","https://juejin.im/search?query=%s&type=all","http://caniuse.com/#search=%s","http://www.runoob.com/?s=%s","https://hub.docker.com/search?q=%s&type=image"
	];

	function openTimer(nextIndex) {
		//便利完成则退出循环,并关闭当前页,并取消关闭提示
		if(nextIndex >= urlAll.length) {
			window.opener = null;
			//window.open("about:blank", "_self");
			//window.close();
			return;
		};
		var urls = new Array();
		for(i = 0; i < urlAll.length; i++) {
			urls[i] = urlAll[i];
			urls[i] = urls[i].replace(/%s/g, text);//替换%s
		}

		//间隔时间（毫秒，1秒=1000毫秒）可以自行设置
		var winObj = window.open(urls[j], '_blank');
		setTimeout(function() {
			openTimer(++j);
			
		}, timeout);
	}
	openTimer(0);
  }

  function openWebvideo() 
  {
    var j = 0;
	var timeout = document.getElementById("myInputtime").value;
	var text = document.getElementById("myInput").value;
	//需要打开的视频搜索
	var urlAll = ["https://www.youtube.com/results?search_query=%s","https://www.bilibili.com/search?keyword=%s","https://www.douyin.com/search/%s","https://www.kuaishou.com/search/video?searchKey=%s","https://www.acfun.cn/search?keyword=%s"];

	function openTimer(nextIndex) {
		//便利完成则退出循环,并关闭当前页,并取消关闭提示
		if(nextIndex >= urlAll.length) {
			window.opener = null;
			//window.open("about:blank", "_self");
			//window.close();
			return;
		};
		var urls = new Array();
		for(i = 0; i < urlAll.length; i++) {
			urls[i] = urlAll[i];
			urls[i] = urls[i].replace(/%s/g, text);//替换%s
		}

		//间隔时间（毫秒，1秒=1000毫秒）可以自行设置
		var winObj = window.open(urls[j], '_blank');
		setTimeout(function() {
			openTimer(++j);
			
		}, timeout);
	}
	openTimer(0);
  }


  function openWebAI() 
  {
    var j = 0;
	var timeout = document.getElementById("myInputtime").value;
	var text = document.getElementById("myInput").value;
	//需要打开的AI搜索
	var urlAll = ["https://tongyi.aliyun.com/qianwen","https://chat.deepseek.com/","https://zhida.zhihu.com","https://chatgpt.com"
	];

	function openTimer(nextIndex) {
		//便利完成则退出循环,并关闭当前页,并取消关闭提示
		if(nextIndex >= urlAll.length) {
			window.opener = null;
			//window.open("about:blank", "_self");
			//window.close();
			return;
		};
		var urls = new Array();
		for(i = 0; i < urlAll.length; i++) {
			urls[i] = urlAll[i];
			urls[i] = urls[i].replace(/%s/g, text);//替换%s
		}

		//间隔时间（毫秒，1秒=1000毫秒）可以自行设置
		var winObj = window.open(urls[j], '_blank');
		setTimeout(function() {
			openTimer(++j);
			
		}, timeout);
	}
	openTimer(0);
  }

</script>





</head>
<body>
<h1>批量搜索：使用请关闭浏览器弹窗拦截</h1>



<button onclick="openallweb()">一键签到</button>&nbsp<button onclick="openPersonalwebpage()">个人网站</button>&nbsp<button onclick="openWebAI()">AI</button>
<p>
	网页打开间隔时间毫秒
	<input type="text" value="3" id="myInputtime">
</p>
	<input type="text" value="搜索内容" id="myInput">
	<button onclick="openWebse()">搜索</button>
	<button onclick="openWebcxy()">程序员</button>
	<button onclick="openWebvideo()">视频</button>


<footer>
    <p>版权所有 &copy; 2025
        <a href="https://www.52pojie.cn/home.php?mod=space&uid=750418" target="_blank">吾爱破解-大毛孩</a>
        <a href="https://github.com/nihongvfx/OneClickMultiPage/tree/main" target="_blank">Github源码</a>
        <a href="https://www.jybsf.com/" target="_blank">自用网站效果展示</a>
    所有人免费使用
    </p>
	
</footer>

</body>

</html>
```
