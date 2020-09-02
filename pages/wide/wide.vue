<template>
	<view class="wide-container">
		<view class="d-flex">
			<view class="wide-top d-flex d-flex-middle">
				<image src="../../static/wide-route.png" class="wide-top-img"/>
				<view class="wide-top-text">
					<view>100M</view>
					<text>您已开通1条宽带</text>
				</view>
			</view>
			<view class="wide-top d-flex d-flex-middle">
				<image src="../../static/wide-TV.png" class="wide-top-img"/>
				<view class="wide-top-text">
					<view>未开通</view>
					<text>您还未开通TV</text>
				</view>
			</view>
		</view>
		<view class="wide-account d-flex d-flex-middle d-flex-center">当前账号  <text class="color-text-blue">15827274242</text></view>
		<view class="wide-family">
			<wide-title title="家庭宽带"/>
			<view class="wide-family-con">
				<view class="d-flex d-flex-between">
					<wide-item @click.native="linkTo('../newly/newly?type=0')" icon="../../static/wide-route-blue.png" title="宽带新装" desc=""/>
					<wide-item icon="../../static/wide-route-blue.png" title="宽带续费" desc=""/>
				</view>
				<view class="wide-family-fix d-flex d-flex-between">
					<view @click="showAlert" class="d-flex d-flex-middle d-flex-center"><image src="../../static/wide-nav01.png"/>宽带排障</view>
					<view @click="showAlert" class="d-flex d-flex-middle d-flex-center"><image src="../../static/wide-nav02.png"/>信号勘测</view>
					<view @click="showAlert" class="d-flex d-flex-middle d-flex-center"><image src="../../static/wide-nav03.png"/>一键测速</view>
				</view>
			</view>
		</view>
		<view class="wide-tv">
			<wide-title title="家庭TV"/>
			<view class="wide-tv-con d-flex d-flex-between">
				<wide-item @click.native="linkTo('../newly/newly?type=1')" icon="../../static/wide-TV-blue.png" title="TV新装" desc=""/>
				<wide-item icon="../../static/wide-TV-blue.png" title="TV续费" desc=""/>
			</view>
		</view>
		<view class="wide-ad d-flex d-flex-middle d-flex-center">
			<image src="../../static/wide-ad.png"/>
		</view>
		<view class="wide-recommond">
			<wide-title title="新品推荐"/>
			<view class="wide-goods d-flex d-flex-wrap d-flex-between">
				<goods v-for="(item,index) in 7" :key="index"/>
			</view>
		</view>
	</view>
</template>

<script>
	import WideTitle from '../../components/lyl/title.vue'
	import WideItem from '../../components/lyl/wide-item.vue'
	import Goods from '../../components/lyl/goods.vue'
	import util from '../../common/util.js'
	export default {
		components:{
			WideTitle,
			WideItem,
			Goods
		},
		data() {
			return {
				
			}
		},
		methods: {
			linkTo(url){
				uni.navigateTo({
					url:url
				})
			},
			showAlert(){
				util.showToast('此功能还在开发中......')
			}
		}
	}
</script>

<style scoped>
	.wide-container{
		padding:50rpx 30rpx 0;
		background: url('~@/static/wide-head-bg.png') no-repeat 0 0;
		background-size:100% 556rpx;
	}
	.wide-top{
		width: 50%;
		color:#fff;
	}
	.wide-top-img{
		margin-right: 12rpx;
		width: 71rpx;
		height: 64rpx;
	}
	.wide-top-text{
		font-size: 24rpx;
	}
	.wide-top-text view{
		margin-bottom:10rpx;
		font-size: 34rpx;
	}
	.wide-account{
		margin-top:40rpx;
		height: 68rpx;
		background-color: #fff;
		border-radius: 10rpx;
		font-size: 30rpx;
		color: #333;
	}
	.wide-account text{
		color:#2a93fd;
	}
	.wide-family{
		margin-top:60rpx;
		background-color: #fff;
		border-radius: 15rpx;
	}
	.title-link{
		font-weight: normal;
		font-size: 24rpx;
		color:#2a93fd;
	}
	.wide-family-con{
		padding:0 30rpx;
	}
	.wide-family-fix{
		margin-top: 20rpx;
	}
	.wide-family-fix view{
		width: 196rpx;
		height: 68rpx;
		background-color: #f2f2f2;
		border-radius: 10rpx;
		font-size: 24rpx;
		color:#666;
	}
	.wide-family-fix image{
		margin-right: 10rpx;
		width: 32rpx;
		height: 32rpx;
	}
	.wide-tv{
		margin-top: 30rpx;
	}
	.wide-tv-con{
		padding:0 30rpx;
	}
	.wide-ad{
		margin-top:30rpx;
	}
	.wide-ad image{
		width: 720rpx;
		height: 190rpx;
	}
	.wide-recommond{
		margin-top:30rpx;
	}
	.wide-goods{
		padding:0 4rpx;
	}
</style>
