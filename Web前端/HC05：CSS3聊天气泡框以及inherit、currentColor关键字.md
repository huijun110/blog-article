![Ч��ͼ](../../image/1607/main.png)

Ч������ͼ��ʾ����Ҫ�õ�CSS3��α��`::after`��`::before`���Լ�Բ�Ǳ߿�`border-radius`���ԡ�������������ݿ򣬿��������ַ�ʽʵ��С���ǣ�
+ ��ͳ��ʽ������CSS��С���ǣ����õ���͸�������ͱ߿�����`transparent`��Ӧ�á�
+ CSS3��`transform`���Ե�ʹ��

Ȼ��ͨ��`position`��λ�����ʵ�λ�á�

���⣬���Ļ��ὲһ��CSS��`inherit`����ֵ��֪ʶ��

#ʵ�����ݿ�

HTML���Ҳ�ܼ򵥣���һ��DIV�������ǲ���ʹ����CSS�����ǵ�֪ʶ��

HTML��
```html
<div class="message1">
    Demos ������ʾ������Ƭ�� - ���㣬��ӭ�������㣬http://www.mybry.com
</div>

<div class="message2">
    Demos ������ʾ������Ƭ�� - ���㣬��ӭ�������㣬http://www.mybry.com
</div>
```
CSS��
```css
.message1,.message2 {
    width: 200px;
    height: 80px;
    margin: 100px auto;
    background-color: green;
    border-bottom-color:green;/*Ϊ�˸�afterαԪ���Զ��̳�*/
    color: #fff;
    font-size: 12px;
    font-family: Arial;
    line-height: 18px;
    padding: 5px 12px 5px 12px;
    box-sizing: border-box;
    border-radius: 6px;
    position: relative;
    word-break: break-all;
}
.message1::after {
    content: '';
    position: absolute;
    top: 0;
    right: -24px;
    width: 20px;
    height: 20px;
    border-width: 0 0 20px 20px;
    border-style: solid;
    border-bottom-color: inherit;   /*�Զ��̳и�Ԫ�ص�border-bottom-color*/
    border-left-color: transparent;
    border-radius: 0 0 60px 0;
}
/** ͨ����С��������ת45�Ƚ�� **/
.message2::before {
    content: '';
    position: absolute;
    top: 50%;
    left: -5px;
    width: 10px;
    height: 10px;
    margin-top: -10px;
    background: inherit;/*�Զ��̳и�Ԫ�صı���*/
    transform: rotate(45deg);
}

/** ͨ���������ν�� */
/*.message2::before {*/
    /*content: '';*/
    /*position: absolute;*/
    /*top: 50%;*/
    /*left: -20px;*/
    /*width: 0px;*/
    /*height: 0px;*/
    /*margin-top: -10px;*/
    /*border-width: 10px;*/
    /*border-style: solid;*/
    /*border-color: transparent green transparent transparent;*/
/*}*/
```
���Ͼ���ȫ�����롣
�����С������ʹ����inherit����ֵ��ͨ������������ת45���γɶ�������Ƕ��õ���

# ������������inherit�ؼ���

���ܾ�������˶�֪��inherit����ؼ��֣����Ǻܶ��˿�����ʼ���ն�ûʵ���ù������������Լ�������û�У��ڲ�ѯCSS�ĵ�ʱ��ϰ���Եĺ�������ֱ��������CSS���ء��Ȿ�顣

`inherit`���������κ�CSS�����У����w3cschool�ĵ��о��Ѿ������ˣ������ǰ󶨵���Ԫ�صļ���ֵ����αԪ����˵�����ȡ���ɸ�αԪ�ص�����Ԫ�أ���������˵��Ҫ�ѱ�Ԫ�ص������趨Ϊ��ҳ�������������ͬ���㲢����Ҫ�ظ�ָ���������ԣ�ֻ��Ҫ����`inherit`�����Լ��ɣ�
```css
input,select,button { font: inherit }
```
������ƣ�Ҫ�ѳ����ӵ���ɫ�趨Ϊ��ҳ���������ı���ͬ������Ҫ��`inherir`����������Ĵ��룺
HTML��
```html
<div class="article">
    <p>Demos ������ʾ������Ƭ�� - ���� | ������Ψ������ͺù��ﲻ�ɹ���!</p>
    <a href="http://www.mybry.com/demo/">Demos</a>
</div>
```
CSS��
```css
.article {
      font-family: "Microsoft YaHei";
      font-size: 14px;
      color: red;
}
```
Ч����
![Ч��ͼ](../../image/1607/1.png)

��ʱ���ֵ���ɫ�Ǻ�ɫ����������Ĭ������ɫ�������ᱻ�ı䣬�������Ƕ�֪���ģ���ô�����ó�����Ҳ�Ǹ���Ԫ��һ���ĺ�ɫ�أ���ʱ����ֻ��Ҫ��������inherit���ɣ�
```css
.article a { color: inherit; }
```
Ч����
![Ч��ͼ](../../image/1607/2.png)

���inherit���ڱ���ɫ��ͬ�ǳ����ã�������Ҫע����ǣ���Ҫ��Ԫ���������Ե�inherit�ؼ�����Ч����Ԫ�ر������ù�ʹ��inheritΪֵ�����ԡ�

#CSS3��currentColor�ؼ���

��֮���ƵĻ���һ���µ�CSS��ɫ���ԣ�`currentColor`�������������CSS��ɫ�������棩�淶�������ӵģ����Ǵ�SVG�����������ģ�����ؼ��ֲ�û�а󶨵�һ���̶�����ɫֵ������һֱ������Ϊcolor��ʵ���ϣ�����CSS����ʷ������һ����������Ȼ���ܺ����ޣ���������Ǹ�������

�ٸ����ӣ����������������е�ˮƽ�ָ��ߣ�����`<hr>`Ԫ�أ��Զ����ı���ɫ����һ�¡�
��������������������ˮƽ�ߣ�
```css
.article hr {
      height: .5em;
}
```
Ĭ��������������ģ�
![Ч��ͼ](../../image/1607/3.png)
 ��ʱ����� `currentColor`
```css
.article hr {
      height: .5em;
      background: currentColor;
}
```
Ч����
![Ч��ͼ](../../image/1607/4.png)

�����ڰ�������ɫ��Ϊ��ɫ��ʱ�����ǻᱣ�ָ�������ɫһ��

[����CSS3�߿���Ч����鿴��ҳ��](http://www.mybry.com/demo/html-css/CSS3�߿�Ч����ȫ.html)

*****************************************************
**�ο����ϣ�**

��CSS���ܡ�[��]Lea Verou (����) ��[��]CSSħ�� (����)��ͼ������������е������