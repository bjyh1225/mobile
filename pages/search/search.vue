<template>
	<view class="search-container">
		<view class="search-head">
			<view class="search-input d-flex d-flex-middle">
				<image src="../../static/icon-search.png" class="d-flex-unShrink"/>
				<input type="text" placeholder="搜索热门服务" class="d-flex-item"/>
				<view class="d-flex d-flex-middle d-flex-center">取消</view>
			</view>
			<view class="search-sec">
				<view class="search-sec-tit d-flex d-flex-between d-flex-middle">历史搜索 <image src="../../static/icon-trush.png"/></view>
				<view class="search-history d-flex d-flex-wrap">
					<text class="d-flex d-flex-middle">流量可选包</text>
					<text class="d-flex d-flex-middle">5G个人套餐</text>
					<text class="d-flex d-flex-middle">流量7天包</text>
					<text class="d-flex d-flex-middle">积分兑换</text>
				</view>
			</view>
			<view class="search-sec">
				<view class="search-sec-tit">热门业务</view>
				<view class="search-nav d-flex d-flex-middle d-flex-between">
					<view class="on">个人资费</view>
					<image src="../../static/icon-divider.png"/>
					<view>超前5G</view>
					<image src="../../static/icon-divider.png"/>
					<view>宽带业务</view>
					<image src="../../static/icon-divider.png"/>
					<view>积分商城</view>
				</view>
			</view>
		</view>
		<view class="search-list d-flex d-flex-wrap">
			<view v-for="(item,index) in 5" :key="index" class="search-item d-flex d-flex-column d-flex-middle">
				<image src="../../static/search-icon01.png"/>
				<view>余额</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style scoped>
	.search-head{
		padding:30rpx 30rpx 0;
	}
	.search-input{
		position: relative;
		padding-right: 150rpx;
		height: 68rpx;
		background-color: #f2f2f2;
		border-radius: 40rpx;
	}
	.search-input image{
		padding: 10rpx 20rpx;
		width: 28rpx;
		height: 28rpx;
		box-sizing: content-box;
	}
	.search-input input{
		width: 50%;
		height: 100%;
		font-size: 26rpx;
		color:#333;
	}
	.search-input view{
		position: absolute;
		top:0;
		right:0;
		width: 120rpx;
		height: 100%;
		background:linear-gradient(180deg,rgba(80,197,253,1) 0%,rgba(40,145,254,1) 100%);
		box-shadow: 0 1px 6rpx rgba(0,0,0,.1);
		border-radius: 40rpx;
		font-size: 30rpx;
		color: #fff;
	}
	.search-sec{
		margin-top: 35rpx;
	}
	.search-sec-tit{
		font-size: 34rpx;
		font-weight: bold;
		color:#333;
	}
	.search-sec-tit image{
		width: 32rpx;
		height: 35rpx;
	}
	.search-history{
		margin-top: 12rpx;
	}
	.search-history text{
		margin-right: 20rpx;
		padding: 0 20rpx;
		height: 44rpx;
		background-color: #f2f2f2;
		border-radius: 25rpx;
		font-size: 24rpx;
		color: #666;
	}
	.search-nav{
		margin-top: 15rpx;
	}
	.search-nav view{
		width: 140rpx;
		text-align:center;
		font-size: 30rpx;
		color:#333;
	}
	.search-nav .on{
		position: relative;
	}
	.search-nav .on::after{
		content: '';
		position: absolute;
		left:50%;
		bottom:-6rpx;
		width:40rpx;
		height: 6rpx;
		margin-left:-20rpx;
		background-color: #18ACFC;
		border-radius: 5rpx;
	}
	.search-nav image{
		width: 19rpx;
		height: 38rpx;
	}
	.search-list{
		margin-top: 40rpx;
		padding-left: 30rpx;
	}
	.search-item{
		margin:0 20rpx 20rpx;
		width: 100rpx;
		font-size: 26rpx;
		color: #666;
	}
	.search-item image{
		margin-bottom:4rpx;
		width:100rpx;
		height: 100rpx;
	}
</style>
