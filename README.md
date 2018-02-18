# vue-swiper-layout 开发中..

[![npm](https://img.shields.io/npm/v/vue-swiper-layout.svg) ![npm](https://img.shields.io/npm/dm/vue-swiper-layout.svg)](https://www.npmjs.com/package/vue-swiper-layout)
[![vue2](https://img.shields.io/badge/vue-2.x-brightgreen.svg)](https://vuejs.org/)

vue slide list component. vue 滑动列表组件


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

```html
<swiper-layout-box>
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



## License

[MIT](http://opensource.org/licenses/MIT)
