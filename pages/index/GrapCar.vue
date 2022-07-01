<template>
	<view class="content1">
		<view class="go_where">
			<input type="text" placeholder="起点">
			<input type="text"  placeholder="终点">
		</view>
		<view class="go_method">
			预约 接送机 交代车
		</view>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				content:"内容"
			}
		}
		
	}
</script>

<style scoped>
	.content1{
		position: relative;
		height: 16vh;
		width: 100%;
		background-color: #FFFFFF ;
		overflow: hidden;
		border-radius: 2%;
	}
	.go_where{
		position: absolute;
		top: 20%;
		left: 50%;
		transform: translateX(-50%);
	}
		
	.go_method{
		position: absolute;
		bottom: 10%;
		left: 50%;
		transform: translateX(-50%);
	}
</style>