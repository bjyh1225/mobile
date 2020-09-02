<template>
	<view class="title-container d-flex d-flex-between d-flex-middle">
		<view class="tit">{{title}}</view>
		<slot></slot>
	</view>
</template>

<script>
	export default {
		props:['title']
	}
</script>

<style lang="stylus" scoped>
	.title-container{
		position relative
		padding 0 30rpx
		height 88rpx
		font-size 34rpx
		font-weight bold
		color #333
		&::before{
			content ''
			position absolute
			left 0
			top 50%
			width 6rpx
			height 38rpx
			margin-top -19rpx
			background-color #18acfc
			border-radius 5rpx
		}
	}
</style>
