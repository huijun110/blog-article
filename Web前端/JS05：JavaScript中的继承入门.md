��ͳ�������������Զ����ṩextend֮��ķ������ڳ�����ļ̳У���Javascript�����ṩextend��������Javascript��ʹ�ü̳���Ҫ�õ㼼�ɡ�

Javascript�е�ʵ�������Ժ���Ϊ���ɹ��캯����ԭ����������ɵģ����Ƕ��������ࣺPerson��zhangsan���������ڴ��еı�������ͼ1��
![Person��zhangsan���������ڴ��еı���](../image/1604/js-jc/1.png)
�������Zhangsan�̳�Person����ô������Ҫ��Person���캯����ԭ���е����Ժ���Ϊȫ������Zhangsan�Ĺ��캯����ԭ�ͣ�����ͼ2��ʾ��
![Zhangsan�Ĺ��캯����ԭ��](../image/1604/js-jc/2.png)

Are you Ok���˽��˼̳е�˼·����ô����һ�������Person��Zhangsan�ļ̳й��ܡ����ȣ�������Ҫ����Person�࣬���´��룺
[����1]
```js
// ����Person��
function Person (name){
	this.name = name;
	this.type = "��";
}
Person.prototype={
	say : function(){
		console.info("����һ��"+ this.type +"���ҵ����ֽ�" + this.name);
	}
}	
//����Zhangsan��
function Zhangsan (name){
}
Zhangsan.prototype={
	
}
```
Zhangsan��Ȼ���Լ����е����Ժ���Ϊ�������󲿷����Ժ���Ϊ��Person��ͬ����Ҫ�̳���Person�ࡣ��ǰ������JavaScript�м̳���Ҫ�ֱ�̳й��캯����ԭ���е����Ժ���Ϊ�ġ���������Zhangsan�̳�Person�Ĺ��캯���е���Ϊ�����ԣ����´��룺
[����2]
```js
// ����Person��
function Person (name){
	this.name = name;
	this.type = "��";
}
Person.prototype={
	say : function(){
		console.info("����һ��"+ this.type +"���ˣ��ҵ����ֽ�" + this.name);
	}
}	
//����Zhangsan��
function Zhangsan (name){
	this.name = name;
	this.type = "��";
}
Zhangsan.prototype={
}
//ʵ����Zhangsan����
var zs = new Zhangsan("����");
console.info(zs.type);    // ��
```
������������������ôû�����̳еġ�ζ�����أ�������Zhangsan�Ĺ��캯���н�Person�����Ժ���Ϊ������һ�ݣ�����˵�Ǽ̳в���˵�ǡ����ɣ���������Ĺ��캯�����˺�������ͬ�������ط�������һ����������ȱ������ԣ����Person��Ĺ��캯�����κα䶯������Ҳ��Ҫ�ֶ���ͬ���޸�Zhangsan��Ĺ��캯����ͬ��һ�ݴ��룬���Ǹ�����һ��д���˳����� �Ĳ�ͬ�ط�����Υ����DRYԭ�򣬽����˴���Ŀ�ά���ԡ�

���ˣ����������Ľ�����
[����3]
```js
// ����Person��
function Person (name){
	this.name = name;
	this.type = "��";
}
Person.prototype={
	say : function(){
		console.info("����һ��"+ this.type +"���ˣ��ҵ����ֽ�" + this.name);
	}
}	
// ����Zhangsan��
function Zhangsan (name){
	Person(name);
}
Zhangsan.prototype={
}
// ʵ����Zhangsan����
var zs = new Zhangsan("����");
console.info(zs.type);        // undefined
```
������Zhangsan�Ĺ��캯�������Person()������ϣ�����ڲ���ths.xxx������Zhangsan��Ĺ��캯����ִ��һ�飬����ֵ��ǣ����֡�console.info(zs.type);��ʱ���������undefined��������ô�����أ�

���Person�ĵ��÷�ʽ�йء���JavaScript�У�function�����ֲ�ͬ�ĵ��÷�����
1����Ϊ�������ڣ�ֱ���á�()�����ã����硰function test(){}; test();��test������������ֱ�ӱ���()�����ŵ��á�
2����Ϊ��Ĺ��캯�����ڣ�ʹ��new���ã����硰function test(){}; new test();��test��Ϊ��Ĺ��캯����ͨ��new����test���ʵ�����������ַ����ĵ��ã�function�ڲ���thisָ���������ͬ---��Ϊ������function����thisָ�����window������Ϊ���캯����function����thisָ���ʵ������

��������У�Zhangsan�๹�캯���е�Person��ͨ��������ʽ���õģ����ڲ���thisָ�����window������Ч����ͬ�����´��룺
[����4]
```js
// ����Person��
function Person (name){
	this.name = name;
	this.type = "��";
}
Person.prototype={
	say : function(){
		console.info("����һ��"+ this.type +"���ˣ��ҵ����ֽ�" + this.name);
	}
}	
// ����Zhangsan��
function Zhangsan (name){
	window.name = name;
    window.type = "��";
}
Zhangsan.prototype={
}
// ʵ����Zhangsan����
var zs = new Zhangsan("����");
console.info(zs.type);	// undefined
console.info(type);		// �� (window.type����ʡ��д��type)
```
�����ﵽ[����3]��Ч������Person�ڲ�thisָ��Zhangsan���ʵ��������ͨ��call��apply����ʵ�֣����£�
[����5]
```js
// ����Person��
function Person (name){
	this.name = name;
	this.type = "��";
}
Person.prototype={
	say : function(){
		console.info("����һ��"+ this.type +"���ˣ��ҵ����ֽ�" + this.name);
	}
}	
// ����Zhangsan��
function Zhangsan (name){
	Person.call(this,name);
}
Zhangsan.prototype={
}
// ʵ����Zhangsan����
var zs = new Zhangsan("����");
console.info(zs.type);		// ��
```
���캯�������Ժ���Ϊ�Ѿ��ɹ�ʵ���˼̳У�����������Ҫʵ��ԭ���е����Ժ���Ϊ�ļ̳С���ȻZhangsan����Ҫ��Person��ԭ����ͬ�������Ժ���Ϊ����ô�ܷ�Person���ԭ��ֱ�Ӵ���Zhangsan���ԭ�ͣ����´��룺
[����6]
```js
// ����Person��
function Person (name){
	this.name = name;
	this.type = "��";
}
Person.prototype={
	say : function(){
		console.info("����һ��"+ this.type +"���ˣ��ҵ����ֽ�" + this.name);
	}
}	
// ����Zhangsan��
function Zhangsan (name){
	Person.call(this,name);
}
Zhangsan.prototype = Person.prototype;
// ʵ����Zhangsan����
var zs = new Zhangsan("����");
// ����һ�������ˣ��ҵ����ֽ�����
zs.say();
```
ͨ��Person���ԭ�ʹ���Zhangsan���ԭ�ͣ�Zhangsan��ɹ������say��Ϊ�������鲢���������е���ô�򵥣��������Ҫ��Zhangsan�����run��Ϊ�أ����´��룺
[����7�����run��Ϊ]
```js
// ����Person��
function Person (name){
	this.name = name;
	this.type = "��";
}
Person.prototype={
	say : function(){
		console.info("����һ��"+ this.type +"���ˣ��ҵ����ֽ�" + this.name);
	}
}	
// ����Zhangsan��
function Zhangsan (name){
	Person.call(this,name);
}
Zhangsan.prototype = Person.prototype;
Zhangsan.prototype.run = function(){
	console.info("��100�׶���ֻҪ10�룡");
}
// ʵ����Zhangsan����
var zs = new Zhangsan("����");
zs.say();   // ����һ�������ˣ��ҵ����ֽ�����
zs.run();   //��100�׶���ֻҪ10�룡
var zs2 = new Person("����2");
zs2.run();	//��100�׶���ֻҪ10�룡
```
����ֻ���Zhangsan�����run��Ϊ��ΪʲôPerson��Ҳ�����run��Ϊ���أ����漰��ֵ�ʹ�ַ����������----��JavaScript�У���ֵ�����ô�ֵ�ʹ���ַ���ֲ�ͬ�ķ�ʽ���и�ֵ���������ֵ�͡������͡��ַ��͵Ȼ����������ͣ��ڽ��и�ֵʱ�Ὣ����ֱ�Ӹ�ֵһ�ݣ�����ֵ����һ�����ݽ��и�ֵ��Ҳ����ͨ����˵�Ĵ�ֵ����������顢hash����ȸ����������ͣ��ڽ��и�ֵʱ��ֱ�����ڴ��ַ��ֵ�������ǽ����ݸ�ֵһ�ݣ�����Ǵ�ַ��ֵ�����Ǵ����ݵ�ӳ���ַ��
[����8����ֵ�봫ַ]
```js
var a=10;		// ������������
var b=a;		// ������a�����ֵ��ֵһ�ݣ���������b��b��a������һ������
var c=[1,2,3];	// ������������
var d=c;		// ������cָ��������ڴ��ַ��������d��c��dָ��ͬһ������
b++;
d.push(4);
console.info(a);	// 10
console.info(b);	// 11		����b��������ݸ��Ĳ���Ӱ�쵽����a
console.info(c);	// 1,2,3,4	����c��dָ��ͬһ�����ݣ����ݸ��Ļ��໥Ӱ��
console.info(d);	// 1,2,3,4
```
��ԭ��JavaScript�У�ѡ��ֵ���Ǵ���ַ�Ǹ��������������Զ��жϵģ�������ַ��ʱ�������Ǵ������벻�����鷳������������Ҫ�Ը����������͵ĸ�ֵ���п��ƣ��ø�����������Ҳ���Խ��д�ֵ��

��򵥵������Ǳ����������Hash���󣬽��������Hash�������ָ��ӵ����ݲ�ֳ�һ���������ݣ�Ȼ��ֱ�ֵ����������룺
[����9���Ը����������ͽ��д�ֵ]
```js
var a = [1, 2, 3] ,b = {name:'����',sex:'��',tel:'1383838438'};
var c = [] ,d = {};
for(var p in a){
	c[p] = a[p]; 
}
for(var p in b){
	d[p] = b[p];
}
c.push('4');
d.email = 'ibing@outlook.com';
console.info(a);			// [1, 2, 3]
console.info(c);            // [1, 2, 3, "4"]
console.info(b.email);		// undefined
console.info(d.email);		// ibing@outlook.com
```
ֵ��һ����ǣ���������Ĵ�ֵ������ʹ���������slice����concat����ʵ�֣���������룺
[����10�����鴫ֵ�ļ򵥷���]
```js
var a = [1, 2, 3];
var b = a.slice(), c = a.concat();
b.pop();
c.push(4);
console.info(a);		// [1, 2, 3]
console.info(b);        // [1, 2]
console.info(c);		// [1, 2, 3, 4]
```
prototype������Ҳ��һ��hash��������ֱ��������ֵʱ����д�ַ����Ҳ��Ϊʲô[����7���������Ϊ]�У�zs2��Ȼ��run��ԭ�����ǿ�����for in������prototype���Ӷ�ʵ��prototype�Ĵ�ֵ������Ϊprototype��function���������function���Ĺ�ϵ�����ǻ�������һ�ַ���ʵ��prototype�Ĵ�ֵ----new SomeFunction()����������룺
[����11]
```js
// ����Person��
function Person (name){
	this.name = name;
	this.type = "��";
}
Person.prototype={
	say : function(){
		console.info("����һ��"+ this.type +"���ˣ��ҵ����ֽ�" + this.name);
	}
}	
// ����Zhangsan��
function Zhangsan (name){
	Person.call(this,name);
}
Zhangsan.prototype = new Person();
Zhangsan.prototype.constructor = Person;
Zhangsan.prototype.run = function(){
	console.info("��100�׶���ֻҪ10�룡");
}
	
// ʵ����Zhangsan����
var zs = new Zhangsan("����");
zs.say();   // ����һ�������ˣ��ҵ����ֽ�����
zs.run();   // ��100�׶���ֻҪ10�룡
var zs2 = new Person("����2");
zs2.run();	// TypeError: zs2.run is not a function
```
���Ƿ�ע�⵽�������Zhangsan.prototype.constructor = Person;��������ΪZhangsan.prototype = new Person();ʱ��Zhangsan.prototype.constructorָ����Person��������Ҫ��������������ָ��Zhangsan��