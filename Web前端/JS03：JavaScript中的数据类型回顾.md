**1����ʶ����Names��**

��ʶ����һ����ĸ���»��ߺ���Ԫ����ͷ��������ѡ���Եļ���һ��������ĸ�����ֻ��»��ߡ���ʶ������ʹ��������Щ�����֣�
```js
abstract
boolean��break��byte
case��catch��char��class��const��continue
debugger��default��delete��do��double
else��enume��export��extends
false��final��finally��float��for��function
goto
if��implement��import��in��instanceof��int��interface
long
native��new��null
package��private��protected��public
return
short��static��supper��switch��synchronized
this��throw��throws��transient��true��try��typeof
var��volatile��void
while��with
```
������б��д󲿷ֱ�������δ������������ʹ�á�����б�����һЩ��Ӧ�ñ�������û�б������֣�����undefined��NaN��Infinity��JavaScript������ʹ�ñ���������������������������Ķ��ǣ�JavaScript��ѷ���ڶ����������У������õ��������ȡ��������ʱ��ʹ�ñ�������Ϊ�������������

��ʶ����������䡢��������������������������ͱ�ǡ�

**2����ֵ��Numbers��**

�������α߳�����һ����JavaScript���Դ����������ݻ��ı���ֵ��һ�����Կ���ʹ�õ�ֵ�����ͣ���Ϊ�����Ե��������͡�JavaScript֧�ֻ�������ֵ���ַ������������͡���JavaScript�У�������ֵ����64λ˫���ȵģ�ȡֵ��Χ��-5e-324��1.7976931348623157e308��Ҳ����˵����JavaScript�������͸�����֮�䲢û��ʲô���𣬶��߶�����ֵ�����������ʹ����typeof������������ʾ��
```js
> typeof 1;
"number"
> typeof 1.5;
"number"
```
����JavaScript��ֵ���ǰ���IEEE-754˫���ȶ���������׼���б�ʾ����ִ����������ʱӦ��ע��һЩ���⡣���磬�ڰ�������ֵ���ʱ��������Ժ�������һ��ͨ�õĲ�����Ȼ����JavaScript�п��ܻ������˴������Ľ��������Ĵ�����ʾ����һ���⣺
```js
> .1 + .2;
0.30000000000000004
```
JavaScriptû�����õ�ʮ�����������ͣ���JavaScriptΪ��ֵ�ṩ������������toPrecision��toFixed���������������԰��չ̶�λ����С������ʽ����ֵ������Ĵ�����ʾ��������������ʹ�ã�
```js
> var num = 1234.123454321;
> num.toFixed(2);
"1234.12"
> var num2 = 1234.123454321;
> num2.toPrecision(8);
"1234.1235"
```
���ʹ����һ������64λ��Χ����ֵ�����߻��һ������64λ��Χ��ֵ��JavaScript������һ�������ֵ��Infinity������󣩻���-Infinity��������󣩡�����Ϊ0������Infinity����������ֵ������NaN������ʾһ��������ֵ��������һ�����ײ��������ֵ��������һЩBUG�ĸ�Դ��

����ͼ��һ����Ч�ַ�������ת��Ϊһ����ֵʱ�����ΪNaNֵ��NaN���С����ԡ�����NaNֵ����ֵ֮��ִ��һ������������һ��NaNֵ������ʹ�����õ�isNaN()���������һ�������Ƿ���NaNֵ��
```js
> 10 * 1 + 100 - 1 -NaN;
NaN
> var x = NaN;
> isNaN(x);
true
```
JavaScript֧�ְ˽��ƣ�����Ϊ8����ʮ�����ƣ�����Ϊ16�����˽�������ֵ��һ��0�����㣩��Ϊǰ׺��ʮ��������ֵ����һ��x��Ϊǰ׺��

JavaScript����Math�������ڳ�������ѧ���㡣���磬����ʹ��Math.round()���������λ���ľ��ȡ�
```js
> Math.round( (.1+.2)*100)/100;
0.3
```
����������ö�����Խ�ʡʱ�䡢���Ч�ʡ�

**3���ַ�����Strings��**

�ַ�����һ����0������16λ��Unicode�ַ���ɵ�ϵ�У�ʹ�õ����Ż�˫���Ž��ַ�����������ǿ������Unicode�ַ����ǳ��ڹ��ʻ�������ʹ��JavaScript����Ҫ�ԡ�JavaScript��û��Ϊ�ַ�������������������͡��ַ���Ҳ�ǣ����ɱ䣩����һ��������������Զ�޷��ı�����������Ժ����׵�ͨ�� + ��������������ַ���������һ�����ַ�����������������ȫ��ͬ���ַ����ַ�˳��Ҳ��ͬ���ַ�������Ϊ����ͬ���ַ��������ԣ�
```js
> 'c' + 'a' + 't' === 'cat';
true
```
�ַ����Ƕ�������ַ�������һЩ��Ӧ�����Ժͷ������ַ�����һ��length���ԡ����磬"JavaScript".length��10���ٱ�������Ĵ��룺
```js
> 'test String'.indexOf('s');
2
> 'test String'.charAt(5);
"S"
```
����Ҳ������չ���õ�String���������㿪����Ա����Ҫ��

**4��������Boolean��**

Boolean���ͱ�ʾtrueֵ��falseֵ�����ʵ����������У�������һ��if����У��κ������жϵ�ֵ������ת��ΪBooleanֵ���жϡ��桱�򡰼١������ж������У����ַ�����NaNֵ��null��undefined����ֵ0�͹ؼ���false����������Ϊfalse���������κ�ֵ����������Ϊtrue��
```js
if('') {
  console.log('something happens');
} else {
  console.log('nothing happens');
}
//�����nothing happens
```
JavaScript֧�ֵĲ��������������߼��루&&�����߼���||�����߼��ǣ�!�����ںܶೣ�������У������������ڼ���Ҫ��������ַ����ǳ����á�
```js
function validate(){
    var name_input = 'java';
    var age_input;
    return name_input && age_input;
}
if(validate()){
    console.log('pass');
} else {
    console.log('fail');
}
//��� fail
```
NaNֵ��ʾһ������ֵ��ֵ�����������������Ĵ��룬����������֣�
```js
> typeof NaN;
"number"
```
����typeof��������ֵ���Ϊ֮һ��

**5�����ͱȽ�**

JavaScript���е��ڣ�==���������͵�ͬ��===����������==��������Σ�յģ���Ϊ����ִ�бȽ�֮ǰ��ǿ��ִ������ת�������磺
```js
> 1 == '1';
true
```
��Ȼ���ⲻ��������Ҫ�ıȽϽ�����������������Ҳ�����������ȫ��ͬ��===�������Ż᷵��true��
```js
> 1 === '1';
false
```
��Ӧ�Ļ���!=��!==��������������ʹ��===��!==��������

**6�����ڣ�Data��**

JavaScript������Date���󣬿���ʹ��new��������Date()���캯��������Date����Date�������ڱ�ʾ���ں�ʱ�䡣�����κβ�������һ���µ�Date���󣬻�õ���һ����ʾ��ǰ���ں�ʱ���Date����
```js
> var thisMoment = new Date();
> console.log(thisMoment);
Date {Sun Aug 30 2015 10:47:14 GMT+0800}
> thisMoment.getFullYear();
2015
```
��ȻDate��һ������Ķ����˽�ö���Ȼ�������õġ�ǿ�ҽ���ʹ�ÿ�Դ��Date.js����ִ������/ʱ��ļ��㣬���Դ�https://github.com/datejs/Datejs�ҵ���js�⣬datajs�ٷ���վ�����Ѿ��޷��򿪣�����503״̬��

**7����������**

����һ������ʱδ���丳ֵ�����߷�����һ�������ڵĶ������ԣ�����������һ����Ϊundefined�����͡�nullʱJavaScript��һ�����ö�������ʾû��ֵ����ִ�бȽϲ���ʱ��undefined��null���߶���װ����falseֵ��������ñ���ʹ��undefined���ںܶ�JavaScript�������У�undefined�ǿ������¸�ֵ�ģ�������ܻ�������ڱײ��Ĵ��룺
```js
undefined = true;
if(undefined){
    console.log('ƭ�㣡');
}
//�����ƭ�㣡
```
�����г���JavaScript֧�ֵĸ����������͡�������ʽ�����ΪRegEx����������ܡ�
- Number
- String
- Boolean
- Object
- Function
- Array
- Date
- RegEx
- Null
- Undefined 

��ʹ��try/catch���ʱ��ĳЩ���ӵ�����error�����Ƿǳ����õġ�ͨ����throw����д���error����
```js
try{
    throw new Error('�ǳ��������鷢����!');
}catch(e){
    console.log(e.name + '��' + e.message);
}
//�����Error���ǳ��������鷢����!
```
������б��г��˸��ֲ�ͬ��error����
- Error
- EvalError
- RangError
- ReferenceError
- SyntaxError
- TypeError
- URIError

��������˵�������Ī����SyntaxError���������﷨����̫��Ϥ�ˡ�