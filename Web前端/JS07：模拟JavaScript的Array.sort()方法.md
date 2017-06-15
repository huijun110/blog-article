��JavaScript�У�Array�����sort()��������������ģ��������������Ĭ������¿��ܲ���������Ҫ�ģ����������������
```js
var arr = [2,5,10,20,7,15];
```
ʹ��sort�����õ����½����
[10, 15, 2, 20, 5, 7]

�ڲ����ݲ���������£����ǰ��ַ���Unicode����������ġ�

Ϊ�˽��������⣬����Ϊsort()��������һ���������������ECMAScript����ô����ģ�
```js
/**
@param {function} [compareFn]
@return {Array.<T>}
*/
Array.prototype.sort = function(compareFn) {};
```
����Ϊһ��function������бȽϺ��������ǿ��Ը�дΪ������ʽ������һ���ȽϺ�����
```js
arr.sort(function(a,b){
    return a - b;
});
```
a��b����Ҫ�Ƚϵ����������䷵��ֵ���£�
+ �� a С�� b���������������� a Ӧ�ó����� b ֮ǰ���򷵻�һ��С�� 0 ��ֵ��
+ �� a ���� b���򷵻� 0��
+ �� a ���� b���򷵻�һ������ 0 ��ֵ�� 

���ڷ���ֵ�����ֽ�������ǿ���ֱ��ʹ�á�a-b���������Ϳ�����ȷ�õ����
[2, 5, 7, 10, 15, 20]

��ô�����������Ǿ���ģ��һ����������ͱȽϺ�����ʵ�֡�

���ȣ�������ǲ�����������������Լ�ʵ��������ô���ǿ���ʹ�ô�ͳ��ð�����򷽷���
```js
function sort(array){
        for(var i=0; i<array.length - 1; i++){
            // ���������Ѿ��ź�����
            var isSorted = true;
            for(var j=0; j<array.length - 1 - i; j++){
                if(array[j] > array[j + 1]){
                    var temp = array[j];
                    array[j] = array[j + 1];
                    array[j + 1] = temp;
                    // ���бȽϣ�˵������δ����
                    isSorted = false;
                }
            }
            // ��������Ѿ���ɣ�����ѭ��
            if(isSorted){
                break;
            }
        }
    }
```
����һ��ѭ���������ٵ����򷽷������ǣ�����������Ӧ�Բ�ǿ�������ַ�������Ͳ����ˣ������������ַ������飬Ҫ���ַ���������������ʵ�֣�
```js
var arry = ["aaa","aa","c","bb"."xxxxxxxx"];
```
�������������ǲ��ò�����дһ�����������ַ����������������Ҫ�Ķ�����ð������ĵ�6�е��ж�������
```js
if(array[j].length > array[j+1].length){}
```
��ô����Ȼֻ��Ҫ�Ķ���һ�䣬���ǿ��԰���һ����Ϊ�������ݣ��Ժ�����ô�žʹ�ʲô���Ĳ����������������һ���������ص��������������¸�д�����ð�����򣬴���һ���ص�������
```js
// ģ��sort()
function sort(array,fn){
    for(var i=0; i<array.length - 1; i++){
        var isSorted = true;
        for(var j=0; j<array.length - 1 - i; j++){
            if(fn(array[j], array[j + 1]) > 0){
                var temp = array[j];
                array[j] = array[j + 1];
                array[j + 1] = temp;
                    isSorted = false;
                }
            }
        }
        if(isSorted){
           break;
        }
    }
}
```
ע���2�к͵�6�У���sort������һ��fn����������һ��������Ȼ���ڵ�6�е��ã�array[j]��array[j+1]�ֱ���ǻص�������a,b�����Ƚ�ֵ���������д�ķ������ɶ���ֵ��������Ҳ���Զ��ַ������������ˡ�
```js
var arr = ["aaa","a","xxxxxx","abcd","ab"];
sort(arr, function (a,b) {
    return a.length - b.length;
});
console.log(arr);
```
�����["a", "ab", "aaa", "abcd", "xxxxxx"]
