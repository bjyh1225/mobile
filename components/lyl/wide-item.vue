<template>
	<view class="wide-item-container d-flex d-flex-middle d-flex-center">
		<image :src="icon" class="img"/>
		<view class="text">
			<view>{{title}}</view>
			<text>居家必备</text>
		</view>
	</view>
</template>

<script>
	export default {
		props:['icon','title','desc']
	}
</script>

<style lang="stylus" scoped>
	.wide-item-container{
		width 305rpx
		height 142rpx
		background-color #f2f2f2
		border-radius 10rpx
		.img{
			margin-right 40rpx
			width 53rpx
			height 46rpx
		}
		.text{
			font-size 24rpx
			color #666
			view{
				margin-bottom 10rpx
				font-size 30rpx
				font-weight bold
				color #333
			}
		}
	}
</style>
