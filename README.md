## OneClickMultiPage 一键打开多个搜索引擎进行搜索（集成一键签到）
### This website mainly addresses the issue of batch search,Sometimes I use multiple search engines,A search term needs to be searched several times,Efficiency is very low.So I wrote an html web page to directly conduct batch search

### After I finished writing, I found that since it was possible to batch open multiple web pages, wouldn't it be possible to open multiple web pages for check-in with one click? So I directly added one-click check-in at the top as well(Now, if you set it to the browser's home page, you don't have to worry about missing a check-in)

### OneClickMultiPage(一键多页)is a single 100% html file,It's extremely minimalist. Customizing it to your own website is very simple. Just replace the http links in the file and you can use it directly.

Search for the code 'var urlAll = [' to see the default website.

### 此网页主要是解决批量搜索问题，有时候我使用多个搜索引擎，一个搜索词要搜好几次，效率很低。所以写了一个html网页直接进行批量搜索。

### 我写完以后发现，既然可以实现批量打开多个网页不就可以一键打开多个网页签到吗？所以我在顶部直接把一键签到也加上了（现在设置成浏览器主页就不怕漏签到了）

### 一键多页 (OneClickMultiPage)为单个100%的html文件，非常极简,想自定义为自己网站非常简单直接替换文件里的http链接就可以直接使用了。

搜索代码`var urlAll = ["`就可以看到默认网站。


### 使用请关闭浏览器弹窗拦截，否则打开一个网页以后就停了

<a href="https://www.jybsf.com/" target="_blank">网站效果展示Website effect Display</a>



### 示例网站HTML
```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>批量搜索OneClickMultiPage</title>
<style>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
        font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }
    
    body {
        background-color: #0f0f0f;
        color: #ffffff;
        min-height: 100vh;
        padding: 2rem;
        line-height: 1.6;
    }
    
    .container {
        max-width: 800px;
        margin: 0 auto;
        text-align: center;
    }
    
    h1 {
        color: #00ffcc;
        margin: 2rem 0;
        text-shadow: 0 0 10px rgba(0, 255, 204, 0.7);
        font-size: 2.2rem;
    }
    
    .btn-group {
        margin: 2rem 0;
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        gap: 1rem;
    }
    
    button {
        background: linear-gradient(145deg, #1a1a1a, #2d2d2d);
        color: #ffffff;
        border: none;
        padding: 0.8rem 1.5rem;
        border-radius: 8px;
        cursor: pointer;
        font-size: 1rem;
        transition: all 0.3s ease;
        position: relative;
        overflow: hidden;
        box-shadow: 0 4px 6px rgba(0, 0, 0, 0.3);
    }
    
    button::before {
        content: '';
        position: absolute;
        top: 0;
        left: -100%;
        width: 100%;
        height: 100%;
        background: linear-gradient(90deg, transparent, rgba(0, 255, 204, 0.2), transparent);
        transition: all 0.5s ease;
    }
    
    button:hover {
        transform: translateY(-3px);
        box-shadow: 0 6px 12px rgba(0, 255, 204, 0.2);
        color: #00ffcc;
    }
    
    button:hover::before {
        left: 100%;
    }
    
    button:active {
        transform: translateY(1px);
        box-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
    }
    
    .input-group {
        margin: 2rem 0;
    }
    
    input {
        background-color: #2d2d2d;
        border: 1px solid #444;
        color: #ffffff;
        padding: 0.8rem;
        border-radius: 6px;
        margin: 0.5rem;
        width: 200px;
        transition: all 0.3s ease;
    }
    
    input:focus {
        outline: none;
        border-color: #00ffcc;
        box-shadow: 0 0 0 2px rgba(0, 255, 204, 0.2);
    }
    
    footer {
        margin-top: 4rem;
        color: #888;
        font-size: 0.9rem;
    }
    
    footer a {
        color: #00ffcc;
        text-decoration: none;
        margin: 0 0.5rem;
        transition: color 0.3s ease;
    }
    
    footer a:hover {
        color: #66ffdd;
        text-decoration: underline;
    }
    
    .note {
        color: #aaa;
        margin: 1rem 0;
        font-size: 0.9rem;
    }
</style>
<script>
	function openallweb() 
	{
	var j = 0;
	var timeout = document.getElementById("myInputtime").value;
	var text = document.getElementById("myInput").value;
	//需要同时签到的所有网站
	var urlAll = ["https://www.52pojie.cn","https://tieba.baidu.com","https://bbs.binmt.cc/k_misign-sign.html"
	];

	function openTimer(nextIndex) {
		//便利完成则退出循环,并关闭当前页,并取消关闭提示
		if(nextIndex >= urlAll.length) {
			window.opener = null;
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
	var urlAll = ["https://www.01.com","https:/www.02.cn","https:/www.03.top"
	];

	function openTimer(nextIndex) {
		if(nextIndex >= urlAll.length) {
			window.opener = null;
			return;
		};
		var urls = new Array();
		for(i = 0; i < urlAll.length; i++) {
			urls[i] = urlAll[i];
			urls[i] = urls[i].replace(/%s/g, text);
		}

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
		if(nextIndex >= urlAll.length) {
			window.opener = null;
			return;
		};
		var urls = new Array();
		for(i = 0; i < urlAll.length; i++) {
			urls[i] = urlAll[i];
			urls[i] = urls[i].replace(/%s/g, text);
		}

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
		if(nextIndex >= urlAll.length) {
			window.opener = null;
			return;
		};
		var urls = new Array();
		for(i = 0; i < urlAll.length; i++) {
			urls[i] = urlAll[i];
			urls[i] = urls[i].replace(/%s/g, text);
		}

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
		if(nextIndex >= urlAll.length) {
			window.opener = null;
			return;
		};
		var urls = new Array();
		for(i = 0; i < urlAll.length; i++) {
			urls[i] = urlAll[i];
			urls[i] = urls[i].replace(/%s/g, text);
		}

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
	var urlAll = ["https://www.doubao.com/chat","https://tongyi.aliyun.com/qianwen","https://chat.deepseek.com/","https://zhida.zhihu.com","https://chatgpt.com"
	];

	function openTimer(nextIndex) {
		if(nextIndex >= urlAll.length) {
			window.opener = null;
			return;
		};
		var urls = new Array();
		for(i = 0; i < urlAll.length; i++) {
			urls[i] = urlAll[i];
			urls[i] = urls[i].replace(/%s/g, text);
		}

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
    <div class="container">
        <h1>批量搜索工具OneClickMultiPage</h1>
        <p class="note">使用前请关闭浏览器弹窗拦截！</p>
        
        <div class="btn-group">
            <button onclick="openallweb()">批量签到</button>
            <button onclick="openPersonalwebpage()">个人网站</button>
            <button onclick="openWebAI()">AI工具</button>
        </div>
        
        <div class="input-group">
            <p>网页打开间隔时间(毫秒ms)
            <input type="text" value="1" id="myInputtime">
            </p>

            <p>搜索内容</p>
            <input type="text" value="请替换搜索内容" id="myInput">
            
            <div class="btn-group">
                <button onclick="openWebse()">批量搜索引擎</button>
                <button onclick="openWebcxy()">批量程序论坛</button>
                <button onclick="openWebvideo()">批量视频网站</button>
            </div>
        </div>
        
        <footer>
            <p>版权所有 &copy; 2026/01/13
                <a href="https://www.52pojie.cn/forum.php?mod=viewthread&tid=2015918&page=1&extra=#pid52644377" target="_blank">吾爱破解</a>
                <a href="https://github.com/nihongvfx/OneClickMultiPage/tree/main" target="_blank">Github源码</a>
                <a href="https://www.jybsf.com" target="_blank">网站效果展示</a>
                <a href="https://www.jybsf.com/pngico" target="_blank">文字转PNG和ICO</a>
                <a href="https://www.jybsf.com/ps" target="_blank">实际尺寸转PS像素计算器</a>
            </p>
        <footer>
    </div>
</body>
</html>
```

