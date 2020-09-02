<template>
	<view class="detail-container d-flex d-flex-column">
		<view class="detail-con d-flex-item">
			<view class="detail-banner">
				<swiper :duration="1000">
					<swiper-item v-for="(item,index) in 3" :key="index">
						<image src="../../static/img02.png" class="d-img"/>
					</swiper-item>
				</swiper>
				<view class="detail-banner-pagination d-flex d-flex-middle d-flex-center">1/9</view>
			</view>
			<view class="detail-info">
				<view class="detail-name d-flex d-flex-middle">华为P30r 5G手机 <text class="d-flex d-flex-middle d-flex-center">可分期</text></view>
				<view v-if="type=='goods'" class="detail-desc">天玑800 5G SoC芯片4800万高感逛夜拍22.5W超级快充</view>
				<view v-if="type=='goods'" class="detail-num d-flex d-flex-between">
					<view class="detail-price d-flex d-flex-bottom">¥<text>1234</text></view>
					<view>销量：4564</view>
				</view>
				<view v-if="type==4 || type==5" class="detail-points d-flex d-flex-between">
					<view class="detail-points-price"><text>500</text>积分</view>
					<view class="d-flex">
						<view class="detail-points-sales">销量  4564</view>
						<view class="detail-points-total d-flex">当前积分  <text>4647分</text></view>
					</view>
				</view>
				<view v-if="type==6" class="detail-points d-flex d-flex-between">
					<view class="detail-points-price"><text>2300</text>积分</view>
					<view class="detail-points-total d-flex">支付方式  <text>积分 | 现金+积分</text></view>
				</view>
			</view>
			<template v-if="type=='goods'">
				<view class="divider"></view>
				<view class="detail-select">
					<view class="detail-select-item d-flex d-flex-middle">
						<text class="d-flex-unShrink">规格</text>
						<view class="d-flex-item">选择规格</view>
						<image src="../../static/icon-arrow-right.png" class="d-flex-unShrink"/>
					</view>
					<view class="detail-select-item d-flex d-flex-middle">
						<text class="d-flex-unShrink">参数</text>
						<view class="d-flex-item">品牌 华为 型号 ...</view>
						<image src="../../static/icon-arrow-right.png" class="d-flex-unShrink"/>
					</view>
					<view class="detail-select-item d-flex d-flex-middle">
						<text class="d-flex-unShrink">运费</text>
						<view class="d-flex-item">配送至：湖北武汉，包邮</view>
						<image src="../../static/icon-arrow-right.png" class="d-flex-unShrink"/>
					</view>
				</view>
			</template>
			<template v-if="type==4 || type==5 || type==6">
				<view class="divider"></view>
				<detail-msg/>
			</template>
			<template v-if="type==0 || type==1 || type==2 || type==3">
				<view class="divider"></view>
				<detail-package/>
			</template>
			<template v-if="type==4 || type==5">
				<view class="divider"></view>
				<detail-level/>
			</template>
			<template v-if="type==6">
				<view class="divider"></view>
				<detail-recommond/>
			</template>
			<view class="divider"></view>
			<view>
				<view class="detail-tit d-flex d-flex-middle">产品详情</view>
				<image src="../../static/detail.png" mode="widthFix" class="detail-img"/>
			</view>
		</view>
		<view class="detail-foot d-flex-unShrink d-flex">
			<template v-if="type=='goods'">
				<view class="detail-foot-cart d-flex-unShrink d-flex d-flex-column d-flex-middle d-flex-center">
					<image src="../../static/icon-cart.png"/>
					<view>购物车</view>
				</view>
				<view class="detail-foot-add d-flex-unShrink d-flex d-flex-middle d-flex-center">加入购物车</view>
			</template>
			<view class="detail-foot-buy d-flex-item d-flex d-flex-middle d-flex-center">{{(type==4 || type==5 || type==6)?'立即兑换':((type==0 || type==1 || type==2 || type==3)?'立即办理':'立即购买')}}</view>
		</view>
	</view>
</template>

<script>
	import DetailRecommond from '../../components/lyl/detail-recommond.vue'
	import DetailLevel from '../../components/lyl/detail-level.vue'
	import DetailPackage from '../../components/lyl/detail-package.vue'
	import DetailMsg from '../../components/lyl/detail-msg.vue'
	export default {
		components:{
			DetailRecommond,
			DetailLevel,
			DetailPackage,
			DetailMsg
		},
		data() {
			return {
				type:'goods', // 0:5G智享套餐（个人版） 1:5G智享套餐（家庭版A） 2:5G智享套餐（家庭版B） 3:5G特惠流量包 4:兑流量 5：兑通话 6:兑好物 goods:商品详情
			}
		},
		methods: {
			
		},
		onLoad(option){
			this.type=option.type // 0:5G智享套餐（个人版） 1:5G智享套餐（家庭版A） 2:5G智享套餐（家庭版B） 3:5G特惠流量包 goods:商品详情
		}
	}
</script>

<style scoped>
	page{
		height: 100%;
	}
	.detail-container{
		height: 100%;
	}
	.detail-con{
		height: 50%;
		overflow-y: auto;
	}
	.detail-banner{
		position: relative;
		height: 700rpx;
	}
	.detail-banner swiper{
		width: 100%;
		height: 100%;
	}
	.detail-banner-pagination{
		position: absolute;
		right: 30rpx;
		bottom: 30rpx;
		width: 70rpx;
		height: 36rpx;
		background-color: rgba(0,0,0,.15);
		border-radius: 20rpx;
		font-size: 22rpx;
		color: #fff;
	}
	.detail-info{
		padding: 20rpx 30rpx;
	}
	.detail-name{
		font-size: 30rpx;
		color: #333;
		font-weight: bold;
	}
	.detail-name text{
		margin-left: 10rpx;
		width:110rpx;
		height: 42rpx;
		border:1px solid #f00d00;
		border-radius: 30rpx;
		box-sizing: border-box;
		font-size: 28rpx;
		font-weight: normal;
		color:#f10d00;
	}
	.detail-desc{
		margin-top:15rpx;
		font-size: 24rpx;
		color: #666;
	}
	.detail-num{
		margin-top:26rpx;
		font-size: 22rpx;
		color:#999
	}
	.detail-price{
		line-height: 1;
		font-size: 28rpx;
		color:#e83826;
	}
	.detail-price text{
		font-size: 36rpx;
	}
	.detail-select{
		padding: 0 30rpx;
	}
	.detail-select-item{
		height: 80rpx;
		border-bottom: 1px solid #ddd;
	}
	.detail-select-item:last-child{
		border-bottom: 0;
	}
	.detail-select-item text{
		margin-right: 20rpx;
		font-size: 28rpx;
		color:#666;
	}
	.detail-select-item view{
		width: 50%;
		font-size: 28rpx;
		color:#333;
	}
	.detail-select-item image{
		margin-left: 20rpx;
		width:14rpx;
		height: 26rpx;
	}
	.detail-tit{
		padding: 0 30rpx;
		height: 90rpx;
		font-size: 34rpx;
		font-weight: bold;
		color:#333;
	}
	.detail-img{
		width:100%;
	}
	.detail-foot{
		height: 98rpx;
		box-shadow: 0 0 8rpx rgba(0,0,0,.15);
	}
	.detail-foot-cart{
		width:200rpx;
		height:100%;
		font-size: 24rpx;
		color:#999;
	}
	.detail-foot-cart image{
		margin-bottom:4rpx;
		width:37rpx;
		height:37rpx;
	}
	.detail-foot-add{
		width:275rpx;
		height: 100%;
		background-color: #9ac948;
		font-size: 30rpx;
		color:#fff;
	}
	.detail-foot-buy{
		width:20%;
		height: 100%;
		background-color: #18ACFC;
		font-size: 30rpx;
		color:#fff;
	}
	.detail-points{
		margin-top: 26rpx;
	}
	.detail-points-price{
		margin-top: -6rpx;
		font-size: 26rpx;
		color: #e83826;
	}
	.detail-points-price text{
		font-size: 36rpx;
		font-weight: 400;
	}
	.detail-points-sales{
		font-size: 22rpx;
		color: #999;
	}
	.detail-points-total{
		margin-left: 48rpx;
		font-size: 22rpx;
		color: #999;
	}
	.detail-points-total text{
		margin-left: 10rpx;
		color: #18ACFC;
	}
</style>
