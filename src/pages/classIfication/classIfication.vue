<template>
	<view class="padding-top-sm">
		<!--搜索框-->
		<view class="padding-lr-sm">
			<view class="flex align-center  bg-white" style="border-radius: 4px">
				<text class="cuIcon-search text-red" style="font-size: 20px; padding: 4px; margin-left: 4px"></text>
				<input class="text-df" type="text" placeholder-class="text-gray" placeholder="请输入商品名称进行搜索"
					confirm-type="search" style="width: 400rpx" />
			</view>
		</view>
		<!--消息滚动条-->
		<view class="container bg-orange">
			<u-notice-bar :text="text" mode="closable" fontSize="12px" speed="150"></u-notice-bar>
		</view>
		<!--商品列表-->
		<view class="flex">
			<view class="leftBox">
				<scroll-view class="" scroll-y
					:style="'height:'+ scrollHeight() +'px;background: linear-gradient(90deg, #F86A3B 0%, #F48836 100%);'">
					<view class="flex bg-orange flex-direction">
						<view class="padding-lr-sm padding-tb-lg text-center text-white" @click="choiceFn(index)"
							:class="activeIndex==index?'active':(activeIndex-1)==index?'funBotBox':(activeIndex+1)==index?'funTopBox':''"
							v-for="(item,index) in appListJson" :key="index">{{ item.name }}
						</view>
					</view>
				</scroll-view>
			</view>
			<view class="rightBox">
				<view class="margin-tb-lg padding-lr-sm">
					韦丽丹
					<view>韦丽丹</view>
					<view v-for="(items,index) in list" :key="index">
						<view>
							{{items.name}}
						</view>
					</view>
				</view>

				<!-- <appList :listData="appListJson.childrenList" :isSetting="isSetting" @listChange="listChange"
                 :key="appListJson.id+isSetting"></appList> -->
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		components: {},
		data() {
			return {
				list: [{
						name: "韦丽丹"
					},{
						name: "韦丽丹"
					},{
						name: "韦丽丹"
					},
				],
				isSetting: false,
				searchHeight: 0,
				appListJson: [{
						id: 100,
						name: "花西子 ",
						childrenList: [{
								appId: 0,
								appIcon: "cuIcon-evaluate",
								appName: "花西子",
								appLink: "",
								src: "https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fn.sinaimg.cn%2Fsinakd20210921ac%2F262%2Fw640h422%2F20210921%2F3617-109a6b723c6c70cfa869277b1e4165f5.png&refer=http%3A%2F%2Fn.sinaimg.cn&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1674035416&t=5b3730e2e97784f03481864f2274c92b"
							},
							{
								appId: 1,
								appIcon: "cuIcon-evaluate",
								appName: "我的代理商",
								appLink: "",
								src: "https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fn.sinaimg.cn%2Fsinakd20210921ac%2F262%2Fw640h422%2F20210921%2F3617-109a6b723c6c70cfa869277b1e4165f5.png&refer=http%3A%2F%2Fn.sinaimg.cn&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1674035416&t=5b3730e2e97784f03481864f2274c92b"
							},
							{
								appId: 2,
								appIcon: "cuIcon-pay",
								appName: "合同管理",
								appLink: "",
								src: "https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fn.sinaimg.cn%2Fsinakd20210921ac%2F262%2Fw640h422%2F20210921%2F3617-109a6b723c6c70cfa869277b1e4165f5.png&refer=http%3A%2F%2Fn.sinaimg.cn&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1674035416&t=5b3730e2e97784f03481864f2274c92b"
							},
							{
								appId: 4,
								appIcon: "cuIcon-form",
								appName: "商品管理",
								appLink: "",
								src: "https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fn.sinaimg.cn%2Fsinakd20210921ac%2F262%2Fw640h422%2F20210921%2F3617-109a6b723c6c70cfa869277b1e4165f5.png&refer=http%3A%2F%2Fn.sinaimg.cn&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1674035416&t=5b3730e2e97784f03481864f2274c92b"
							},
							{
								appId: 5,
								appIcon: "cuIcon-pic",
								appName: "代理政策",
								appLink: "",
								src: "https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fn.sinaimg.cn%2Fsinakd20210921ac%2F262%2Fw640h422%2F20210921%2F3617-109a6b723c6c70cfa869277b1e4165f5.png&refer=http%3A%2F%2Fn.sinaimg.cn&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1674035416&t=5b3730e2e97784f03481864f2274c92b"
							},
							{
								appId: 6,
								appIcon: "cuIcon-cart",
								appName: "发票管理",
								appLink: "",
								icon: ""
							},
							{
								appId: 7,
								appIcon: "cuIcon-cart",
								appName: "品鉴会报销",
								appLink: "",
								icon: ""
							},
							{
								appId: 8,
								appIcon: "cuIcon-cart",
								appName: "代理审核",
								appLink: "",
								icon: ""
							},
							{
								appId: 9,
								appIcon: "cuIcon-cart",
								appName: "返佣管理",
								appLink: "",
								icon: ""
							},
						]
					},
					{
						id: 101,
						name: "colorKey ",
						childrenList: [{
								appId: 0,
								appIcon: "cuIcon-evaluate",
								appName: "营销管理",
								appLink: "",
								icon: ""
							},
							{
								appId: 1,
								appIcon: "cuIcon-evaluate",
								appName: "我的代理商",
								appLink: "",
								icon: ""
							},
							{
								appId: 2,
								appIcon: "cuIcon-pay",
								appName: "合同管理",
								appLink: "",
								icon: ""
							},
							{
								appId: 4,
								appIcon: "cuIcon-form",
								appName: "商品管理",
								appLink: "",
								icon: ""
							},
							{
								appId: 5,
								appIcon: "cuIcon-pic",
								appName: "代理政策",
								appLink: "",
								icon: ""
							},
							{
								appId: 6,
								appIcon: "cuIcon-cart",
								appName: "发票管理",
								appLink: "",
								icon: ""
							},
							{
								appId: 7,
								appIcon: "cuIcon-cart",
								appName: "品鉴会报销",
								appLink: "",
								icon: ""
							},
							{
								appId: 8,
								appIcon: "cuIcon-cart",
								appName: "代理审核",
								appLink: "",
								icon: ""
							},
							{
								appId: 9,
								appIcon: "cuIcon-cart",
								appName: "返佣管理",
								appLink: "",
								icon: ""
							},
						]
					},
					{
						id: 102,
						name: "into you ",
						childrenList: [{
								appId: 0,
								appIcon: "cuIcon-evaluate",
								appName: "营销管理",
								appLink: "",
								icon: ""
							},
							{
								appId: 1,
								appIcon: "cuIcon-evaluate",
								appName: "我的代理商",
								appLink: "",
								icon: ""
							},
							{
								appId: 2,
								appIcon: "cuIcon-pay",
								appName: "合同管理",
								appLink: "",
								icon: ""
							},
							{
								appId: 4,
								appIcon: "cuIcon-form",
								appName: "商品管理",
								appLink: "",
								icon: ""
							},
							{
								appId: 5,
								appIcon: "cuIcon-pic",
								appName: "代理政策",
								appLink: "",
								icon: ""
							},
							{
								appId: 6,
								appIcon: "cuIcon-cart",
								appName: "发票管理",
								appLink: "",
								icon: ""
							},
							{
								appId: 7,
								appIcon: "cuIcon-cart",
								appName: "品鉴会报销",
								appLink: "",
								icon: ""
							},
							{
								appId: 8,
								appIcon: "cuIcon-cart",
								appName: "代理审核",
								appLink: "",
								icon: ""
							},
							{
								appId: 9,
								appIcon: "cuIcon-cart",
								appName: "返佣管理",
								appLink: "",
								icon: ""
							},
						]
					},
					{
						id: 103,
						name: "完美",
						childrenList: [{
								appId: 0,
								appIcon: "cuIcon-evaluate",
								appName: "营销管理",
								appLink: "",
								icon: ""
							},
							{
								appId: 1,
								appIcon: "cuIcon-evaluate",
								appName: "我的代理商",
								appLink: "",
								icon: ""
							},
							{
								appId: 2,
								appIcon: "cuIcon-pay",
								appName: "合同管理",
								appLink: "",
								icon: ""
							},
							{
								appId: 4,
								appIcon: "cuIcon-form",
								appName: "商品管理",
								appLink: "",
								icon: ""
							},
							{
								appId: 5,
								appIcon: "cuIcon-pic",
								appName: "代理政策",
								appLink: "",
								icon: ""
							},
							{
								appId: 6,
								appIcon: "cuIcon-cart",
								appName: "发票管理",
								appLink: "",
								icon: ""
							},
							{
								appId: 7,
								appIcon: "cuIcon-cart",
								appName: "品鉴会报销",
								appLink: "",
								icon: ""
							},
							{
								appId: 8,
								appIcon: "cuIcon-cart",
								appName: "代理审核",
								appLink: "",
								icon: ""
							},
							{
								appId: 9,
								appIcon: "cuIcon-cart",
								appName: "返佣管理",
								appLink: "",
								icon: ""
							},
						]
					},
					{
						id: 104,
						name: "小辣椒",
						childrenList: [{
								appId: 0,
								appIcon: "cuIcon-evaluate",
								appName: "营销管理",
								appLink: "",
								icon: ""
							},
							{
								appId: 1,
								appIcon: "cuIcon-evaluate",
								appName: "我的代理商",
								appLink: "",
								icon: ""
							},
							{
								appId: 2,
								appIcon: "cuIcon-pay",
								appName: "合同管理",
								appLink: "",
								icon: ""
							},
							{
								appId: 4,
								appIcon: "cuIcon-form",
								appName: "商品管理",
								appLink: "",
								icon: ""
							},
							{
								appId: 5,
								appIcon: "cuIcon-pic",
								appName: "代理政策",
								appLink: "",
								icon: ""
							},
							{
								appId: 6,
								appIcon: "cuIcon-cart",
								appName: "发票管理",
								appLink: "",
								icon: ""
							},
							{
								appId: 7,
								appIcon: "cuIcon-cart",
								appName: "品鉴会报销",
								appLink: "",
								icon: ""
							},
							{
								appId: 8,
								appIcon: "cuIcon-cart",
								appName: "代理审核",
								appLink: "",
								icon: ""
							},
							{
								appId: 9,
								appIcon: "cuIcon-cart",
								appName: "返佣管理",
								appLink: "",
								icon: ""
							},
						]
					},
					{
						id: 105,
						name: "阿玛尼",
						childrenList: [{
								appId: 0,
								appIcon: "cuIcon-evaluate",
								appName: "营销管理",
								appLink: "",
								icon: ""
							},
							{
								appId: 1,
								appIcon: "cuIcon-evaluate",
								appName: "我的代理商",
								appLink: "",
								icon: ""
							},
							{
								appId: 2,
								appIcon: "cuIcon-pay",
								appName: "合同管理",
								appLink: "",
								icon: ""
							},
							{
								appId: 4,
								appIcon: "cuIcon-form",
								appName: "商品管理",
								appLink: "",
								icon: ""
							},
							{
								appId: 5,
								appIcon: "cuIcon-pic",
								appName: "代理政策",
								appLink: "",
								icon: ""
							},
							{
								appId: 6,
								appIcon: "cuIcon-cart",
								appName: "发票管理",
								appLink: "",
								icon: ""
							},
							{
								appId: 7,
								appIcon: "cuIcon-cart",
								appName: "品鉴会报销",
								appLink: "",
								icon: ""
							},
							{
								appId: 8,
								appIcon: "cuIcon-cart",
								appName: "代理审核",
								appLink: "",
								icon: ""
							},
							{
								appId: 9,
								appIcon: "cuIcon-cart",
								appName: "返佣管理",
								appLink: "",
								icon: ""
							},
						]
					},
					{
						id: 106,
						name: "香奈儿",
						childrenList: [{
								appId: 0,
								appIcon: "cuIcon-evaluate",
								appName: "营销管理",
								appLink: "",
								icon: ""
							},
							{
								appId: 1,
								appIcon: "cuIcon-evaluate",
								appName: "我的代理商",
								appLink: "",
								icon: ""
							},
							{
								appId: 2,
								appIcon: "cuIcon-pay",
								appName: "合同管理",
								appLink: "",
								icon: ""
							},
							{
								appId: 4,
								appIcon: "cuIcon-form",
								appName: "商品管理",
								appLink: "",
								icon: ""
							},
							{
								appId: 5,
								appIcon: "cuIcon-pic",
								appName: "代理政策",
								appLink: "",
								icon: ""
							},
							{
								appId: 6,
								appIcon: "cuIcon-cart",
								appName: "发票管理",
								appLink: "",
								icon: ""
							},
							{
								appId: 7,
								appIcon: "cuIcon-cart",
								appName: "品鉴会报销",
								appLink: "",
								icon: ""
							},
							{
								appId: 8,
								appIcon: "cuIcon-cart",
								appName: "代理审核",
								appLink: "",
								icon: ""
							},
							{
								appId: 9,
								appIcon: "cuIcon-cart",
								appName: "返佣管理",
								appLink: "",
								icon: ""
							},
						]
					},
					{
						id: 107,
						name: "圣罗兰",
						childrenList: [{
								appId: 0,
								appIcon: "cuIcon-evaluate",
								appName: "营销管理",
								appLink: "",
								icon: ""
							},
							{
								appId: 1,
								appIcon: "cuIcon-evaluate",
								appName: "我的代理商",
								appLink: "",
								icon: ""
							},
							{
								appId: 2,
								appIcon: "cuIcon-pay",
								appName: "合同管理",
								appLink: "",
								icon: ""
							},
							{
								appId: 4,
								appIcon: "cuIcon-form",
								appName: "商品管理",
								appLink: "",
								icon: ""
							},
							{
								appId: 5,
								appIcon: "cuIcon-pic",
								appName: "代理政策",
								appLink: "",
								icon: ""
							},
							{
								appId: 6,
								appIcon: "cuIcon-cart",
								appName: "发票管理",
								appLink: "",
								icon: ""
							},
							{
								appId: 7,
								appIcon: "cuIcon-cart",
								appName: "品鉴会报销",
								appLink: "",
								icon: ""
							},
							{
								appId: 8,
								appIcon: "cuIcon-cart",
								appName: "代理审核",
								appLink: "",
								icon: ""
							},
							{
								appId: 9,
								appIcon: "cuIcon-cart",
								appName: "返佣管理",
								appLink: "",
								icon: ""
							},
						]
					},
				],
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
		width: 550rpx;
	}

	.funBotBox {
		border-radius: 0 0 24rpx 0 !important;
	}

	.funTopBox {
		border-radius: 0 24rpx 0 0 !important;
	}

	.active {
		color: black;
		background-color: white;
		border-radius: 0;
	}

	.leftBox {
		width: 200rpx;
	}
</style>
