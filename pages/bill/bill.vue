<template>
	<view class="bill-container d-flex d-flex-column">
		<view class="bill-nav d-flex-unShrink">
			<bill-nav/>
		</view>
		<view class="bill-content d-flex-item">
			<view class="bill-con">
				<view class="d-flex d-flex-middle d-flex-between">
					<view class="bill-account d-flex d-flex-middle"><image src="../../static/bill-level-3.png"/>158****4283<text>（**凡）</text></view>
					<view class="bill-date d-flex d-flex-middle"><image src="../../static/icon-clock.png"/>8月1日-8月16</view>
				</view>
				<view class="bill-consumption d-flex d-flex-column d-flex-middle d-flex-center">
					<view>您本号码消费（元）</view>
					<text>45.38</text>
				</view>
				<view class="bill-order-tit d-flex d-flex-between">
					<view>消费项目</view>
					<view>消费金额</view>
				</view>
				<view class="bill-order-item item1">
					<view class="bill-order-item-tit">套餐及固定费</view>
					<view class="bill-order-item-sec d-flex d-flex-between"><view>来电显示月租</view> <text>0.00</text></view>
					<view class="bill-order-item-sec d-flex d-flex-between"><view>移动大流量套餐98元</view> <text>45.08</text></view>
				</view>
				<view class="bill-order-item item2">
					<view class="bill-order-item-tit">套餐外短信费</view>
					<view class="bill-order-item-sec d-flex d-flex-between"><view>短信通信费</view> <text>0.00</text></view>
				</view>
				<view class="bill-order-item item3">
					<view class="bill-order-item-tit">套餐外短信费</view>
					<view class="bill-order-item-sec d-flex d-flex-between"><view>和彩云等中移互联业务包月费</view> <text>0.00</text></view>
				</view>
				<view class="bill-order-total d-flex d-flex-between">
					<view>合计</view>
					<text>45.38</text>
				</view>
			</view>
			<view class="bill-tips">
				<view>1.以上是您本月通过话费支付订购和使用移动业务/服务的消费记录。</view>
				<view>2.以上是您本月通过话费支付订购和使用移动业务。</view>
			</view>
		</view>
	</view>
</template>

<script>
	import BillNav from '../../components/lyl/bill-nav.vue'
	export default {
		components:{
			BillNav
		},
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style scoped>
	page{
		height: 100%;
	}
	.bill-container{
		height: 100%;
		background-color: #0b1026;
	}
	.bill-nav{
		padding: 20rpx 0;
	}
	.bill-content{
		height: 50%;
		overflow-y: auto;
	}
	.bill-con{
		padding: 20rpx 30rpx;
	}
	.bill-account{
		font-size: 36rpx;
		color: #fff;
	}
	.bill-account image{
		margin-right: 10rpx;
		width: 34rpx;
		height: 40rpx;
	}
	.bill-account text{
		font-size: 24rpx;
	}
	.bill-date{
		padding-right: 20rpx;
		height: 38rpx;
		background: linear-gradient(180deg,rgba(255,167,54,.1) 0%,rgba(255,208,92,.1) 100%);
		border-radius: 20rpx;
		font-size:22rpx;
		color: #ffac3a;
	}
	.bill-date image{
		margin-right: 10rpx;
		width: 30rpx;
		height: 30rpx;
	}
	.bill-consumption{
		margin-top: 18rpx;
		height: 200rpx;
		background-color: #23283c;
		border-radius: 10rpx;
		font-size: 26rpx;
		color: #fff;
	}
	.bill-consumption text{
		margin-top: 14rpx;
		font-size: 66rpx;
	}
	.bill-order-tit{
		margin-top: 36rpx;
		padding: 0 40rpx;
		font-size: 26rpx;
		color: #fff;
	}
	.bill-order-item{
		margin: 20rpx 0;
		padding: 26rpx 0 28rpx 40rpx;
		border-radius: 10rpx;
	}
	.bill-order-item.item1{
		background:#23283c url('~@/static/bill-line01.png') no-repeat 0 center;
		background-size: 10rpx 120rpx;
	}
	.bill-order-item.item2{
		background:#23283c url('~@/static/bill-line02.png') no-repeat 0 center;
		background-size: 10rpx 120rpx;
	}
	.bill-order-item.item3{
		background:#23283c url('~@/static/bill-line03.png') no-repeat 0 center;
		background-size: 10rpx 120rpx;
	}
	.bill-order-item-tit{
		font-size: 32rpx;
		font-weight: bold;
		color: #fff;
	}
	.bill-order-item-sec{
		margin-top: 15rpx;
		font-size: 28rpx;
	}
	.bill-order-item-sec view{
		max-width: 350rpx;
		color: rgba(255,255,255,.7);
	}
	.bill-order-item-sec text{
		width: 165rpx;
		color: #18ACFC;
	}
	.bill-order-total{
		padding: 0 40rpx;
		font-size: 30rpx;
		color: #fff;
	}
	.bill-order-total text{
		font-size: 36rpx;
	}
	.bill-tips{
		padding: 20rpx 30rpx;
		background: linear-gradient(360deg,rgba(11,16,38,0) 0%,rgba(93,106,161,.2) 100%);
		border-radius: 10rpx 10rpx 0 0;
		line-height: 1.5;
		font-size: 24rpx;
		color: #fff;
	}
</style>
