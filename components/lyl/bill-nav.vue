<template>
	<view class="bill-nav-container">
		<scroll-view scroll-x class="nav">
			<view v-for="(item,index) in date" :key="index" @click="switchNav(index)" :class="{on:item.isChecked}" class="item">
				<view>{{item.month}}月</view>
				<text>{{item.year}}</text>
			</view>
		</scroll-view>
	</view>
</template>

<script>
	export default {
		data(){
			return {
				date:[
					{year:'2020',month:'8',isChecked:true},
					{year:'2020',month:'7',isChecked:false},
					{year:'2020',month:'6',isChecked:false},
					{year:'2020',month:'5',isChecked:false},
					{year:'2020',month:'4',isChecked:false},
					{year:'2020',month:'3',isChecked:false},
					{year:'2020',month:'2',isChecked:false},
					{year:'2020',month:'1',isChecked:false}
				],
				selectedIndex:0
			}
		},
		methods:{
			switchNav(index){
				if(this.selectedIndex==index) return
				this.selectedIndex=index
				this.date.forEach((v,i) => {
					v.isChecked = i === index
				})
			}
		}
	}
</script>

<style lang="stylus" scoped>
	.bill-nav-container{
		.nav{
			height 120rpx
			white-space nowrap
			.item{
				display inline-block
				margin 0 20rpx
				padding-top 10rpx
				width 100rpx
				height 120rpx
				text-align center
				box-sizing border-box
				font-size 24rpx
				color #fff
				&.on{
					background url('~@/static/bill-date-bg.png') no-repeat 0 0
					background-size 100% 100%
				}
				view{
					font-size 36rpx
					font-weight bold
				}
			}
		}
	}
</style>
