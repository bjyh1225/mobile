<template>
	<view class="index-btn-container d-flex d-flex-middle d-flex-center">
		<image :src="icon"/>
		<view>{{text}}</view>
	</view>
</template>

<script>
	export default {
		props:['icon','text']
	}
</script>

<style lang="stylus" scoped>
	.index-btn-container{
		width 196rpx
		height 68rpx
		background-color #fff
		box-shadow 0 1px 10rpx rgba(0,0,0,.1)
		border-radius 40rpx
		font-size 24rpx
		color #333
		image{
			margin-right 10rpx
			width 30rpx
			height 30rpx
		}
	}
</style>
