�����ڱ�д�����ʱ���ܻ�����һЩ��Ҫ����ʹ�õĴ���Ƭ�Ρ���ʱ�����Ҫ�����ĸ��ƺ���������Ӱ��Ч�ʡ���������Sublime Text��snippet������Ƭ�Σ����ܣ����ܺܺõĽ����һ���⡣ͨ�׵Ľ������ǰ����ǳ��õĴ���ֱ𱣴�������Ȼ��ͨ���������ʽ���������á�

����������Tools �����ߣ�> New Snippet����Ƭ�Σ�

��ʱ����������´��룺
```
<snippet>
	<content><![CDATA[
Hello, ${1:this} is a ${2:snippet}.
]]></content>
	<!-- Optional: Set a tabTrigger to define how to trigger the snippet -->
	<!-- <tabTrigger>hello</tabTrigger> -->
	<!-- Optional: Set a scope to limit where the snippet will trigger -->
	<!-- <scope>source.python</scope> -->
	<!-- <description>description</description> -->
</snippet>
```
���У�content����CDATA���������Ĳ���������Ҫ����Ĵ���Ƭ�Σ���ѡ��

tabTrigger������tab���������Զ���ȫ���빦�ܵ�һ�����֣���ѡ��

scope����ѡ��ʹ�÷�Χ������д����������ļ���Ч������source.css��test.html�ֱ��Ӧ��ͬ�ļ���

description����ѡ����snippet�˵��е���ʾ˵����֧�����ģ�����������壬�˵�����ʾ��ǰ�ļ����ļ�����

${1:this}��ʾ�������󣬹����ͣ����λ�ã���ͬʱ������������:thisΪ�Զ����������ѡ����
${2}��ʾ�������󣬰�Tab�����������˳����ת����Ӧλ�ã��Դ����ƣ���

���ڣ���Ӧ�����˸����µ��˽⡣�����ǾͿ�ʼ�Լ����ֱ�дһ��ʵ�������Ƕ�֪������Sublime�У����룡����html:5�ٰ�tab���������Զ���ȫHTML�ṹ��������������Ժܼ򵥣����Լ���չ�����Ľ�����ݣ������˼���mate��ǩ��������ҳ��������
```
<snippet>
	<content><![CDATA[
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<meta name="Generator" content="Sublime Text3">
	<meta name="Author" content="dunizb">
    <meta name="website" content="http://www.mybry.com">
    <meta name="Description" content="���㣬������Ψ������ͺù��ﲻ�ɹ���~~">
    <link type="image/x-icon" rel="shortcut icon" href="image/favicon.ico" />
	<script type="text/javascript">
		${1:}
	</script>
<body>
    ${2:����html����}
</body>
</html>
]]></content>
	<!-- Optional: Set a tabTrigger to define how to trigger the snippet -->
	<tabTrigger>hjs</tabTrigger>
	<!-- Optional: Set a scope to limit where the snippet will trigger -->
	<!-- <scope>source.python</scope> -->
	<description>custom-html</description>
</snippet>
```
Ȼ�󱣴����Ƭ�Σ����浽Sublime Text3\Data\Packages\User���棬ȡ������

![Paste_Image.png](../image/1605/sublime-snippet/1.png)

����������HTMLҳ��������hjs+tab���Ϳ����Զ���ȫ��һϵ�д����ˡ�