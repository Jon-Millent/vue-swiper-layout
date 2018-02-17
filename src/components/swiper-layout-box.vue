<template>
  <div class="swiper-layout-box">
    <slot></slot>
  </div>
</template>

<script type="text/ecmascript-6">
  export default{
    name: 'swiper-layout-box'
  }
</script>

<style type="text/css">
  .swiper-layout-box{
    width: 100%;
  }
  .swiper-layout-box:after{
    content: '';
    display: block;
    clear: both;
  }
</style>
