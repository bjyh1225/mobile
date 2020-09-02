<template>
	<view class="exchange-container d-flex d-flex-column">
		<view class="d-flex-unShrink">
			<view class="exchange-nav d-flex d-flex-around d-flex-middle">
				<text v-for="(item,index) in nav" :key="index" @click="switchNav(index)" :class="{on:item.isChecked}">{{item.text}}</text>
			</view>
			<view class="exchange-filter d-flex d-flex-between d-flex-middle">
				<view>0~15631313积分</view>
				<view class="exchange-filter-sort">积分值</view>
			</view>
		</view>
		<view class="exchange-list d-flex-item">
			<exchange-ticket v-for="(item,index) in 10" :key="index" @onClick="exchange"/>
		</view>
	</view>
</template>

<script>
	import ExchangeTicket from '../../components/lyl/ticket.vue'
	export default {
		components:{
			ExchangeTicket
		},
		data() {
			return {
				type:0, // 0兑流量 1兑通话 2兑好物
				nav:[
					{text:'兑流量',isChecked:true},
					{text:'兑通话',isChecked:false},
					{text:'兑好物',isChecked:false}
				],
				selectedIndex:0
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
			exchange(){
				var type=0
				if(this.selectedIndex==0){
					type=4
				}else if(this.selectedIndex==1){
					type=5
				}else{
					type=6
				}
				uni.navigateTo({
					url:'../detail/detail?type='+type
				})
			}
		},
		onLoad(option){
			this.type=option.type  // 0兑流量 1兑通话 2兑好物
			this.switchNav(this.type)
		}
	}
</script>

<style>
	page{
		height: 100%;
	}
	.exchange-container{
		height: 100%;
	}
	.exchange-nav{
		height: 88rpx;
		background-color: #333;
		font-size: 30rpx;
		color: #fff;
	}
	.exchange-nav .on{
		position: relative;
	}
	.exchange-nav .on::after{
		content: '';
		position: absolute;
		left: 50%;
		bottom: -16rpx;
		width: 40rpx;
		height: 6rpx;
		margin-left: -20rpx;
		background-color: #18ACFC;
		border-radius: 5rpx;
	}
	.exchange-filter{
		position: relative;
		z-index: 9;
		padding:0 60rpx 0 30rpx;
		height: 68rpx;
		box-shadow: 0 3rpx 6rpx rgba(0,0,0,.1);
		font-size: 26rpx;
		color: #000;
	}
	.exchange-filter-sort{
		position: relative;
	}
	.exchange-filter-sort::before{
		content: '';
		position: absolute;
		right: -24rpx;
		top:6rpx;
		width:0;
		height:0;
		border-bottom:12rpx solid #666;
		border-left:10rpx solid transparent;
		border-right:10rpx solid transparent;
	}
	.exchange-filter-sort::after{
		content: '';
		position: absolute;
		right:-24rpx;
		bottom:4rpx;
		border-top:12rpx solid #999;
		border-left:10rpx solid transparent;
		border-right:10rpx solid transparent;
	}
	.exchange-list{
		padding: 30rpx;
		height: 50%;
		overflow-y: auto;
	}
</style>
