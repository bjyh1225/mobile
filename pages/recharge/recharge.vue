<template>
	<view class="recharge-container d-flex d-flex-column">
		<view class="recharge-nav d-flex-unShrink d-flex d-flex-middle">
			<text v-for="(item,index) in nav" :key="index" @click="switchNav(index)" :class="{on:item.isChecked}">{{item.text}}</text>
		</view>
		<view class="recharge-con d-flex-item">
			<view class="recharge-wrap">
				<view class="recharge-head d-flex d-flex-middle">
					<view class="recharge-head-account d-flex-item">
						<view class="recharge-head-tit">默认号码（移动）</view>
						<view class="recharge-head-num d-flex d-flex-middle">
							<input disabled type="text" placeholder="158 2742 4248" class="d-flex-item"/>
							<image src="../../static/icon-edit.png" class="d-flex-unShrink"/>
						</view>
					</view>
					<view class="recharge-head-other d-flex-unShrink d-flex d-flex-column d-flex-middle d-flex-center">
						<image src="../../static/icon-phoneBook.png"/>
						<view>给他人充</view>
					</view>
				</view>
			</view>
			<view class="recharge-list d-flex d-flex-wrap">
				<view v-for="(item,index) in list" :key="index" @click="choose(index)" :class="{on:item.isChecked}" class="recharge-item d-flex d-flex-column d-flex-middle d-flex-center">
					<view>{{selectedIndex==0?'10元':'10GB'}}</view>
					<text v-if="selectedIndex==1">售价：50元</text>
				</view>
			</view>
			<view v-if="selectedIndex==0" class="recharge-wrap"><view class="recharge-diy d-flex d-flex-middle d-flex-center">自定义</view></view>
			<view class="recharge-wrap">
				<view class="recharge-tips d-flex d-flex-between">
					<view>支付金额：<text>9.98</text>元</view>
					<view>到账金额：<text>10.00</text>元</view>
				</view>
			</view>
		</view>
		<view class="recharge-foot d-flex-unShrink d-flex d-flex-middle d-flex-center">立即充值</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				type:0,
				nav:[
					{text:'话费',isChecked:true},
					{text:'流量',isChecked:false}
				],
				selectedIndex:0,
				list:[
					{isChecked:true},
					{isChecked:false},
					{isChecked:false},
					{isChecked:false},
					{isChecked:false},
					{isChecked:false}
				]
			}
		},
		methods: {
			switchNav(index){
				if(this.selectedIndex==index) return
				this.selectedIndex=index
				this.nav.forEach((v,i) => {
					v.isChecked=i==index
				})
			},
			choose(index){
				this.list.forEach((v,i) => {
					v.isChecked=i==index
				})
			}
		},
		onLoad(option){
			this.type=option.type  // 0话费 1流量
			this.switchNav(this.type)
		}
	}
</script>

<style scoped>
	page{
		height: 100%;
	}
	.recharge-container{
		height: 100%;
		background: url('~@/static/recharge-head-bg.png') no-repeat 0 0;
		background-size: 750rpx 220rpx;
	}
	.recharge-nav{
		padding: 0 30rpx;
		height: 110rpx;
		background: url('~@/static/recharge-head-bg.png') no-repeat 0 0;
		background-size: 750rpx 220rpx;
	}
	.recharge-nav text{
		width: 50%;
		text-align: center;
		font-size: 34rpx;
		font-weight: 500;
		color: #fff;
	}
	.recharge-nav .on{
		position: relative;
	}
	.recharge-nav .on::after{
		content: '';
		position: absolute;
		left: 50%;
		bottom: -20rpx;
		width: 80rpx;
		height: 8rpx;
		margin-left: -40rpx;
		background-color: #fff;
		border-radius: 6rpx;
	}
	.recharge-con{
		padding: 20rpx 0 20rpx 30rpx;
		height: 50%;
		overflow-y: auto;
	}
	.recharge-wrap{
		padding-right: 30rpx;
	}
	.recharge-head{
		height: 188rpx;
		background-color: #fff;
		border-radius: 20rpx;
		box-shadow: 0 3rpx 6rpx rgba(0,0,0,.1);
	}
	.recharge-head-account{
		padding: 0 40rpx;
		width: 50%;
	}
	.recharge-head-tit{
		font-size: 28rpx;
		color: #666;
	}
	.recharge-head-num{
		margin-top: 20rpx;
	}
	.recharge-head-num input{
		width: 50%;
		height: 60rpx;
		font-size: 48rpx;
		font-weight: bold;
		color: #333;
	}
	.recharge-head-num image{
		margin-left: 60rpx;
		width: 35rpx;
		height: 34rpx;
	}
	.recharge-head-other{
		width: 165rpx;
		height: 120rpx;
		border-left: 1px solid #ddd;
		font-size: 24rpx;
		color: #18ACFC;
	}
	.recharge-head-other image{
		margin-bottom:6rpx;
		width: 48rpx;
		height: 57rpx;
	}
	.recharge-list{
		margin-top: 40rpx;
	}
	.recharge-item{
		margin:0 20rpx 20rpx 0;
		padding: 18rpx 0;
		width: 216rpx;
		border: 1px solid #707070;
		border-radius: 10rpx;
		box-sizing: border-box;
		font-size: 30rpx;
		font-weight: 500;
		color: #666;
	}
	.recharge-item.on{
		border-color: rgba(24,172,252,.2);
		background-color: rgba(24,172,252,.2);
		color: #18ACFC;
	}
	.recharge-item text{
		margin-top: 6rpx;
		font-size: 24rpx;
		font-weight: normal;
	}
	.recharge-diy{
		height: 80rpx;
		border: 1px solid #707070;
		border-radius: 10rpx;
		box-sizing: border-box;
		font-size: 30rpx;
		color: #666;
	}
	.recharge-tips{
		margin-top: 16rpx;
		font-size: 30rpx;
		font-weight: bold;
		color: #333;
	}
	.recharge-tips text{
		color: #18ACFC;
	}
	.recharge-foot{
		height: 98rpx;
		background-color: #18ACFC;
		font-size: 30rpx;
		color: #fff;
	}
</style>
