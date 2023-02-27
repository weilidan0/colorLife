<template>
  <view class="padding-top-sm">
    <!--搜索框-->
    <view class="padding-lr-sm">
      <view class="flex align-center  bg-white" style="border-radius: 4px">
        <text class="cuIcon-search text-red" style="font-size: 20px; padding: 4px; margin-left: 4px"></text>
        <input class="text-df" type="text" placeholder-class="text-gray" placeholder="请输入商品名称进行搜索"
               confirm-type="search" style="width: 400rpx"/>
      </view>
    </view>
    <!--消息滚动条-->
    <view class="container bg-orange">
      <u-notice-bar :text="text" mode="closable" fontSize="12px" speed="150"></u-notice-bar>
    </view>
    <!--商品列表-->
    <view class="flex w100">
      <view class="w25">
        <scroll-view scroll-y="true">
          <view v-for="(item,index) in list" :key="index" class="padding-lr-sm margin-top">
            <view>{{ item.name }}</view>
          </view>
        </scroll-view>
      </view>
      <view class="">
        <scroll-view scroll-y="true" style="height: 500px">
          <view v-for="item in listMage" :key="item.index">
            <view class="margin-tb-sm bg-orange light radius padding-tb-xs text-center" style="width: 80px;">{{ item.name }}</view>
            <view class="flex">
              <view v-for="(child,childIndex) in item.srcList" :key="childIndex" class="margin-right-sm">
                <image :src="child.src" style="width: 60px;height: 60px"></image>
                <view class="text-center">{{child.name}}</view>
              </view>
            </view>
          </view>
        </scroll-view>
      </view>
    </view>
  </view>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      list: [
        {name: "Dior迪奥"},
        {name: "MAC魅可"},
        {name: "YSL圣罗兰"},
        {name: "阿玛尼"},
        {name: "兰蔻"},
        {name: "3CE"},
        {name: "香奈儿"},
        {name: "完美日记"},
        {name: "花西子"},
        {name: "colorKey"},
        {name: "菊朵"},
        {name: "INTOYOU"},
      ],
      listMage: [
        {
          name: "Dior迪奥", srcList: [
            {name: "口红", src: "https://img2.baidu.com/it/u=3334796141,152041816&fm=253&fmt=auto&app=138&f=JPEG?w=750&h=500"},
            {name: "唇釉", src: "https://img0.baidu.com/it/u=2581946535,653493052&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=500"},
            {name: "唇蜜", src: "https://img2.baidu.com/it/u=3289928323,1524668420&fm=253&fmt=auto&app=138&f=JPEG?w=250&h=300"},
            {name: "唇泥", src: "https://img1.baidu.com/it/u=2857141078,2995435619&fm=253&fmt=auto&app=138&f=JPEG?w=300&h=300"},
          ]
        },
        {
          name: "MAC魅可", srcList: [
            {name: "口红", src: "https://img0.baidu.com/it/u=1371744838,194720790&fm=253&fmt=auto&app=120&f=JPEG?w=500&h=500"},
            {name: "唇釉", src: "https://img2.baidu.com/it/u=3530113526,189701335&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=667"},
          ]
        }, {
          name: "YSL圣罗兰", srcList: [
            {name: "口红", src: "https://img0.baidu.com/it/u=1742529727,192480679&fm=253&fmt=auto&app=138&f=JPEG?w=250&h=250"},
            {name: "唇釉", src: "https://img0.baidu.com/it/u=2294025247,3950719482&fm=253&fmt=auto&app=138&f=JPEG?w=600&h=400"},
            {name: "唇蜜", src: "https://img2.baidu.com/it/u=1129960595,413873331&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=500"},
          ]
        }, {
          name: "阿玛尼", srcList: [
            {name: "口红", src: "https://img2.baidu.com/it/u=855032468,231471647&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=530"},
            {name: "唇釉", src: "https://img1.baidu.com/it/u=3497173430,1424213892&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=500"},
            {name: "唇蜜", src: "https://img1.baidu.com/it/u=4255992743,3832000871&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=500"},
          ]
        },{
          name: "兰蔻", srcList: [
            {name: "口红", src: "https://img2.baidu.com/it/u=1699093395,2655311312&fm=253&fmt=auto&app=138&f=JPEG?w=555&h=500"},
            {name: "唇釉", src: "https://img2.baidu.com/it/u=148825356,3234372617&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=647"},
            {name: "唇蜜", src: "https://img1.baidu.com/it/u=4006918540,469892314&fm=253&fmt=auto&app=138&f=JPEG?w=468&h=379"},
            {name: "唇泥", src: "https://img2.baidu.com/it/u=3120850202,965244290&fm=253&fmt=auto&app=138&f=JPEG?w=300&h=300"},
          ]
        }, {
          name: "3CE", srcList: [
            {name: "口红", src: "https://img1.baidu.com/it/u=1015606783,3174841757&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=500"},
            {name: "唇釉", src: "https://img0.baidu.com/it/u=550463458,2932966721&fm=253&fmt=auto&app=120&f=JPEG?w=500&h=500"},
            {name: "唇蜜", src: "https://img0.baidu.com/it/u=3275676352,413927415&fm=253&fmt=auto&app=120&f=JPEG?w=500&h=500"},
            {name: "唇泥", src: "https://img1.baidu.com/it/u=2987408066,4099110974&fm=253&fmt=auto&app=138&f=JPEG?w=667&h=500"},
          ]
        }, {
          name: "香奈儿", srcList: [
            {name: "口红", src: "https://img0.baidu.com/it/u=1479959196,2723430788&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=549"},
            {name: "唇釉", src: "http://t14.baidu.com/it/u=210713608,3257336391&fm=224&app=112&f=JPEG?w=500&h=500"},
            {name: "唇蜜", src: "https://img1.baidu.com/it/u=902948812,1046275028&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=375"},
            {name: "唇泥", src: "https://img2.baidu.com/it/u=1334420513,3543014180&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=500"},
          ]
        }, {
          name: "完美日记", srcList: [
            {name: "口红", src: "https://img0.baidu.com/it/u=693060361,856984642&fm=253&fmt=auto&app=138&f=JPEG?w=750&h=500"},
            {name: "唇釉", src: "https://img2.baidu.com/it/u=4149133026,1849685316&fm=253&fmt=auto&app=120&f=JPEG?w=500&h=500"},
            {name: "唇泥", src: "https://img1.baidu.com/it/u=2220839004,1675872221&fm=253&fmt=auto&app=120&f=PNG?w=500&h=500"},
          ]
        }, {
          name: "花西子", srcList: [
            {name: "口红", src: "https://img1.baidu.com/it/u=1917996679,2648608848&fm=253&fmt=auto&app=138&f=JPEG?w=600&h=400"},
            {name: "唇釉", src: "https://img2.baidu.com/it/u=2176563174,4111415816&fm=253&fmt=auto&app=138&f=JPEG?w=250&h=250"},
            {name: "唇蜜", src: "https://img0.baidu.com/it/u=3394434913,1306035593&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=500"},
          ]
        },{
          name: "colorKey", srcList: [
            {name: "口红", src: "http://t14.baidu.com/it/u=1138688732,3651527219&fm=224&app=112&f=JPEG?w=500&h=500"},
            {name: "唇釉", src: "https://img0.baidu.com/it/u=1606121105,2981194266&fm=253&fmt=auto&app=120&f=JPEG?w=1200&h=800"},
            {name: "唇蜜", src: "https://img1.baidu.com/it/u=4119093601,3451106343&fm=253&fmt=auto&app=138&f=JPEG?w=544&h=500"},
            {name: "唇泥", src: "https://img0.baidu.com/it/u=1574835933,3970549645&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=500"},
          ]
        },{
          name: "菊朵", srcList: [
            {name: "口红", src: "http://t13.baidu.com/it/u=3730434609,4079740908&fm=224&app=112&f=JPEG?w=500&h=500"},
            {name: "唇釉", src: "https://img2.baidu.com/it/u=3038251164,1316527869&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=500"},
            {name: "唇泥", src: "https://img2.baidu.com/it/u=3894466084,682936158&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=666"},
          ]
        },{
          name: "INTOYOU", srcList: [
            {name: "唇釉", src: "https://img1.baidu.com/it/u=1209296426,254792387&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=500"},
            {name: "唇蜜", src: "https://img2.baidu.com/it/u=634637772,267522852&fm=253&fmt=auto&app=138&f=JPEG?w=300&h=300"},
            {name: "唇泥", src: "https://img1.baidu.com/it/u=3216111786,2767508567&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=575"},
          ]
        },
      ],
      isSetting: false,
      searchHeight: 0,
      activeIndex: 0,
      text: "轻盈水润，色彩饱满，是你唇上的彩虹！艺术与时尚在唇间尽情绽放，娇嫩双唇从这里开始！你在追寻什么？显色度、显耀度、透明感？ 颜色生活，赋予双唇花瓣娇艳的纯净之美，在品质上提升光泽感和延长性"
    }
  },
  methods: {
    listChange(option) {
    },
    scrollHeight() {
      return this.searchHeight - (this.CustomBar + this.searchHeight + 80);
    },
    choiceFn(index) {
      this.activeIndex = index;
    }
  }
}
</script>

<style lang="scss">
.rightBox {
  background-color: red;
  position: relative;
  width: 550 rpx;
}

.funBotBox {
  border-radius: 0 0 24 rpx 0 !important;
}

.funTopBox {
  border-radius: 0 24 rpx 0 0 !important;
}

.active {
  color: blue;
  background-color: white;
  border-radius: 1px;
}

.leftBox {
  width: 200 rpx;
}
</style>
