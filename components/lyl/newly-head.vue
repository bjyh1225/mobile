<template>
	<view class="newly-head-container">
		<view class="item">当前号码 <text>15698989898</text></view>
		<view class="item">当前套餐 <text>移动大流量套餐98元</text></view>
		<view class="tips d-flex d-flex-middle"><image src="../../static/icon-warn.png"/>提示当前套餐不包含TV，可升级套餐或单独办理</view>
		<view class="btn d-flex d-flex-middle d-flex-center">去升级</view>
	</view>
</template>

<script>
</script>

<style lang="stylus" scoped>
	.newly-head-container{
		padding 40rpx 45rpx
		background-color #fff
		border-radius 20rpx
		.item{
			position relative
			margin 10rpx 0 18rpx
			padding 0 20rpx
			font-size 30rpx
			color #666
			&::before{
				content ''
				position absolute
				left 0
				top 0
				width 6rpx
				height 100%
				background linear-gradient(180deg,rgba(166,94,241,1) 0%,rgba(190,125,246,1) 100%)
				border-radius 4rpx
			}
			text{
				margin-left 20rpx
				font-weight bold
				color #333
			}
		}
		.tips{
			margin-top 10rpx
			font-size 22rpx
			color #666
			image{
				margin-right 10rpx
				width 30rpx
				height 30rpx
			}
		}
		.btn{
			margin-top 45rpx
			height 80rpx
			background linear-gradient(180deg,rgba(166,94,241,1) 0%,rgba(190,125,246,1) 100%)
			border-radius 40rpx
			font-size 30rpx
			color #fff
		}
	}
</style>
