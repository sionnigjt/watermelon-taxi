<template>
	<view class="content1">
		<view class="go_where">
			<view class="first">
				从xxx出发
			</view>
			<view class="end">
				目的地
			</view>
		</view>
		<view class="go_method">
			预约 | 接送机  | 交代车
		</view>
	</view>
</template>

<script >
	export default{
		data(){
			return{
				content:"内容"
			}
		}
		
	}
</script>

<style scoped lang="less">
	.content1{
		position: relative;
		height: 23vh;
		width: 100%;
		background-color: #ffffff ;
		overflow: hidden;
		border-radius: 2%;
	}
	.go_where{
		position: absolute;
		top: 15%;
		left: 50%;
		width: 80%;
		height: 11vh;
		transform: translateX(-50%);
		border:1px solid #f7f7f7;
		border-radius:5% ;
		padding: 1vh;
		box-shadow:    0px -10px 0px 0px rgba(0,0,0,0),   /*上边阴影  透明*/
		
		                -10px 0px 0px 0px rgba(0,0,0,0),   /*左边阴影  透明*/
		                
		                10px 0px 0px 0px rgba(0,0,0,0),    /*右边阴影  透明*/
		                
		                0px 10px 30px 0px rgba(0,0,0,0.1);    /*下边阴影 */
		.first,.end{
			margin-left: 4vh;
			margin-top: 1vh;
			
		}
		.first::before,.end::before{
			display: inline-block;
			content: "";
			border-radius: 50%;
			background-color: #9fff73;
			margin-right: 1vh;
			padding: 0.7vh;
			
		}
		.end::before{
			background-color: #da0000;
		}
	}
		
	.go_method{
		position: absolute;
		bottom: 10%;
		left: 50%;
		transform: translateX(-50%);
	}
</style>