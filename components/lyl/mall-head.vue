<template>
	<view class="mall-head-container d-flex d-flex-column d-flex-center">
		<view class="tit">当前积分</view>
		<view class="points d-flex d-flex-bottom"><text>123123</text>分</view>
	</view>
</template>

<script>
</script>

<style lang="stylus" scoped>
	.mall-head-container{
		padding 0 200rpx 0 60rpx
		width 100%
		height 245rpx
		box-sizing border-box
		background url('~@/static/mall-head-bg.png') no-repeat 0 0
		background-size 100% 100%
		.tit{
			font-size 26rpx
			color #fff
		}
		.points{
			margin-top 20rpx
			line-height 0.5
			font-size 24rpx
			color #fff
			text{
				font-size 46rpx
				font-weight bold
			}
		}
	}
</style>
