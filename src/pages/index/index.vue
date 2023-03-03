<template>
  <view class="padding-bottom-xl">
    <!-- 轮播图 -->
    <view>
      <!-- :class="[index === current && 'indicator__dot--active']" -->
      <!-- @change="e => current = e.current" -->
      <u-swiper :list="imglist5" height="200">
        <view slot="indicator" class="indicator">
          <view class="indicator__dot" v-for="(item, index) in imglist5" :key="index"
          >
          </view>
        </view>
      </u-swiper>
      <u-gap bgColor="transparent" height="15"></u-gap>
    </view>
    <!-- 搜索 -->
    <view class="padding-lr">
      <view class="flex align-center  bg-white" style="border-radius: 4px">
        <text class="cuIcon-search text-red" style="font-size: 20px; padding: 4px; margin-left: 4px"></text>
        <input class="text-df" type="text" placeholder-class="text-gray" placeholder="请输入商品名称进行搜索"
               confirm-type="search" style="width: 400rpx"/>
      </view>
    </view>
    <!-- 推荐商品 -->
    <view class="padding-lr-sm margin-top-sm flex justify-between" style="width: 100%;flex-wrap:wrap">
      <view v-for="(item,index) in productList" :key="index" class="margin-top-sm bg-white padding-bottom-sm"
            style="width: 47%;border-radius: 10px"
            @click="getPath('/src/pages/detailsList/goodsDetails')">
        <image :src="item.img" mode="aspectFill" style="width: 100%;height: 300rpx;border-radius: 10px"></image>
        <view class="margin-left-sm margin-top-sm">
          <view class="text-black">{{ item.name }}</view>
          <view class="text-gray ">
            <text class="text-sm">{{ item.brand }}</text>
            |
            <text class="text-sm">{{ item.skin }}</text>
            |
            <text class="text-sm">{{ item.origin }}</text>
          </view>
          <view class="flex align-end">
            <view class="text-red">￥
              <text class="text-xl text-bold">{{ item.price }}</text>
            </view>
            <view class="text-gray text-sm margin-left-sm">{{ item.number }}+人付款</view>
          </view>
        </view>
      </view>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      keyword: '遥看瀑布挂前川',
      title: 'Hello',
      imglist5: [
        'https://img2.baidu.com/it/u=471620330,3155897425&fm=253&fmt=auto&app=120&f=JPEG?w=750&h=500',
        'https://img1.baidu.com/it/u=3371454242,3707891229&fm=253&fmt=auto&app=138&f=PNG?w=884&h=500',
        'https://img0.baidu.com/it/u=1493830450,533641357&fm=253&fmt=auto&app=138&f=JPG?w=500&h=281',
      ],
      productList: [{
        name: "送女友口红完美",
        brand: "完美日记",
        skin: "任何肤质",
        origin: "中国",
        price: "9.9",
        number: 1000,
        img: 'https://t14.baidu.com/it/u=4247635420,861139513&fm=224&app=112&f=JPEG?w=500&h=500'
      },
        {
          name: "官方授权丝绒保权",
          brand: "花西子",
          skin: "任何肤质",
          origin: "中国",
          price: "9.9",
          number: 8000,
          img: 'https://img1.baidu.com/it/u=1185397408,1454519325&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=844'
        },
        {
          name: "INTOYOU水雾唇泥",
          brand: "intoyou",
          skin: "任何肤质",
          origin: "中国",
          price: "9.9",
          number: 9000,
          img: 'https://img1.baidu.com/it/u=1209296426,254792387&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=500'
        },
        {
          name: "热巴同款colorKey坷垃",
          brand: "colorKey",
          skin: "任何肤质",
          origin: "中国",
          price: "9.9",
          number: 8000,
          img: 'https://t14.baidu.com/it/u=402068458,3006785633&fm=224&app=112&f=JPEG?w=500&h=500'
        }
      ]
    }
  },
  onLoad() {

  },
  methods: {
    getPath(path) {
      uni.navigateTo({
        url: path
      })
    },
    add() {
      console.log('韦丽丹')
    }
  }
}
</script>

<style lang="scss">


.indicator {
  @include flex(row);
  justify-content: center;

  &__dot {
    height: 6px;
    width: 6px;
    border-radius: 100px;
    background-color: rgba(255, 255, 255, 0.35);
    margin: 0 5px;
    transition: background-color 0.3s;

    &--active {
      background-color: #ffffff;
    }
  }
}
</style>
