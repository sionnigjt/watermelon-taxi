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
			
	.map-content{
		height: 55vh;
			overflow: hidden;
		}
	.content{
		height: 100%;
		overflow: hidden;
	}
	page{
			height: 100%;
		}
	/* 滑动条 */
	/* *{
		overflow: hidden;
	} */
	/* scroll-view ::-webkit-scrollbar {  
	
	    display: none !important;  
	
	    width: 0 !important;  
	
	    height: 0 !important;  
	
	    -webkit-appearance: none;  
	
	    background: transparent;  
	
	}
	::-webkit-scrollbar{
	
	  display: none;} */
</style>
