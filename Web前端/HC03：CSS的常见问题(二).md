hasLayout
===========================
�ܶ�ʱ��CSS��IE�µĽ���ʮ����֣�������Firefox����ʾ�ķǳ���ȷ��������IE��ȴ���������⣬��ʱ����Щ����������ķǳ����졪�����磬һ���ȽϾ����BUG��������border��ʱ����ʱ��border��Ͽ���ˢ��ҳ����߹���ҳ���ʱ�򣬶ϵ��Ĳ����ֻ���������������

��Щ��������������󲿷ֺ�IE�µ�һ�����ص�������ء���hasLayout��

hasLayout��IE�µ�һ��ת�����ԣ�����CSS�Ľ������档��ʱ����IE��һЩ���ӵ�CSS���ý������������BUG����ԭ���������hasLayoutû�б��Զ������йأ�����ͨ��һЩ���ɣ��ֶ�����hasLayout���ԾͿ��Խ��BUG�ˡ���Ҳ�������IE��������֢������ƫ���ˣ��ܶ�ʱ�򣬴�����hasLayout�Ϳ���ҩ�������ˡ�

hasLayout�Ĵ��������кܶ��֣���������width��heightֵ������positionΪrelative�ȡ������������width��height��position���ᴥ��hasLayout��ͬʱ����һЩ�����õġ����ڵĹ���ʦ�Ƽ�ʹ�á�height��1%��������hasLayout����ʱ��û�г���IE7����height������IE6����ʵ�ǰ��ա�min-height�������͵ģ�����ֻҪ���IE6����hack����* html{height:1%}���Ϳ��Դ���hasLayout��ͬʱ�ֲ����������á��������ֵ�IE7��Ȼ���ںܶ�hasLayout��������⣬��IE7�Ѿ��ܹ���ȷʶ��height�����ˣ���height��1%���ķ���Ҳ�Ͳ��������ˡ�

���ǣ�һ�����õķ�����ʼ�����ˣ���ʹ����һ����Ƨ��CSS����zoom������hasLayout������zoom��1�����Դ���hasLayout�����Ҳ�����height������һ�����븱���ã�������ǣ����ǿ��Բ���CSS hack�ˡ�����zoom��������һ�����Դ���hasLayout�ģ��ڼ�����������£�����ǳ����ӵ�CSS���ã��ر���ʹ��DHTML��ʱ��ʹ�á�zoom��1����ʱ��Ҳ����Ч����ʱ�����ǿ�����Ҫ������Ϊǿ��ġ�position��relative������������hasLayout����֮����zoom������á��ȫ���ɱ���С�Ĵ���hasLayout�ķ�ʽ��һ������£�ʹ������ȫ���Դ���hasLayout�ˡ����������������������zoom��1����Ч������£����ǿ���ͨ�����á�position��relative��������hasLayout�������������һ�㸱���á�

ֵ��ǿ�����ǣ�hasLayout���漰���������ڸ����鼶Ԫ�صĺ�ģ�ͽ��͵ģ��������ڿ鼶Ԫ�صġ������������Ԫ�أ�������һЩ�����Ч����

ֵ�����ҵ��ǣ�����΢��window10���Ƴ�����֮�����������˹�ʹ��ճ�����IE��Ϊ��Զ����ʷ�����ò�˵��ר��IE�ĸ���˽�˽��������ʧЧ�����ǲ�����ҪΪIE�ĸ��ֹ�������е�ͷʹ��ӵ��Webkit����������ںˣ�����ǰ��WEBҳ��Ĺ�������Firefoxһ����������������˾���Firefox����������ĵ����������

�鼶Ԫ�غ�����Ԫ�ص�����
------------------------------
�鼶Ԫ�غ�����Ԫ���ǲ��ֵ������������Ԫ�أ������Ŀ鼶Ԫ����div��p��form��ul��li��ol�ȣ������Ķ�����Ԫ����span��strong��em�ȡ�

�鼶Ԫ�غ�����Ԫ����ʲô�����أ��鼶Ԫ�ػ��ռһ�У�Ĭ������£������Զ������丸����Ԫ�ؿ�ȣ�����Ԫ�ز����ռһ�У����ڵ�Ԫ��������ͬһ���У�ֱ��һ���Ĳ��²Żỻ�У�������Ԫ�ص����ݶ��仯�������´��룺
```html
<style type="text/css">
p{background-color: red;}
div{background-color: yellow}
span{background-color: blue}
strong{background-color: green}
</style>

<p>�鼶Ԫ��P</p><div>�鼶Ԫ��DIV</div><span>����Ԫ��span</span><strong>����Ԫ��strong</strong>
```

��������е�Ч������ͼ��  
![Paste_Image.png](../image/1604/css2/1.png)

�鼶Ԫ�ؿ�������width��height���ԣ�����Ԫ������width��height������Ч����������룺
```html
<style type="text/css">
p{background-color: red;width: 200px;height: 200px;}
div{background-color: yellow;width: 400px;height: 10px;}
span{background-color: blue;width: 200px;height: 200px;}
strong{background-color: green;width: 400px;height: 100px;}
</style>

<p>�鼶Ԫ��P</p><div>�鼶Ԫ��DIV</div><span>����Ԫ��span</span><strong>����Ԫ��strong</strong>
```

��������е�Ч������ͼ:  
![Paste_Image.png](../image/1604/css2/2.png)

ע�⣬�鼶Ԫ�ؼ�ʹ�����˿�ȣ���Ȼ�Ƕ�ռһ�еġ�

�鼶Ԫ�ؿ�������margin��padding���ԡ�����Ԫ�ص�margin��padding���Ժ���֣�ˮƽ�����padding- left��padding-right��margin-left��margin-right�������߾�Ч������ 6�����padding-top��padding-bottom��margin-top��margin-bottomȴ��������߾�Ч�������´��룺
```html
<style type="text/css">
p{background-color: red;padding: 20px;margin: 20px;}
div{background-color: yellow;padding: 20px;}
span{background-color: blue;padding: 20px;margin: 20px;}
strong{background-color: green;padding: 20px;margin: 20px;}
</style>

<p>�鼶Ԫ��P</p><div>�鼶Ԫ��DIV</div><span>����Ԫ��span</span><strong>����Ԫ��strong</strong>
```

��������е�Ч����ͼ��  
![Paste_Image.png](../image/1604/css2/3.png)

����ͼ��ʾ����ֱ�����margin�������κ�Ч������ֱ�����padding��Ȼ�����ˣ���ȴ��û�к����ڵ�Ԫ���������롣

�鼶Ԫ�غ�����Ԫ�ص�CSS���������display�����п鼶Ԫ�ض�Ӧ��display��block������Ԫ�ض�Ӧ��display��inline�����ǿ���ͨ���޸�display�������л��鼶Ԫ�غ�����Ԫ�أ���������룺
```html
<style type="text/css">
p{background-color: red;display: inline;}
div{background-color: yellow;display: inline;}
span{background-color: blue;display: block;}
strong{background-color: green;display: block;}
</style>

<p>�鼶Ԫ��P</p><div>�鼶Ԫ��DIV</div><span>����Ԫ��span</span><strong>����Ԫ��strong</strong>
```

��������е�Ч����ͼ��  
![Paste_Image.png](../image/1604/css2/4.png)