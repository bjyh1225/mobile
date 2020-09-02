<template>
	<view>
		<view class="index-content">
			<view class="index-balance">
				<view class="index-balance-tit d-flex d-flex-between d-flex-middle">
					<view>本月当前余额</view>
					<navigator url="../recharge/recharge?type=0" hover-class="none" class="title-link">去充值></navigator>
				</view>
				<index-balance/>
			</view>
			<view class="index-nav d-flex d-flex-between">
				<index-btn @click.native="linkTo('../personalRate/personalRate')" icon="../../static/index-nav01.png" text="套餐余量"/>
				<index-btn @click.native="linkTo('../ahead-5g/ahead-5g')" icon="../../static/index-nav02.png" text="5G套餐"/>
				<index-btn @click.native="linkTo('../bill/bill')" icon="../../static/index-nav03.png" text="我的账单"/>
			</view>
			<view class="index-sec">
				<index-title title="流量查询"/>
				<view class="index-flow">
					<view class="index-flow-2 d-flex d-flex-between">
						<view class="d-flex d-flex-middle d-flex-center">国内流量已用：<text>9.5GB</text></view>
						<view class="d-flex d-flex-middle d-flex-center">其中本号已用：<text>9.5GB</text></view>
					</view>
					<view class="index-flow-3 d-flex d-flex-between">
						<view class="index-flow-item d-flex d-flex-column d-flex-center">
							<view class="index-flow-item-tit">通用流量已用</view>
							<view class="index-flow-item-con"><text>9.5</text>GB</view>
						</view>
						<view class="index-flow-item d-flex d-flex-column d-flex-center">
							<view class="index-flow-item-tit">通用流量剩余</view>
							<view class="index-flow-item-con"><text>9.5</text>GB</view>
						</view>
						<view class="index-flow-item d-flex d-flex-column d-flex-center">
							<view class="index-flow-item-tit">其他流量</view>
							<view class="index-flow-item-con"><text>暂无</text></view>
						</view>
					</view>
				</view>
			</view>
			<view class="index-sec">
				<index-title title="语音查询">
					<navigator url="../recharge/recharge?type=1" hover-class="none" class="title-link">去充值></navigator>
				</index-title>
				<view class="index-voice">
					<index-balance/>
				</view>
			</view>
			<view class="index-nav d-flex d-flex-between">
				<index-btn @click.native="linkTo('../personalRate/personalRate')" icon="../../static/index-nav01.png" text="套餐余量"/>
				<index-btn @click.native="linkTo('../ahead-5g/ahead-5g')" icon="../../static/index-nav02.png" text="5G套餐"/>
				<index-btn @click.native="linkTo('../bill/bill')" icon="../../static/index-nav03.png" text="我的账单"/>
			</view>
		</view>
		<image src="../../static/index-bottom.png" class="index-botm"/>
		<view class="index-foot d-flex d-flex-middle d-flex-center">
			<image src="../../static/index-foot.png"/>
		</view>
		<view style="padding:100rpx 30rpx;background-color: pink;">
			这里是测试用的
			<view style="height: 30rpx;"></view>
			<navigator url="../mall/mall">积分商城</navigator>
			<view style="height: 30rpx;"></view>
			<navigator url="../wide/wide">宽带业务</navigator>
			<view style="height: 30rpx;"></view>
			<navigator url="../search/search">搜索</navigator>
			<view style="height: 30rpx;"></view>
			<!-- <navigator url="../exchange/exchange">积分兑换</navigator> -->
			<view style="height: 30rpx;"></view>
			<!-- <navigator url="../detail/detail">商品详情</navigator> -->
			<view style="height: 30rpx;"></view>
			<!-- <navigator url="../recharge/recharge">充值中心</navigator> -->
			<view style="height: 30rpx;"></view>
			<!-- <navigator url="../bill/bill">话费账单</navigator> -->
			<view style="height: 30rpx;"></view>
			<!-- <navigator url="../newly/newly">新装宽带/TV</navigator> -->
		</view>
	</view>
</template>

<script>
	import IndexBtn from '../../components/lyl/index-btn.vue'
	import IndexBalance from '../../components/lyl/index-balance.vue'
	import IndexTitle from '../../components/lyl/title.vue'
	export default {
		components:{
			IndexBtn,
			IndexBalance,
			IndexTitle
		},
		data() {
			return {
				title: 'Hello'
			}
		},
		methods: {
			linkTo(url){
				console.log('url=====',url)
				uni.navigateTo({
					url:url
				})
			}
		}
	}
</script>

<style scoped>
	.index-content{
		padding: 580rpx 30rpx 0;
		background: url('~@/static/index-head-bg.png') no-repeat 0 0;
		background-size: 100% 750rpx;
	}
	.index-balance{
		padding:0 30rpx;
		background-color: #fff;
		border-radius: 15rpx;
	}
	.index-balance-tit{
		height: 100rpx;
		border-bottom:1px solid #ddd;
		font-size: 34rpx;
		color: #333;
	}
	.title-link{
		font-size: 24rpx;
		font-weight: normal;
		color: #18acfc;
	}
	.index-nav{
		padding: 10rpx 20rpx;
	}
	.index-sec{
		margin-top:50rpx;
		background: linear-gradient(180deg,rgba(24,172,252,.08) 0%,rgba(255,255,255,0) 100%);
		border-radius: 20rpx;
	}
	.index-flow{
		padding:0 30rpx;
	}
	.index-flow-2{
		height: 80rpx;
	}
	.index-flow-2 view{
		width: 305rpx;
		height: 100%;
		background-color: #f2f2f2;
		border-radius: 10rpx;
		font-size: 24rpx;
		color: #666;
	}
	.index-flow-2 text{
		font-weight: 400;
		color: #333;
	}
	.index-flow-3{
		margin-top: 20rpx;
	}
	.index-flow-item{
		padding-left: 20rpx;
		width: 196rpx;
		height: 142rpx;
		background-color: #F2F2F2;
		border-radius: 10rpx;
		box-sizing: border-box;
	}
	.index-flow-item-tit{
		font-size: 26rpx;
		color: #666666;
	}
	.index-flow-item-con{
		margin-top:10rpx;
		font-size: 24rpx;
		color:#333333;
	}
	.index-flow-item-con text{
		font-size: 46rpx;
		font-weight: bold;
	}
	.index-voice{
		padding:0 30rpx;
		width: 100%;
		border-top:1px solid #ddd;
		box-sizing: border-box;
	}
	.index-botm{
		margin-top:50rpx;
		width:100%;
		height: 180rpx;
	}
	.index-foot{
		height: 120rpx;
	}
	.index-foot image{
		width:304rpx;
		height:60rpx;
	}
</style>
