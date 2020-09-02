<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	/*每个页面公共css */
	@import 'common/common.css';
	.color-text-main{
		color: #404040!important;
	}
	.color-text-red{
		color: #f54029!important;
	}
	.color-text-blue{
		color: #2a93fd!important;
	}
	.color-bg-grey{
		background-color: #f7f7f8;
	}
</style>
