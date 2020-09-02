<template>
	<view class="index-balance-container d-flex d-flex-middle">
		<view class="sec">
			<view class="tit">账户余额</view>
			<view class="money d-flex d-flex-bottom"><text>150.03</text>元</view>
		</view>
		<view class="sec">
			<view class="right tit d-flex d-flex-middle">当月消费 <view class="num d-flex d-flex-middle"><text>52.83</text>元</view></view>
			<view class="right tit d-flex d-flex-middle">可用余额 <view class="num d-flex d-flex-middle"><text>52.83</text>元</view></view>
		</view>
	</view>
</template>

<script>
</script>

<style lang="stylus" scoped>
	.index-balance-container{
		position relative
		width 100%
		height 145rpx
		&::after{
			content ''
			position absolute
			left 50%
			top 50%
			width 0
			height 74rpx
			margin-top -37rpx
			border-left 1px solid #ddd
		}
		.sec{
			width 50%
			.tit{
				font-size 26rpx
				color #666
			}
			.money{
				margin-top 25rpx
				line-height 0.5
				font-size 24rpx
				color #333
				text{
					font-size 46rpx
					font-weight bold
				}
			}
			.right{
				margin 16rpx 0 16rpx 30rpx
				.num{
					font-size 22rpx
					color #333
					text{
						font-size 30rpx
						font-weight bold
					}
				}
			}
		}
	}
</style>
