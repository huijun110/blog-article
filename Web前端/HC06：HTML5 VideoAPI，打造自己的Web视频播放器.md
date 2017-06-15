���Ľ�ʹ��HTML5�ṩ��VideoAPI��һ���Զ������Ƶ����������Ҫ�õ�HTML5�ṩ��video��ǩ���Լ�HTML5�ṩ�Ķ�JavascriptAPI����չ��

![video](../../image/1608/video/video.jpg)

һ������֪ʶ
===================================
1.�÷�
--------------------
```
<video src="./video/mv.mp4"></video>
```
**ע��**
audio��videoԪ�ر���ͬʱ������ʼ�ͽ�����ǩ������ʹ��`<audio />`�����Ŀ�Ԫ���﷨��ʽ��

2.��ҪHTML����
-----------------------
**controls**��ontrol��������ָ����ԣ������û���ʾ�ؼ������粥�Ű�ť��ÿ��������еĲ��ſؼ�����̫һ��������;��һ���������Կ��ƿ�ʼ�ͽ�����������λ�ú͵�������
**autoplay**��autoplay��������ָ����ԣ�����Ƶ�ھ��������ϲ��š����������autoplay���ԣ��������û��������Ű�ť�ŻᲥ����Ƶ�ļ���
**loop**��loop��(ѭ������)�������������Ƶ����ĩβʱ���ٴ�ͷ��ʼ���²���
**preload**��auto��mete��none��������������������Ƶ
   + auto������������������ļ����Ա��û��������Ű�ťʱ���ܲ��š���Ȼ�����ع����Ǻ�̨���еģ���ҳ�ÿͲ��صȴ�������ɣ�������Ȼ��������鿴��ҳ��
   + meta������������Ȼ�ȡ��Ƶ�ļ���ͷ�����ݿ飬�Ӷ�����ȷ��һЩ������Ϣ��������Ƶ����ʱ����
   + none��**�������������Ԥ�����ء�ǡ����������Щֵ�����Խ�ʡ����

���û������preload���ԣ���������Լ������Ƿ�Ԥ�������ˡ�����һ�㣬��ͬ������Ĵ���ʽҲ��һ���������������auto��ΪĬ��ֵ����Firefox��Ĭ��ֵ��metadata��������Ҳ����ע�⣬���preload����Ҳ���Ǳ����ϸ�ִ�еĹ��򣬶�ֻ�����������Ľ��顣���ݾ����������������Ժ���������á�����Щ�ɰ汾��������ݲ�������preload���ԡ���

3.�����¼�
-----------------
�¼�����    |    ����    |
------------|----------|
oncanplay| ���ļ��������Կ�ʼ����ʱ���еĽű����������㹻��ʼʱ����|
ontimeupdate    |    ������λ�øı�ʱ�����統�û������ý����һ����ͬ��λ��ʱ�����еĽű���    |
onended    |    ��ý���ѵ����βʱ���еĽű����ɷ������ơ���л�ۿ���֮�����Ϣ����    |

4.���÷���
------------------
��������    |    ����    |
------------|-----------|
play()        |    ��ʼ������Ƶ/��Ƶ    |
pause()     |    ��ͣ��ǰ���ŵ���Ƶ/��Ƶ    |

5.����API����
-----------------
��������    |    ����        |
------------|-------------|
duration    |    ���ص�ǰ��Ƶ/��Ƶ�ĳ��ȣ�����ƣ�    |
paused        |    ���û򷵻���Ƶ/��Ƶ�Ƿ���ͣ    |
currentTime|    ���û򷵻���Ƶ/��Ƶ�еĵ�ǰ����λ�ã�����ƣ�|
ended    |    ������Ƶ/��Ƶ�Ĳ����Ƿ��ѽ���    |

�������ԡ��¼���������鿴[w3school](http://www.w3school.com.cn/tags/html_ref_audio_video_dom.asp)

���������Լ��Ĳ�����
============================
����ʹ��JavaScript���Ʋ��ſؼ�����Ϊ���Զ��岥�ſؼ�����ʵ�����¹��ܣ�
+ ����HTML+CSS����һ���Լ��Ĳ��ſؼ�����Ȼ��λ����Ƶ���·�
+ ��Ƶ����loadingЧ��
+ ���š���ͣ
+ ��ʱ���͵�ǰ����ʱ����ʾ
+ ���Ž�����
+ ȫ����ʾ

1.���ſؼ�
------------------
```html
<body>
<figure>
    <figcaption>��Ƶ������</figcaption>
    <div class="player">
        <video src="./video/mv.mp4"></video>
        <div class="controls">
            <!-- ����/��ͣ -->
            <a href="javascript:;" class="switch fa fa-play"></a>
            <!-- ȫ�� -->
            <a href="javascript:;" class="expand fa fa-expand"></a>
            <!-- ������ -->
            <div class="progress">
                <div class="loaded"></div>
                <div class="line"></div>
                <div class="bar"></div>
            </div>
            <!-- ʱ�� -->
            <div class="timer">
                <span class="current">00:00:00</span> /
                <span class="total">00:00:00</span>
            </div>
            <!-- ���� -->
        </div>
    </div>
</figure>
```
������ȫ��HTML���룬`.controls`����ǲ��ſؼ�HTML������CSS���룺
```html
<link rel="stylesheet" href="./css/font-awesome.css">
<link rel="stylesheet" href="./css/player.css">
```
Ϊ����ʾ���Ű�ť��ͼ����ʹ��������ͼ��

2.��Ƶ����loadingЧ��
--------------------------
һ��ʼ��������Ƶ����һ������ͼƬ������ȵ���Ƶ������ɿ��Բ���ʱ����ʾ��Ƶ
CSS��
```css
.player {
    width: 720px;
    height: 360px;
    margin: 0 auto;
    background: #000 url(../../images/loading.gif) center/300px no-repeat;
    position: relative;
}

video {
    display: none;
    height: 100%;
    margin: 0 auto;
}
```

3.���Ź���
-------------------
�����ǿ�ʼдjavascript����ɣ����������Ȼ�ȡҪ�õ���DOMԪ�أ�
```js
var video = document.querySelector("video");
var isPlay = document.querySelector(".switch");
var expand = document.querySelector(".expand");
var progress = document.querySelector(".progress");
var loaded = document.querySelector(".progress > .loaded");
var currPlayTime = document.querySelector(".timer > .current");
var totalTime = document.querySelector(".timer > .total");
```
����Ƶ���Բ���ʱ����ʾ��Ƶ
```js
//����Ƶ�ɲ��ŵ�ʱ��
video.oncanplay = function(){
      //��ʾ��Ƶ
      this.style.display = "block";
      //��ʾ��Ƶ��ʱ��
      totalTime.innerHTML = getFormatTime(this.duration);
};
```

4.���š���ͣ
----------------------
������Ű�ťʱ��ʾ��ͣͼ�꣬�ڲ��ź���ͣ״̬֮���л�ͼ��
```js
//���Ű�ť����
isPlay.onclick = function(){
        if(video.paused) {
            video.play();
        } else {
            video.pause();
        }
        this.classList.toggle("fa-pause");
};
```

5.��ʱ���͵�ǰ����ʱ����ʾ
------------------------
ǰ���������ʵ�Ѿ���������ش��룬��ʱ����ֻ��Ҫ�ѻ�ȡ���ĺ�����ת����������Ҫ��ʱ���ʽ���ɣ��ṩ`getFormatTime()`������
```js
function getFormatTime(time) {
        var time = time || 0;

        var h = parseInt(time/3600),
            m = parseInt(time%3600/60),
            s = parseInt(time%60);
        h = h < 10 ? "0"+h : h;
        m = m < 10 ? "0"+m : m;
        s = s < 10 ? "0"+s : s;

        return h+":"+m+":"+s;
    }
```

6.���Ž�����
-----------------------
```
//���Ž���
video.ontimeupdate = function(){
    var currTime = this.currentTime,    //��ǰ����ʱ��
    duration = this.duration;       // ��Ƶ��ʱ��
    //�ٷֱ�
    var pre = currTime / duration * 100 + "%";
    //��ʾ������
    loaded.style.width = pre;

     //��ʾ��ǰ���Ž���ʱ��
    currPlayTime.innerHTML = getFormatTime(currTime);
};
```
�����Ϳ���ʵʱ��ʾ�������ˣ���ʱ�����ǻ���Ҫ���������������Ծ���ţ������ǵ������ʱ�����Ƶ��ת����ǰʱ��㲥�ţ�
```
//��Ծ����
progress.onclick = function(e){
    var event = e || window.event;
    video.currentTime = (event.offsetX / this.offsetWidth) * video.duration;
};
```

7.ȫ����ʾ
----------------------
������ܿ���ʹ��HTML5�ṩ��ȫ��API��`webkitRequestFullScreen`ʵ�֣���`video`�޹أ�
```
//ȫ��
expand.onclick = function(){
     video.webkitRequestFullScreen();
};
```

[����ʾ����Դ���������](http://www.mybry.com/demo/html-css/HTML5%E8%A7%86%E9%A2%91API%E7%AE%80%E5%8D%95%E4%BD%BF%E7%94%A8/)

[github]()

��������firefox��IE��ȫ�����ܲ����ã����������ˣ�ȫ��API�����webkit�ں˵ġ�