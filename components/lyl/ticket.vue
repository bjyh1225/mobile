<template>
	<view class="ticket-container color-bg-grey d-flex">
		<image src="../../static/mall-img.png" class="img d-flex-unShrink"/>
		<view class="info d-flex-item d-flex d-flex-column">
			<view class="title color-text-main d-ellipsis-single d-flex-unShrink">兑换100MB国内流量</view>
			<view class="tips d-flex-item">500积分可兑换100MB国内流量</view>
			<view class="color-text-red d-flex-unShrink d-flex d-flex-between d-flex-bottom">
				<view class="points d-flex d-flex-bottom"><text>675</text>积分</view>
				<view @click="exchange" class="btn color-text-red d-flex d-flex-middle d-flex-center">立即兑换</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		methods:{
			exchange(){
				this.$emit('onClick')
			}
		}
	}
</script>

<style lang="stylus" scoped>
	.ticket-container{
		margin-bottom 20rpx
		padding 20rpx
		height 224rpx
		border-radius 8rpx
		box-sizing border-box
		.img{
			margin-right 20rpx
			width 183rpx
			height 183rpx
			background-color #fff
		}
		.info{
			width 50%
			height 100%
			.title{
				font-size 30rpx
			}
			.tips{
				margin-top 4rpx
				font-size 22rpx
				color #666
			}
			.points{
				position relative
				bottom 10rpx
				line-height 0.5
				font-size 24rpx
				text{
					font-size 34rpx
				}
			}
			.btn{
				width 146rpx
				height 54rpx
				background-color #ffebe8
				border-radius 30rpx
				font-size 26rpx
			}
		}
	}
</style>
