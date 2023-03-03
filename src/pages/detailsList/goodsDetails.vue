<template>
  <view>
<!--商品轮播-->
    <view>
      <u-swiper
          :list="list4"
          keyName="url"
          :autoplay="false"
          height="210"
      ></u-swiper>
    </view>
    <view class="padding-sm">
      <view class="radius bg-white padding-sm">
        <view class="text-red">
          <text class="">￥</text>
          <text class="text-lg">54.9-59.9</text>
        </view>
        <view class="margin-tb-sm">
          <text class="bg-red light radius padding-xs">商品券满53减5</text>
          <text class="bg-red light radius margin-left-sm  padding-xs">满118减5</text>
        </view>
        <text class="margin-top-sm">完美日记银翼小细跟口红正品大牌素颜口红小众品牌镜面水光滋润</text>
      </view>
    </view>
  </view>
</template>

<script>
export default {
  name: "goodsDetails",
  data(){
    return{
      list4: [{
        url: 'https://vd2.bdstatic.com/mda-nhfbd9tgqjcn4zre/hd/cae_h264/1660637485658343251/mda-nhfbd9tgqjcn4zre.mp4?v_from_s=hkapp-haokan-hna&auth_key=1677569389-0-0-f6e565fa6ee3be714800314f1e7026e8&bcevod_channel=searchbox_feed&pd=1&cd=0&pt=3&logid=3589614552&vid=4344110737833584236&abtest=107346_1&klogid=3589614552',
      },{
        url: 'https://img0.baidu.com/it/u=3682836340,2580204262&fm=253&fmt=auto&app=138&f=JPEG?w=250&h=250',
      },{
        url: 'https://img.alicdn.com/imgextra/i1/2200698115626/O1CN01lOJ07c1rQkzgLzfFf_!!2200698115626-2-scmitem6000.png_430x430q90.jpg',
      },{
        url: 'https://img.alicdn.com/imgextra/i1/2200698115626/O1CN01OXbxay1rQkzYdXEVl_!!2200698115626-2-scmitem6000.png_430x430q90.jpg',
      },{
        url: 'https://img.alicdn.com/imgextra/i3/2200698115626/O1CN01azTRcG1rQkzZElNda_!!2200698115626-2-scmitem6000.png_430x430q90.jpg',
      }],
    }
  }
}
</script>

<style scoped>

</style>