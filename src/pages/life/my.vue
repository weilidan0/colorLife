<template>
	<view style="padding-bottom: 20px;">
		<view class="bgPicture">
			<view class=" margin-left-xl  flex justify-between ">
				<image src="../../../static/iamge/head.png" style="width: 40px;height: 40px;margin-top: 10px;"
					mode="aspectFill"></image>
				<view class="flex justify-between align-center">
					<view class="" style="margin-right: 140px;">
						<view class=" margin-top text-white">王刚</view>
						<view class="margin-top-xs  text-white">180****6095</view>
					</view>
					<view @click="pageTo('pages/my/baseInfo/QRcodeIndex')">
						<image mode="widthFix" src="../../../static/iamge/erweima.png"
							style="width: 44rpx;margin-right: 30px;"></image>
					</view>
				</view>
			</view>
		</view>
		<view class="vipCard">
			<view class="flex justify-around align-center">
				<view class="margin-right-lg text-lg" style="color: snow">VIP会员 | <text
						class="margin-left-xs text-sm">2022-11-15到期</text></view>
				<button class="cu-btn btnSize">成为会员</button>
			</view>
		</view>
		<view class="padding-sm flex justify-around align-center hp bg-white yuanJiao">
			<view class="flex flex-direction align-center">
				<view>0.00</view>
				<view class="text-red margin-top-sm">余额
				</view>
			</view>
			<view class="flex flex-direction align-center">
				<view>12.00</view>
				<view class="text-red margin-top-sm">积分</view>
			</view>
			<view class="flex flex-direction align-center">
				<view>100.00</view>
				<view class="text-red margin-top-sm">优惠劵</view>
			</view>
			<view class="flex flex-direction align-center">
				<view>50.00</view>
				<view class="text-red margin-top-sm">零钱</view>
			</view>
		</view>
		<view class=" try margin-top">
			<view>
				<u-swiper :list="imglist5" @change="e => current = e.current">
					<view slot="indicator" class="indicator">
						<view class="indicator__dot" v-for="(item, index) in imglist5" :key="index"
							:class="[index === current && 'indicator__dot--active']">
						</view>
					</view>
				</u-swiper>
				<u-gap bgColor="transparent" height="15"></u-gap>
			</view>
		</view>
    <view>
      <u-notice-bar :text="text1"></u-notice-bar>
    </view>
			<view class="bg-white margin-top-sm margin-lr padding " >
				<view class="flex u-border-bottom padding-bottom justify-between">
					<view class="text-black">我的订单</view>
					<view>查看全部订单<text class="cuIcon-right"></text></view>
				</view>
				<view class="flex justify-between">
					<view class="margin-top">
				<view class="lg text-gray cuIcon-pay text-center" style="font-size: 18px;"></view>
				<view>待付款</view>
				</view>
				<view class="margin-top">
				<view class="lg text-gray cuIcon-send text-center" style="font-size: 18px;"></view>
				<view>待发货</view>
				</view>
				<view class="margin-top">
				<view class="lg text-gray cuIcon-deliver text-center" style="font-size: 18px;"></view>
				<view>待收货</view>
				</view>
				<view class="margin-top">
				<view class="lg text-gray cuIcon-vipcard text-center" style="font-size: 18px;"></view>
				<view>待评价</view>
				</view>
				<view class="margin-top">
				<view class="lg text-gray cuIcon-recharge text-center" style="font-size: 18px;"></view>
				<view>退款/售后</view>
				</view>
			</view>
	</view>
	<view class="bg-white margin-top-sm margin-lr padding"  >
				<view class="flex justify-between">
					<view class="margin-top-xs">
				<view class="lg text-gray cuIcon-cart text-center" style="font-size: 18px;"></view>
				<view>购物车</view>
				</view>
				<view class="margin-top-xs">
				<view class="lg text-gray cuIcon-location text-center" style="font-size: 18px;"></view>
				<view>收货地址</view>
				</view>
				<view class="margin-top-xs">
				<view class="lg text-gray cuIcon-comment text-center" style="font-size: 18px;"></view>
				<view>客服聊天</view>
				</view>
				<view class="margin-top-xs">
				<view class="lg text-gray cuIcon-friendadd text-center" style="font-size: 18px;"></view>
				<view>个人信息</view>
				</view>
				<view class="margin-top-xs">
				<view class="lg text-gray cuIcon-expressman text-center" style="font-size: 18px;"></view>
				<view>账户设置</view>
				</view>
			</view>
	</view>
  </view>
</template>

<script>
	export default {
		data() {
			return {
				text1: '疫情期间不定时更新，中高风险地区快递时效会因此受到影响，具体以实际发出为准',
				imglist5: [
					'https://tse3-mm.cn.bing.net/th/id/OIP-C.k8Xx3YZssC_BGfs5Rh6sAgHaJh?w=146&h=188&c=7&r=0&o=5&dpr=1.3&pid=1.7',
					'https://img1.baidu.com/it/u=3371454242,3707891229&fm=253&fmt=auto&app=138&f=PNG?w=884&h=500',
					'https://img0.baidu.com/it/u=1493830450,533641357&fm=253&fmt=auto&app=138&f=JPG?w=500&h=281',
				],
			}
		}
	}
</script>

<style lang="scss" scoped>
	.bgPicture {
		background-image: linear-gradient(to right, yellow, pink);
		width: 100%;
		height: 300rpx;
		background-size: 100% 100%;
		background-repeat: no-repeat;


		// border-radius: 0 0 10px 10px;
	}

	.yuanJiao {
		border-radius: 15px 15px 0px 0px;
	}

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

	.indicator-num {
		padding: 2px 0;
		background-color: rgba(0, 0, 0, 0.35);
		border-radius: 100px;
		width: 35px;
		@include flex;
		justify-content: center;

		&__text {
			color: #FFFFFF;
			font-size: 12px;
		}
	}

	.try {
		width: 90%;
		margin-left: 18px;

	}

	.vipCard {
		position: absolute;
		background-image: linear-gradient(to right, #F37B1D, #E55349);
		width: 80%;
		top: 80px;
		padding-left: 5px;
		margin-left: 35px;
		padding: 30rpx;
		border-radius: 25px 25px 0px 0px;

		.hp {
			position: absolute;
			border-radius: 55px 55px 0px 0px;
		}

		.hp {
			position: absolute;
			border-radius: 55px 55px 0px 0px;
		}

		.btnSize {
			height: 60rpx;
			color: #E65B49;
			font-size: 0.6rem;
			border-radius: 45px 45px 45px 45px;
		}
	}
</style>
