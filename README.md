# vue-swiper-layout  


<a href="https://github.com/Jon-Millent/vue-swiper-layout/blob/master/README.md">中文</a>
|
<a href="https://github.com/Jon-Millent/vue-swiper-layout/blob/master/en.MD">English</a>  



[![npm](https://img.shields.io/npm/v/vue-swiper-layout.svg) ![npm](https://img.shields.io/npm/dm/vue-swiper-layout.svg)](https://www.npmjs.com/package/vue-swiper-layout)
[![vue2](https://img.shields.io/badge/vue-2.x-brightgreen.svg)](https://vuejs.org/)

vue slide list component. vue 滑动列表组件
<div  align="center">    
    <img src="https://github.com/Jon-Millent/vue-swiper-layout/blob/master/show01.gif" width="30%" />
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    <img src="https://github.com/Jon-Millent/vue-swiper-layout/blob/master/show02.gif" width="30%" />
</div>

<div  align="center">  
    <img src="https://qr.api.cli.im/qr?data=http%253A%252F%252Fshow.thisummer.com%252Fvue-swiper-layout-demo%252F%2523%252F&level=H&transparent=false&bgcolor=%23ffffff&forecolor=%23000000&blockpixel=12&marginblock=1&logourl=&size=280&kid=cliim&key=a21055d6a420b8916fa5c887ead61632" width="30%"/>
</div> 
<div  align="center">  
    <p>demo</p>
</div> 

## 安装

```
npm install --save vue-swiper-layout
```

## 使用

全局注册  

```javascript
import Vue from 'vue'
import VueSwiperLayout from 'vue-swiper-layout'

Vue.use(VueSwiperLayout)
```

局部注册

```javascript
import { swiperLayout, swiperLayoutBox } from 'vue-swiper-layout'

export default {
    components: {
        swiperLayout,
        swiperLayoutBox
    }
}

```

```vue
<swiper-layout-box> // 用来包裹 swiper-layout 的容器
    
  <swiper-layout
                type="right" 
                v-model="open"
                menuHeight="60px" 
                menuWidth="40%"
                :swiperConfig="config"
                @offset="offsetEvent"
                offsetNumber="120">
    <template slot="content">
      <span>列表内容</span>
    </template>
    <template slot="menu">
      <span class="menu-item">功能菜单</span>
    </template>
  </swiper-layout>
    
</swiper-layout-box>
```
<table>
    <tr>
        <th>属性名</th>
        <th>说明</th>
        <th>类型</th>
        <th>值</th>
    </tr>
    <tr>
        <th>type</th>
        <th>菜单滑动的方式</th>
        <th>String</th>
        <th>right | left | top | bottom</th>
    </tr>
    <tr>
        <th>v-model</th>
        <th>菜单是否打开</th>
        <th>Boolean</th>
        <th>true 菜单打开， false 菜单关闭</th>
    </tr>
    <tr>
        <th>menuHeight</th>
        <th>整个列表的高度，当type为top或者bottom时候需要配置本参数</th>
        <th>String</th>
        <th>例如： 50px</th>
    </tr>
    <tr>
        <th>swiperConfig</th>
        <th>本组件基于swiper3.4.2，详细配置见官方文档</th>
        <th>Object</th>
        <th>http://3.swiper.com.cn/api/index.html</th>
    </tr>
    <tr>
        <th>@offset</th>
        <th>当滑动到菜单页，在继续滑动会触发offset事件</th>
        <th>/</th>
        <th>/</th>
    </tr>
    <tr>
        <th>offsetNumber</th>
        <th>当滑动到菜单页，设置再滑动多少距离触发offset事件，单位px</th>
        <th>Number</th>
        <th>默认：120px</th>
    </tr>
</table>

## 问题
### 1.关于样式
本组件未提供任何样式，请根据需求自行定义样式
### 2.用 `v-for` 循环，如何删除本组件？ 
推荐使用 `v-if` 动态删除本组件，实例代码见 `/test/test01.vue`

### 3.当一个菜单打开的时候怎么关闭其他菜单？ 
实例代码见 `/test/test02.vue`

## License

[MIT](http://opensource.org/licenses/MIT)
