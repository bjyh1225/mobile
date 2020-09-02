<template>
	<view class="detail-msg-container d-flex">
		<view class="tit d-flex-unShrink">短信兑换</view>
		<view class="desc d-flex-item d-ellipsis-multiple">发短信兑123换发短456信兑换789发短信兑换发短信发短信兑换发短信兑换发短信兑换发...</view>
		<image src="../../static/icon-arrow-right.png" class="arrow d-flex-unShrink"/>
	</view>
</template>

<script>
</script>

<style lang="stylus" scoped>
	.detail-msg-container{
		padding 18rpx 30rpx
		font-size 28rpx
		.tit{
			margin-right 20rpx
			color #666
		}
		.desc{
			width 50%
			max-height 74rpx
			line-height 37rpx
			-webkit-line-clamp 2
			color #333
		}
		.arrow{
			margin 6rpx 0 0 40rpx
			width 14rpx
			height 26rpx
		}
	}
</style>
