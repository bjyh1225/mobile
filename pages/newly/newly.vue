<template>
	<view class="newly-container">
		<newly-head/>
		<image :src="'../../static/newly-text-'+(type==0?'wide.png':'tv.png')" class="newly-title"/>
		<view class="newly-form">
			<view class="newly-section">
				<view class="newly-sec-tit d-flex d-flex-middle"><text>1</text>选择安装地址</view>
				<view class="newly-item d-flex d-flex-middle">
					<text class="newly-item-label d-flex-unShrink">归属地址</text>
					<view class="newly-item-text color d-flex-item d-flex d-flex-middle">湖北武汉</view>
				</view>
				<view class="newly-item d-flex d-flex-middle">
					<text class="newly-item-label d-flex-unShrink">选择区县</text>
					<view class="newly-item-text d-flex-item d-flex d-flex-middle">
						<picker :value="selectedAreaIndex" :range="area" @change="selectArea" style="width: 100%;">
							<view class="d-ellipsis-single">{{area[selectedAreaIndex]}}</view>
						</picker>
					</view>
					<image src="../../static/icon-arrow-down.png" class="newly-item-arrow d-flex-unShrink"/>
				</view>
				<view class="newly-item d-flex d-flex-middle">
					<text class="newly-item-label d-flex-unShrink">乡镇/街道</text>
					<input type="text" placeholder="请输入乡镇/街道名称" class="newly-item-text d-flex-item d-flex d-flex-middle"/>
				</view>
				<view class="newly-item d-flex d-flex-middle">
					<text class="newly-item-label d-flex-unShrink">小区/社区</text>
					<input type="text" placeholder="请输入小区/社区名称" class="newly-item-text d-flex-item d-flex d-flex-middle"/>
				</view>
				<view class="newly-item d-flex d-flex-middle">
					<text class="newly-item-label d-flex-unShrink">详细地址</text>
					<input type="text" placeholder="请输入详细地址，精确到门牌号" class="newly-item-text d-flex-item d-flex d-flex-middle"/>
				</view>
			</view>
			<view v-if="type==0" class="newly-section">
				<view class="newly-sec-tit d-flex d-flex-middle"><text>2</text>选择方案</view>
				<view class="newly-plan d-flex d-flex-wrap d-flex-between">
					<view class="on d-flex d-flex-middle d-flex-center">100M移动宽带</view>
					<view class="d-flex d-flex-middle d-flex-center">100M移动宽带</view>
					<view class="d-flex d-flex-middle d-flex-center">100M移动宽带</view>
					<view class="d-flex d-flex-middle d-flex-center">100M移动宽带</view>
				</view>
			</view>
			<view class="newly-section">
				<view class="newly-sec-tit d-flex d-flex-middle"><text>{{type==0?3:2}}</text>选择安装地址</view>
				<view class="newly-item d-flex d-flex-middle">
					<text class="newly-item-label d-flex-unShrink">受理号码</text>
					<view class="newly-item-text color d-flex-item d-flex d-flex-middle">湖北武汉</view>
				</view>
				<view class="newly-item d-flex d-flex-middle">
					<text class="newly-item-label d-flex-unShrink">预约姓名</text>
					<input type="text" placeholder="请输入您的姓名" class="newly-item-text d-flex-item d-flex d-flex-middle"/>
				</view>
				<view class="newly-item d-flex d-flex-middle">
					<text class="newly-item-label d-flex-unShrink">身份证号</text>
					<input type="text" placeholder="请输入身份证号" class="newly-item-text d-flex-item d-flex d-flex-middle"/>
				</view>
				<view class="newly-item d-flex d-flex-middle">
					<text class="newly-item-label d-flex-unShrink">备注</text>
					<input type="text" placeholder="请输入备注" class="newly-item-text d-flex-item d-flex d-flex-middle"/>
				</view>
				<view class="newly-item d-flex d-flex-middle">
					<text class="newly-item-label d-flex-unShrink">支付方式</text>
					<view class="newly-item-method d-flex d-flex-middle">
						<view v-for="(item,index) in payMethod" :key="index" @click="selectMethod(index)" class="d-flex d-flex-middle">
							<image :src="'../../static/icon-checkbox'+(item.isChecked?'-checked.png':'.png')"/>
							{{item.text}}
						</view>
					</view>
				</view>
			</view>
			<view class="newly-btn d-flex d-flex-middle d-flex-center">提交订单</view>
		</view>
	</view>
</template>

<script>
	import NewlyHead from '../../components/lyl/newly-head.vue'
	export default {
		components:{
			NewlyHead
		},
		data() {
			return {
				type:0, // 0.宽带新装 1.TV新装
				area:['请选择区县','江岸区','江汉区','硚口区','汉阳区','洪山区','青山区'],
				selectedAreaIndex:0,
				payMethod:[
					{text:'上门支付',isChecked:true},
					{text:'线上支付',isChecked:false}
				]
			}
		},
		methods: {
			selectArea(e){
				this.selectedAreaIndex=e.detail.value
			},
			selectMethod(index){
				this.payMethod.forEach((v,i) => {
					v.isChecked=i==index
				})
			}
		},
		onLoad(option){
			this.type=option.type // 0.宽带新装 1.TV新装
		}
	}
</script>

<style scoped>
	page{
		background:#1d0076 url('~@/static/newly-bg.png') no-repeat 0 0;
		background-size: 750rpx 1375rpx;
	}
	.newly-container{
		padding: 240rpx 30rpx 80rpx;
	}
	.newly-title{
		display: block;
		margin:40rpx auto 0;
		width: 239rpx;
		height: 50rpx;
	}
	.newly-form{
		margin-top: 30rpx;
		padding: 4rpx 55rpx 40rpx;
		background-color: #fff;
		border-radius: 20rpx;
	}
	.newly-section{
		margin-top: 40rpx;
	}
	.newly-sec-tit{
		font-size: 30rpx;
		font-weight: bold;
		color: #1d0076;
	}
	.newly-sec-tit text{
		margin-right: 10rpx;
		width: 34rpx;
		height: 34rpx;
		text-align: center;
		line-height: 34rpx;
		background: linear-gradient(180deg,rgba(166,94,241,1) 0%,rgba(190,125,246,1) 100%);
		border-radius: 50%;
		font-size: 28rpx;
		font-weight: normal;
		color: #fff;
	}
	.newly-item{
		margin-top: 20rpx;
		padding: 0 20rpx;
		height: 80rpx;
		background-color: #f2f2f2;
		border-radius: 10rpx;
	}
	.newly-item-label{
		width: 160rpx;
		font-size: 30rpx;
		color: #333333
	}
	.newly-item-text{
		width: 50%;
		height: 100%;
		font-size: 26rpx;
		color: #555;
	}
	.newly-item-text.color{
		color: #1D0076;
	}
	.newly-item-arrow{
		margin-left: 20rpx;
		width: 25rpx;
		height: 14rpx;
	}
	.newly-plan view{
		margin-top: 20rpx;
		width: 280rpx;
		height: 80rpx;
		border: 1px solid #a961f2;
		border-radius: 10rpx;
		box-sizing: border-box;
		font-size: 30rpx;
		font-weight: bold;
		color: #1d0076;
	}
	.newly-item-method view{
		margin-right: 40rpx;
		font-size: 26rpx;
		color: #666;
	}
	.newly-item-method view:last-child{
		margin-right: 0;
	}
	.newly-item-method image{
		margin-right: 10rpx;
		width: 30rpx;
		height: 30rpx;
	}
	.newly-btn{
		margin-top: 40rpx;
		height: 80rpx;
		background: linear-gradient(180deg,rgba(166,94,241,1) 0%,rgba(190,125,246,1) 100%);
		border-radius: 40rpx;
		font-size: 30rpx;
		color: #fff;
	}
</style>
