<template>
	<view @click="toDetail" class="goods-container">
		<view class="img color-bg-grey d-flex d-flex-middle d-flex-center"><image src="../../static/img01.png"/></view>
		<view class="text d-flex d-flex-column d-flex-middle">
			<view class="name color-text-main d-ellipsis-single">小荷MINI10</view>
			<view class="price color-text-red">¥299.00</view>
		</view>
	</view>
</template>

<script>
	export default {
		methods:{
			toDetail(){
				uni.navigateTo({
					url:'../../pages/detail/detail?type=goods'
				})
			}
		}
	}
</script>

<style lang="stylus" scoped>
	.goods-container{
		margin-bottom 30rpx
		width 335rpx
		.img{
			width 100%
			height 312rpx
			image{
				width 181rpx
				height 186rpx
			}
		}
		.text{
			padding 24rpx 20rpx 0
			font-size 26rpx
			.name{
				
			}
			.price{
				margin-top 8rpx
			}
		}
	}
</style>
