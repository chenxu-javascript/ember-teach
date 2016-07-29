`handlebars`ģ���ṩ����һ���������Ƶ��������ʽ������`if`��`if����else����`��
�ڽ�����Щ�������ʽ֮ǰ��������������ʾ��׼�������������һ�ʹ��`Ember CLI`�����`route`��`template`��Ȼ���ڴ�����`template`�ϱ�д`handlebars`ģ����롣
�ȴ���`route`��<br>
`ember generate route handlbars-conditions-exp-route`<br>
���ߣ�<br>
`ember generate route handlbarsConditionsExpRoute`<br>
��������������ļ�������һ���ġ����`Ember CLI`��Ϊ�����Զ�����2����Ҫ���ļ���`app/templates/handlbars-conditions-exp-route.hbs`  �� `app/routes/handlbars-conditions-exp-route.js`

**ע�⣺�����ʹ�õ����շ�ʽ������`Ember CLI`�����`Ember`�������淶�Զ��������л���`-`�ָ������ơ�Ϊʲô������ʹ�������`route`������`template`�أ�����Ϊ�㴴��`route`��ͬʱ`Ember CLI`���Զ����㴴��һ����Ӧ��ģ���ļ�����������ȴ���`template`�Ļ����㻹��Ҫ�ֶ���ִ�д���`route`���������Ҫִ��2������(`ember generate template handlbars-conditions-exp-route`��`ember generate route handlbars-conditions-exp-route`)��**

�õ���ʾ����Ҫ���ļ���ص����⣬��ʼ����`handlebars`�������жϱ��ʽ��
Ϊ����ʾ����`route`�ļ����ģ���������룺

```javascript
//  app/routes/handlebars-condition-exp-route.js

import Ember from 'ember';

export default Ember.Route.extend({

	model: function () {
		return {name: 'i2cao.xyz', age: 25, isAtWork: false, isReading: false };
		// return { enable: true };
	}		
});
```

����`handlebars-condition-exp-route.js`����ļ������ݻ��ں���·����һ����ϸ���ܣ���������ҵ����Ƿ�����һ������ģ���ϡ���`EL`���ʽ�ǳ����ƣ��������`.`��ȡ�����������ֵ���磺`person.name`����

### 1��`if`���ʽ

```html
<!-- app/templates/handlbars-conditions-exp-route.hbs -->

<!-- if�жϱ�ǩ����model��ֵ��Ϊ false, undefined, null or [] ��ʱ����ʾ��ǩ�ڵ����� -->
{{#if model}}
Welcome back, <b>{{model.name}}</b> !
{{/if}}
```

![run result](/content/images/2016/03/17.png)

ÿ���������ʽ��Ҫ��`#`��ͷ����Ҫ�ж�Ӧ�Ĺرձ�ǩ�����Ƕ���`if`��ǩ��˵���Ǳ���Ҫ�رձ�ǩ�ģ�����򵥾ٸ����ӣ�

```html
<!-- û�йرչرձ�ǩ��if�÷� -->
<div class="{{if flag 'show' 'hide'}}">
��������
</div>
```

���`if`��ǩ�൱��һ��`��Ԫ�����`,ֻ��ʡ����`?`��`:`,�����������`flag`��ֵ�ж�����ʾ�Ǹ�CSS�࣬���`flag`��ֵ����`false`������`[]`�����飬Ҳ����`null`��Ҳ����`undefined`��`div`�����CSS��`show`��ģ�����֮��ı�ǩΪ`<div class="show">`��������CSS��`hide`ģ�����֮��ı�ǩΪ`<div class="hide">`����������Ӧ�ú���������ˣ���ʵ˵���˾�һ��`if`�жϡ�û����ѵ㡣����

���е�ʱ����Ҫע�������ط���һ���������ִ�е�`URL`�������Ҳ��ʹ���շ�ʽ��������ʽ������������`ember generate route handlbarsConditionsExpRoute`���������`URL`���ҵ���һ���ģ�������ֻҪ�ǵ�ִ�е�`URL`���㴴����`route`��������һ�µġ���Ȼ��������ǿ����޸ĵġ���`app/router.js`�����޸ģ���`Router.map`��Ĵ���Ҳ��`Ember CLI`�Զ������ġ����ǿ��Կ�����һ��`this.route('handlebarsConditionsExpRoute');`����������·�ɵ����ơ�

**���飺����֮���·��������ò�Ҫ�޸ģ�`ember`�����Ĭ�ϵ������淶����`route`��Ӧ��`template`��������޸���`router.js`�����������Ҫͬʱ�޸�`app/routes` �� `app/templates` �����Ӧ���ļ���������`URL`�ϵ�·���޷��ҵ���Ӧ��`template`��ʾ������ݣ���`router.js`�����õ����ֱ�����`app/routes`Ŀ¼�µ�·���ļ����ֶ�Ӧ��ģ������ֲ�һ��Ҫ��·���������ƶ�Ӧ��Ӧ�ÿ�����`route`����ָ����Ⱦ��ģ�����Ǹ��������������ݻὲ���������ص����ݣ��˽⼴�ɣ���
˵���������㿴�����ҽ�ͼ������е�������Ϊ���޸�����ģ��(`app/index.html`)�����������ļ�������Լ�ϲ������ʽ����һ��`app/index.html`���������ʽ��������`ember-cli-build.js`�����������ʽ�����ԣ��Զ������ʽ����`public/assets/`�£����û��Ŀ¼���������ֶ��������ڴ˾Ͳ���׸����������Ǳ��ĵ��ص㡣**

### 2��`if����else����`���ʽ

```html
<!-- app/templates/handlebars-conditions-exp-route.hbs -->
<!-- if����else�����ж� -->
{{#if model.isAtWork}}
Ship that code..<br>
{{else if model.isReading}}
You can finish War and Peace eventually..<br>
{{else}}
This is else block...
{{/if}}
```
����������This is else block...
��Ϊ`isAtWork`��`isReading`����`false`�����߿����Լ��޸�`app/routes/handlebars-condition-exp-route.js`�����Ӧ��ֵȻ��鿴��������

### 3��`unless`���ʽ

`unless`���ʽ�����ڷǲ�������`model.isReading`ֵΪ`false`��ʱ���������ʽ��������ݡ�

```html
<!-- app/templates/handlebars-conditions-exp-route.hbs -->
<!-- ���ж� -->
{{#unless model.isReading}}
unless.....
{{/unless}}
```

���`isReading`ֵΪ`false`�����`unless��`���򲻽�����ʽ�ڡ�

### 4����HTML��ǩ��ʹ�ñ��ʽ

`handlebars`���ʽ����ֱ����Ƕ�뵽`HTML`��ǩ�ڡ�

```html
<!-- app/templates/handlebars-conditions-exp-route.hbs -->
<!-- ���԰ѱ��ʽֱ��Ƕ����ĳ����ǩ�У���enable��ֵΪtrue������������һ����(css����)enable����������'disable' -->
<span class={{if enable 'enable' 'disable'}}>enable or disable</span>
```

˵������ʵ����һ����Ŀ���㡣������⡣��������������һ�㽲û�йرձ�ǩ��`if`����һ�£��͵��Ǹ�ϰ��=^=��

��������`handlebars`����õļ����������ʽ���Լ���ΪС������ʾһ��϶����ˣ������е㾪�ȵĿ�����������һ�鼴�ɡ��ǳ��ļ򵥣����ܺ��滹���������������жϵı��ʽ�������Ჹ�ϡ�
<br>
���������������[Github](https://github.com/ubuntuvim/my_emberjs_code)�����ľ�������޸ģ������ϵĴ�����github��������ֳ��룬����Ӱ�첻�󣡣����������ò��Ķ����е��ã�����github��Ŀ�ϸ��ҵ��`star`�ɡ����Ŀ϶�������˵�����Ķ�������
