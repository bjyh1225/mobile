<template>
	<view class="persona-rate d-flex d-flex-column">
		<view class="content d-flex-item">
			<image mode="widthFix" src="../../static/personal-rate.png"/>
		</view>
		 <view class="btn-color d-flex-unShrink d-flex d-flex-middle d-flex-center">换套餐</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style>
	page{
		height: 100%;
	}
.persona-rate {
	height: 100%;
	}
	.content{
		height: 50%;
		overflow-y: auto;
	}
	.content image{
		width: 100%;
	}
	.btn-color{
		height: 98rpx;
		background-color: #18ACFC;
		font-size: 30rpx;
		color:#fff;
	}
</style>
