<h1>这是一个个人风格的markdown设置</h1>

- 以sublime的markdown preview（以下简称MP）为工具生成的markdown的一些设置

- 除了MP设置，其他设置请直接看源文件

[TOC]

## 样式调整

### 目录

- 固定在左栏

- 设置为有滚动条

- 一级标题目录加粗

### 代码块

- 代码块自动换行，而不是默认的加滚动条

### 其他

- 鼠标hover变手、颜色加深

## 功能按钮

前进、后退、顶部、底部功能

## 自带bgm

- 需下载至本地，并生成为html，用MP在浏览器预览或者用预览markdown的软件打开是不会有音乐的

- 回车键暂停或播放

## MP的设置

```
[
    { "keys": ["alt+m"], "command": "markdown_preview", "args": { "target": "browser"} }
]

```



<div class = "location-a">
    <a class = "location back-a" href="javascript:history.go(-1);">后退</a>
    <a class = "location forward-a" href="javascript:history.go(1);">前进</a>
    <a class = "location top-a" onclick="scrollBy( 0, -99999 )">顶部</a>
    <a class = "location bottom-a" onclick="scrollBy( 0, 99999 )">底部</a>
</div>

<style type="text/css">

div.location-a{
    width: 10%;
    position: fixed;right: 0px;top: 0px;
}

a.location:hover{
    cursor: pointer;
    color:blue;
}

a.back-a{
    position: absolute;right: 5em;top: 1em;
}

a.forward-a{
    position: absolute;right: 2em;top: 1em;
}

a.top-a{
    position: absolute;right: 2em;top: 3em;
}

a.bottom-a{
    position: absolute;right: 2em;top: 5em;
}

div.toc{
    overflow:scroll; width:23%; height:100%;
    position: fixed;left: 2%;top: 0px;
    padding-top: 2%;
}

body{
    width: 65%;
    margin-left: 26%;
}

div.toc>ul>li>a{
    font-weight: bold;
}

.markdown-body pre>code{
    white-space: pre-wrap;
    word-break:break-all;
}

<audio src="resource/夏后&小贱-输给时间.mp3" hidden="true" autoplay="true" loop="true" id = "mp3">
</audio>

<script>
document.onkeydown=function(event){
           var e = event || window.event || arguments.callee.caller.arguments[0];
            if(e && e.keyCode==13){ // enter 键
                var x = document.getElementById("mp3");
                if( x.paused ) {
                    x.play();
                } else {
                    x.pause();
                }
            }
        };
function audioPlay( $audioObj ){
    $audioObj.play();
}
function audioPause( $audioObj ){
    $audioObj.pause();
}
</script>