CSS���õ���ʽ�ǿ��Բ���ģ�������[����1]

[����1]
```html
<style type="text/css">
	span{font-size: 40px;}
	.test{color:red;}
</style>

<span class="test">CSS�ĵ�Ȩ��ԭ��</span>
```
��CSS�ĵ�Ȩ��ԭ�򡱼ȿ��Եĵ���font-size:40px������ʽ���ֿ��Եõ���color�� red������ʽ�����������ͬѡ������õ���ʽ�г�ͻ���ֻ���Σ�������[����2]
[���룺CSS����г�ͻ�����]
```html
<style type="text/css">
	span{font-size: 40px;color:green}
	.test{color:red;}
</style>

<span class="test">CSS�ĵ�Ȩ��ԭ��</span>
```
��CSS�ĵ�Ȩ��ԭ����ɫ����ʲô�أ��Ƕԡ�span�����õġ�color:green���أ����ǵڡ�.test�����õġ�color:red���أ�����漰CSSѡ�����Ȩ�������ˡ�

CSS��ѡ�������Ȩ�صģ�```����ͬѡ�������ʽ�����г�ͻʱ�������Ȩ�ظߵ�ѡ������õ���ʽ��```Ȩ�صĹ����������ģ�```HTML��ǩ��Ȩ����1��class��Ȩ����10��id��Ȩ����100```������p��Ȩ����1����div em����Ȩ����1+1=2����strong.demo����Ȩ����10+1=11����#test.red����Ȩ����100+10=110.

[����2]�У�ѡ���span��Ȩ����1����.test����Ȩ����10�����ԡ�CSS�ĵ�Ȩ��ԭ�򡱵�colorӦ����red��

�������������[����3]ʱ���ֻ�����أ�
```html
<style type="text/css">
span{font-size: 40px;}
.test{color:red;}
.test2{color: green}
</style>

<span class="test test2">CSS�ĵ�Ȩ��ԭ��</span>
```
span�ı�ǩͬʱ����test��test2����class�����ǵ�Ȩ�ض���10����ô��CSS�ĵ�Ȩ��ԭ�򡱵�color�ָ����ĸ��أ�```��� CSSѡ���Ȩ����ͬ����ô��ʽ����ѭ�ͽ�ԭ���ĸ�ѡ������壬�Ͳ����ĸ�ѡ�������ʽ��```[����3]��test2���壬����color����á�.test2��������Ϊgreen��

����ı䡰.test���͡�.test2�������λ�ã���[����4]
```html
<style type="text/css">
span{font-size: 40px;}
.test2{color: green}
.test{color:red;}
</style>

<span class="test test2">CSS�ĵ�Ȩ��ԭ��</span>
```
��ô ��CSS�ĵ�Ȩ��ԭ�򡱵�color��Ϊred�ˡ�

��Ҫǿ�����Ǿͽ�ԭ��ָ����ѡ���  ���Ⱥ�˳�򣬶����ǹ�class�����Ⱥ�˳��```<span class="test test2">CSS�ĵ�Ȩ��ԭ��</span>```��```<span class="test2 test">CSS�ĵ�Ȩ��ԭ��</span>```û������

CSSѡ���Ȩ���Ǹ����ױ����Ե����⡣����ʵ�������̫ע��ѡ�����Ȩ�أ�����������򲻵���С�鷳����������[����5]
```
<style type="text/css">
#test{font-size: 14px;}
</style>

<p id="test">CSS��ѡ���Ȩ�غ���Ҫ</p>
```
������Ҫ��������Ҫ������������Ϊ��ɫ������Ӧ����ô���أ�
����һ��������ѡ��������[����6]
```html
<style type="text/css">
#test{font-size: 14px;}
#test span{color: red}
</style>

<p id="test">CSS��ѡ���Ȩ��<span>����Ҫ</span></p>
```
���������½�class����[����7]
```html
<style type="text/css">
#test{font-size: 14px;}
.font{color: red}
</style>

<p id="test">CSS��ѡ���Ȩ��<span class="font">����Ҫ</span></p>
```
�ܶ๤��ʦ�Ƽ�ʹ�÷���һ����Ϊʹ����ѡ�������Ա�������class����HTML�������࣬��ô�������е���ģ��������ʱ�����б仯����Ҫ����µĶ����ֽ�������[����8]
```html
<style type="text/css">
#test{font-size: 14px;}
#test span{color: red}
</style>

<p id="test">CSS��ѡ���Ȩ��<span>����Ҫ</span>������ҪС�Ĵ���</p>
```
Ҫ�����ǽ���С�Ĵ�������Ϊ��ɫ�����ǿ�����ô������[����9]
```html
<style type="text/css">
#test{font-size: 14px;}
#test span{color: red}
.font{color:green}
</style>

<p id="test">CSS��ѡ���Ȩ��<span>����Ҫ</span>������Ҫ<span class="font">С�Ĵ���</span></p>
```
����ΪС�Ĵ���ᱻѡ���font����Ϊ��ɫ������ȴ��ѡ���Ȩ�ظ��ߵġ�#test span�����ó��˺�ɫ����ѡ������������Ӱ�쵽����������ӵĴ��롣�����Ҫ�ﵽ���ǵ�Ԥ�ڣ�������Ҫ������[9]��д
```html
<style type="text/css">
#test{font-size: 14px;}
#test span{color: red}            /* ѡ���Ȩ��Ϊ100+1=101 */
#test .font{color:green}         /* ѡ���Ȩ��Ϊ100+10=110 */
</style>

<p id="test">CSS��ѡ���Ȩ��<span>����Ҫ</span>������Ҫ<span class="font">С�Ĵ���</span></p>
```
�����ʹ�÷������أ�
```html
<style type="text/css">
#test{font-size: 14px;}
.test{color: red}            /* ѡ���Ȩ��Ϊ100+1=101 */
.font2{color:green}         /* ѡ���Ȩ��Ϊ100+10=110 */
</style>

<p id="test">CSS��ѡ���Ȩ��<span class="font">����Ҫ</span>������Ҫ<span class="font2">С�Ĵ���</span></p>
```
��Ϊû��ʹ����ѡ������������������´�������µ�class�Ϳ���˳���������ʽ�������ˡ�

ʹ����ѡ������������CSSѡ�����Ȩ�أ�CSS��ѡ���Ȩ��Խ�ߣ���ʽԽ���ױ����ǣ����Գ���ȷ��HTML�ṹ�ǳ��ȶ���һ���������޸��ˣ�������ʹ����ѡ������Ϊ�˱�֤��ʽ���ױ����ǣ���߿�ά���ԣ�CSSѡ���Ȩ�ؾ����ܵ͡�

������ѡ����������Ҫ�����class����Web��׼ʢ�еĳ��ڣ��ܶ๤��ʦ��Ϊ�����class�ǲ��õģ������ʹ����ѡ������Ӧ�þ���ʹ�ã�ʹ�ô�����class��������������class֢�����ڽ�������ʵ�����Ҳ�����Ϊ��class��̫��Ļ������෴����ʹ����ѡ������ȣ������class����������ά����