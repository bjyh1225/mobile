<template>
	<view>
		<mall-head/>
		<view class="mall-nav d-flex d-flex-around">
			<view v-for="(item,index) in nav" :key="index" @click="linkTo(index)" class="mall-nav-item d-flex d-flex-column d-flex-middle">
				<image :src="item.src"/>
				<view>{{item.text}}</view>
			</view>
		</view>
		<view class="mall-con">
			<mall-title title="热门兑换"/>
			<view class="mall-tickets">
				<mall-ticket v-for="(item,index) in 3" :key="index" @onClick="exchange"/>
			</view>
			<mall-title title="热门兑换"/>
			<view class="mall-goods d-flex d-flex-wrap d-flex-between">
				<goods v-for="(item,index) in 9" :key="index"/>
			</view>
		</view>
	</view>
</template>

<script>
	import MallHead from '../../components/lyl/mall-head.vue'
	import MallTitle from '../../components/lyl/title.vue'
	import MallTicket from '../../components/lyl/ticket.vue'
	import Goods from '../../components/lyl/goods.vue'
	export default {
		components:{
			MallHead,
			MallTitle,
			MallTicket,
			Goods
		},
		data() {
			return {
				nav:[
					{src:'../../static/mall-nav01.png',text:'兑流量'},
					{src:'../../static/mall-nav02.png',text:'兑通话'},
					// {src:'../../static/mall-nav03.png',text:'领积分'},
					{src:'../../static/mall-nav04.png',text:'兑好物'}
				]
			}
		},
		methods: {
			linkTo(index){
				uni.navigateTo({
					url:'../exchange/exchange?type='+index
				})
			},
			exchange(){
				uni.navigateTo({
					url:'../detail/detail?type=4'
				})
			}
		}
	}
</script>

<style scoped>
	.mall-nav{
		padding: 40rpx 10rpx;
	}
	.mall-nav-item{
		width: 92rpx;
		font-size: 22rpx;
		color:#666;
	}
	.mall-nav-item image{
		margin-bottom:10rpx;
		width:100%;
		height:86rpx;
	}
	.mall-con{
		padding:0 30rpx;
	}
	.mall-tickets{
		margin-bottom:20rpx;
	}
	.mall-goods{
		
	}
</style>
