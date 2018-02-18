# vue-swiper-layout

[![npm](https://img.shields.io/npm/v/vue-swiper-layout.svg) ![npm](https://img.shields.io/npm/dm/vue-swiper-layout.svg)](https://www.npmjs.com/package/vue-swiper-layout)
[![vue2](https://img.shields.io/badge/vue-2.x-brightgreen.svg)](https://vuejs.org/)

vue slide list component. vue 滑动列表组件
<div  align="center">    
    <img src="https://github.com/Jon-Millent/vue-swiper-layout/blob/master/show01.gif" width="40%" />
    <img src="https://github.com/Jon-Millent/vue-swiper-layout/blob/master/show02.gif" width="40%" />
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
        <th>offset</th>
        <th>当滑动到菜单页，在继续滑动会触发offset事件</th>
        <th>@</th>
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
本组件为提供任何样式，请根据需求自行定义样式
### 2.用 `v-for` 循环，如何删除本组件？ 
推荐使用 `v-if` 动态删除本组件，例如下面代码
```vue
<template>
  <div>
    <swiper-layout-box class="my-layout">
      <swiper-layout 
      v-for="(target, index) in list" 
      v-if="target.isAlive" 
      :key="index" 
      @offset="deletes(target, index)" 
      :type="target.type" 
      menuHeight="60px" 
      :menuWidth="target.width || '100%'">
        <template slot="content">
          <span>{{target.name}}</span>
          <span class="gury">{{target.tel}}</span>
        </template>
        <template slot="menu">
          <div class="menu-item">编辑</div>
          <div class="menu-item" @click="deletes(target, index)">删除</div>
        </template>
      </swiper-layout>
    </swiper-layout-box>
  </div>
</template>
<script type="text/ecmascript-6">
  import { swiperLayout, swiperLayoutBox }  from 'vue-swiper-layout'

  export default {
    name: 'hello',
    data(){
      return {
        list: [
          {
            name: '联系人0017',
            tel: '13241269845xxxxx',
            type: 'right',
            width: '40%',
            isAlive: true
          },
          {
            name: '联系人0018',
            tel: '13241269845xxxxx',
            type: 'right',
            width: '40%',
            isAlive: true
          }
        ]
      }
    },
    components: {
      swiperLayout,
      swiperLayoutBox
    },
    methods: {
      deletes(target, index) {
        target.isAlive = false
      }
    }
  }
</script>
```

## License

[MIT](http://opensource.org/licenses/MIT)
