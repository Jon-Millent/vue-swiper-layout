# vue-swiper-layout

[![npm](https://img.shields.io/npm/v/vue-swiper-layout.svg) ![npm](https://img.shields.io/npm/dm/vue-swiper-layout.svg)](https://www.npmjs.com/package/vue-swiper-layout)
[![vue2](https://img.shields.io/badge/vue-2.x-brightgreen.svg)](https://vuejs.org/)

vue slide list component.
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

## Install

```
npm install --save vue-swiper-layout
```

## Usage

Global registration

```javascript
import Vue from 'vue'
import VueSwiperLayout from 'vue-swiper-layout'

Vue.use(VueSwiperLayout)
```

Partial registration

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
<swiper-layout-box> // Used to wrap the swiper-layout container
    
  <swiper-layout
                type="right" 
                menuHeight="60px" 
                menuWidth="40%"
                :swiperConfig="config"
                @offset="offsetEvent"
                offsetNumber="120">
    <template slot="content">
      <span>List contents</span>
    </template>
    <template slot="menu">
      <span class="menu-item">Function menu</span>
    </template>
  </swiper-layout>
    
</swiper-layout-box>
```
<table>
    <tr>
        <th>Attributes</th>
        <th>Description</th>
        <th>Types</th>
        <th>Value</th>
    </tr>
    <tr>
        <th>type</th>
        <th>Menu sliding way</th>
        <th>String</th>
        <th>right | left | top | bottom</th>
    </tr>
    <tr>
        <th>menuHeight</th>
        <th>The height of the entire list, when the type is top or bottom, you need to configure this parameter</th>
        <th>String</th>
        <th>E.g： 50px</th>
    </tr>
    <tr>
        <th>swiperConfig</th>
        <th>This component is based on swiper3.4.2, the detailed configuration, see the official document</th>
        <th>Object</th>
        <th>http://3.swiper.com.cn/api/index.html</th>
    </tr>
    <tr>
        <th>@offset</th>
        <th>When you swipe to the menu page, the offset event fires as you continue swiping</th>
        <th>/</th>
        <th>/</th>
    </tr>
    <tr>
        <th>offsetNumber</th>
        <th>When sliding to the menu page, set how much further distance to trigger the offset event in px</th>
        <th>Number</th>
        <th>Default：120px</th>
    </tr>
</table>

## Question
### 1.About style
This component does not provide any style, please customize the style according to your needs
### 2.With `v-for` loop, how to delete this component?
It is recommended to use `v-if` to dynamically delete this component, instance code
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

<style type="text/css">
  html, body{
    padding: 0;
    margin: 0;
  }
  .my-layout .swiper-layout-parent .swiper-slide{
    border: none;
    line-height: 60px;
  }
  .my-layout .swiper-layout-parent .swiper-slide.content{
    padding-left: 20px;
  }
  .my-layout .swiper-layout-item{
    border: none;
    border-bottom: 1px solid #EAEAEB;
  }
  .gury{
    color: #ccc;
  }
  .my-layout .before-menu .menu-item{
    width: 50%;
    float: left;
    text-align: center;
    color: #fff;
  }
  .my-layout .before-menu .menu-item:nth-of-type(1){
    background-color: #FF9C00;
  }
  .my-layout .before-menu .menu-item:nth-of-type(2){
    background-color: #FF3B30;
  }
</style>
```

## License

[MIT](http://opensource.org/licenses/MIT)
