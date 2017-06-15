## Vue-cli������Ŀ

��װ��npm install -g vue-cli  
vue list���� ���鿴�ٷ�ģ���б�  
��ʼ����Ŀ��vue init webpack ��Ŀ��   
��װ������npm install  
���У�npm run dev  

## Vue����֧�֣�transition��

��DIV���ҵ����ķ��붯��Ϊ����  
����Ҫ�Ӷ������齨���������ԣ�transition="��������"  

```
<template>
  <div v-show="showFlag" transition="move" class="food">
  </div>
</template>
```

�����Ҫ��Ӷ������齨������transition���ԣ�����ֵ����move��Ҳ����ȥ������

Ȼ����style��ʽ�зֱ�д������ʽ��
```
<style lang="less" rel="stylesheet/less">
  .food{
    // ������ʽ
    ... ...
    &.move-transition{
      transition: all .2s linear;
      transform: translate3d(0,0,0);
    }
    &.move-enter,&.move-leave{
      transform: translate3d(100%,0,0);
    }
  }
</style>
```

��ʽ�ԡ���������-transition��Ϊ������ʾ������ʼ�����ã��ԡ�enter����leave����β�ı�ʾ�������������á�

�����������һ���򵥵�Vue������

## ���齨���������������v-ref��

parent�������child����������������������v-ref���ԣ�

```
<template>
   // child�齨
   <child v-ref:child></child>
</template>
<script type="text/ecmascript-6">
    export default{
        methods: {
            methodA() {
                // �������������
                this.$refs.child.show();
            }
        }
    };
</script>
<style lang="less" rel="stylesheet/less">
</style>
```

ע�⣺v-ref�����ֵ���ԡ�:�����ӵĶ����ǡ�=���š���this.$refs.child�����ǻ�ȡ���������

child���������
```
<template>
   <div>����child�齨</div>
</template>
<script type="text/ecmascript-6">
    export default{
        methods: {
            show() {
                //��������
            }
        }
    };
</script>
<style lang="less" rel="stylesheet/less">
</style>
```

## ���齨֪ͨ��������¼��ɷ�$dispatch��

�������������
```
this.$dispatch('content.toggle', type);
```

��ratingtype.select�����Զ����¼������ڸ�����п��Լ������¼����ڸ�����ж���events���Դ����¼�
```
events: {
      'ratingtype.select'(type) {
        this.selectType = type;
      },
      'content.toggle'(onlyContent) {
        this.onlyContent = onlyContent;
      }
}
```

## DOM�󶨣�v-el��$els��

ͨ����div���á�v-el:xxx������ͬ��div����һ��id���ԣ�Ȼ�����ͨ�����id��ȡDIVԪ�ء�
```
<div class="food" v-el:food>

```

Ȼ����ʹ��$els���ɷ��ʸ�Ԫ��
```
let food = this.$els.food;
```

food�õ��ľ���һ��DOM����

## ��ֹԪ�ص����͸��ð��
```
<div @click.stop.prevent="test">test</div>
```

## �������ڲ����¼��أ�keep-alive��

���л�·�ɵ�ʱ��ϣ��ÿ���л������±���Ⱦһ�Σ�������·�ɳ��������keep-alive���Լ���
```
<router-view :user="user" keep-alive></router-view>
```

## ��Ŀ������ע��

ʹ��vue-cli��������Ŀʹ��npm run build������д������ɾ�̬�ļ������ǿ������������쳣��
```
- building for production...shell.js: internal error
Error: ENOENT: no such file or directory, stat 'D:\xxxxxapp\static\*'
... ...
```

��ʱ�����Գ��Ը���shelljs���İ汾������Ŀ��shelljs��ǰ�汾��0.6.0����ô���Ը�����0.7.4��npm update shelljs@0.7.4�����ٴν���build����.