<template>
	<view class="detail-level-container">
		<view class="title d-flex d-flex-middle">可选挡位</view>
		<view class="list d-flex d-flex-wrap d-flex-between">
			<view v-for="(item,index) in 4" :key="index" class="item fill d-flex d-flex-middle d-flex-center">500兑30分钟</view>
		</view>
	</view>
</template>

<script>
</script>

<style lang="stylus" scoped>
	.detail-level-container{
		padding 0 30rpx 20rpx
		.title{
			height 88rpx
			font-size 34rpx
			font-weight bold
			color #333
		}
		.item{
			margin-bottom 20rpx
			width 335rpx
			height 68rpx
			border 1px solid #666
			border-radius 10rpx
			box-sizing border-box
			font-size 30rpx
			color #333
			&.on{
				border-color #f10d00
				color #f10d00
			}
		}
		.item.fill{
			background-color #f2f2f2
			border-color #f2f2f2
			&.on{
				background-color rgba(240,13,0,.1)
				border-color rgba(240,13,0,.1)
			}
		}
	}
</style>
