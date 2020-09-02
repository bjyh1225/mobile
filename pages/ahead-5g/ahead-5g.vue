<template>
	<view class="ahead-container">
		<view class="set-meal d-flex d-flex-middle">
			<view @click="toDetail('../detail/detail?type=0')" class="d-flex d-flex-column">
				<image class="meal-size" src="../../static/set-meal-1.png" />
				<view class="d-flex d-flex-column meal-font">
					<text class="font-set">5G智享套餐</text>
					<text class="font-set">（个人版）</text>
				</view>
			</view>
			<view @click="toDetail('../detail/detail?type=1')" class="d-flex d-flex-column">
				<image class="meal-size" src="../../static/set-meal-2.png" />
				<view class="d-flex d-flex-column meal-font">
					<text class="font-set">5G智享套餐</text>
					<text class="font-set">（家庭版A）</text>
				</view>
			</view>
			<view @click="toDetail('../detail/detail?type=2')" class="d-flex d-flex-column">
				<image class="meal-size" src="../../static/set-meal-3.png" />
				<view class="d-flex d-flex-column meal-font">
					<text class="font-set">5G智享套餐</text>
					<text class="font-set">（家庭版B）</text>
				</view>
			</view>
		</view>
		<!-- 流量 -->
		<view class="flow d-flex d-flex-middle">
			<view @click="toDetail('../detail/detail?type=3')" class="d-flex d-flex-column">
				<image class="meal-size" src="../../static/5g-flow-1.png" />
				<view class="d-flex d-flex-column meal-font">
					<text class="font-set">5G特惠流量包</text>	
				</view>
			</view>
			<view @click="toDetail('../detail/detail?type=3')" class="d-flex d-flex-column">
				<image class="meal-size" src="../../static/5g-flow-2.png" />
				<view class="d-flex d-flex-column meal-font">
					<text class="font-set">流量7天包</text>
				</view>
			</view>
			<view @click="toDetail('../detail/detail?type=3')" class="d-flex d-flex-column">
				<image class="meal-size" src="../../static/5g-flow-3.png" />
				<view class="d-flex d-flex-column meal-font">
					<text class="font-set">5G直通包</text>
				</view>
			</view>
		</view>
		<!-- 手机 -->
		<view class="phone-5g d-flex d-flex-middle">
			<view v-for="(item,index) in 6" :key="index" @click="toDetail('../detail/detail?type=goods')" class="d-flex d-flex-column">
				<image class="phone-size" src="../../static/phone-5g.png" />
				<view class="d-flex d-flex-column phone-font">
					<text class="font-set">华为P30r 5G手机</text>
					<text class="font-set-color">￥4599.00</text>	
				</view>
			</view>
		</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		methods: {
			toDetail(url){
				uni.navigateTo({
					url:url
				})
			}
		}
	}
</script>

<style>
	page{
		background-color: #ad82f7;
	}
	.ahead-container {
		width: 100vw;
		height: 180vh;
		text-align: center;
		background: url('../../static/ahead-5g-bg.png') no-repeat;
		background-size: 100%;
	} 
	.set-meal{
		/* align-items: center; */
		width: 92%;
		height: 15%;
		/* background-color: red; */
		margin: 0 auto;
		justify-content: space-evenly;
		position: relative;
		top: 460rpx;
	}
	.meal-font{
		background: #43A1F7;
		height: 100rpx;
		width: 180rpx;
		border-radius: 0 0 10rpx 10rpx;
		justify-content: center;
	}
	.meal-size {
		width: 180rpx;
		height: 180rpx;
	}

	.font-set {
		color: #ffffff;
		font-size: 24rpx;
	}
	.flow{
		width: 92%;
		height: 15%;
		/* background-color: red; */
		margin: 0 auto;
		justify-content: space-evenly;
		position: relative;
		top: 530rpx;
	}
	.phone-5g{
		width: 100%;
		/* height: 65%; */
		/* background-color: red; */
		margin: 0 auto;
		justify-content: space-evenly;
		position: relative;
		top: 740rpx;
		flex-wrap: wrap;
	}
	.phone-size {
		width: 325rpx;
		height: 325rpx;
	}
	.phone-font{
		height: 120rpx;
		width: 325rpx;
		justify-content: center;
		line-height: 40rpx;
	}
	.font-set-color {
		color: #D6DE00;
		font-size: 24rpx;
	}
</style>
