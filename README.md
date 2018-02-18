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
    </tr>
    <tr>
        <th>键盘</th>
        <th>/dev/stdin</th>
        <th>0</th>
    </tr>
    <tr>
        <th>显示器</th>
        <th>/dev/stdout</th>
        <th>1</th>
    </tr>
    <tr>
        <th>显示器</th>
        <th>/dev/stderr</th>
        <th>2</th>
    </tr>
</table>

作者：Gaolex
链接：https://www.jianshu.com/p/abaff828100d
來源：简书
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。


## License

[MIT](http://opensource.org/licenses/MIT)
