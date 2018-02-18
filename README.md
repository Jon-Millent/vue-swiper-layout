# vue-swiper-layout

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
        <th>整个列表的高度</th>
        <th>String</th>
        <th>例如： 50px</th>
    </tr>
    <tr>
        <th>swiperConfig</th>
        <th>本组件基于swiper3.4.2，详细配置见官方文档</th>
        <th>Object</th>
        <th>http://3.swiper.com.cn/api/index.html</th>
    </tr>
</table>

作者：Gaolex
链接：https://www.jianshu.com/p/abaff828100d
來源：简书
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。


## License

[MIT](http://opensource.org/licenses/MIT)
