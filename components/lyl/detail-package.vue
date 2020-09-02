<template>
	<view class="detail-package-container">
		<view class="item d-flex d-flex-middle">
			<text class="d-flex-unShrink">我的套餐</text>
			<view class="d-flex-item d-ellipsis-single">移动大流量套餐98元/月</view>
			<image src="../../static/icon-arrow-right.png" class="d-flex-unShrink"/>
		</view>
		<view class="item d-flex d-flex-middle">
			<text class="d-flex-unShrink">套餐包含</text>
			<view class="d-flex-item d-ellipsis-single">10GB流量+300分钟通话</view>
		</view>
	</view>
</template>

<script>
</script>

<style lang="stylus" scoped>
	.detail-package-container{
		padding 15rpx 30rpx
		.item{
			height 60rpx
			font-size 30rpx
			text{
				margin-right 20rpx
				color #666
			}
			view{
				width 50%
				color #333
			}
			image{
				margin-left 20rpx
				width 14rpx
				height 26rpx
			}
		}
	}
</style>
