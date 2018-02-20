# vue-swiper-layout  


<a href="https://github.com/Jon-Millent/vue-swiper-layout/blob/master/README.md">中文</a>
|
<a href="https://github.com/Jon-Millent/vue-swiper-layout/blob/master/en.MD">English</a>  


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
                v-model="open"
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
        <th>v-model</th>
        <th>The menu is open</th>
        <th>Boolean</th>
        <th>true : open, false : close</th>
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
It is recommended to use `v-if` to dynamically delete this component, instance code at `/test/test01.vue`
### 3.How to close other menus when a menu is open？ 
See example code at `/test/test02.vue`

## License

[MIT](http://opensource.org/licenses/MIT)
