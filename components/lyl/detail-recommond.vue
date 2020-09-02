<template>
	<view class="detail-recommond-container">
		<view class="title d-flex d-flex-middle">同类推荐</view>
		<scroll-view scroll-x class="list">
			<view v-for="(item,index) in 10" :key="index" class="item">
				<view class="item-con d-flex d-flex-column d-flex-middle">
					<view class="img d-flex d-flex-center d-flex-middle">
						<image src="../../static/img01.png"/>
					</view>
					<view class="tit color-text-main">小荷MINI10</view>
					<text class="price color-text-red">¥299.00</text>
				</view>
			</view>
		</scroll-view>
	</view>
</template>

<script>
</script>

<style lang="stylus" scoped>
	.detail-recommond-container{
		.title{
			padding 0 30rpx
			height 80rpx
			font-size 34rpx
			font-weight bold
			color #333
		}
		.list{
			padding-bottom 30rpx
			white-space nowrap
			.item{
				display inline-block
				margin 0 20rpx
				width 200rpx
				.item-con{
					.img{
						width 100%
						height 186rpx
						background-color #f2f2f2
						image{
							width 100rpx
							height 103rpx
						}
					}
					.tit{
						margin 5rpx 0 10rpx
						font-size 26rpx
					}
					.price{
						font-size 26rpx
					}
				}
			}
		}
	}
</style>
