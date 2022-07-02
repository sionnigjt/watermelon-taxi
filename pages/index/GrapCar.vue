<template>
	<view class="content1">
		<view class="go_where">
			<view class="first">
			从<span @click="find_start_point">
			{{start_point}}</span>	出发
			</view>
			<view class="end">
				<span>{{end_point}}</span>
			</view>
		</view>
		<view class="go_method">
			<navigator open-type="navigate" class="go_method_nav">预约</navigator>
			<navigator open-type="navigate" class="go_method_nav">接送机</navigator>
			<navigator open-type="navigate" class="go_method_nav">交代车</navigator>
		</view>
	</view>
</template>

<script >
	export default{
		data(){
			let start_point="xxx"
			let end_point="目的地"
			//经过处理后
			return{
				content:"内容",
				end_point,
				start_point
			}
		},
		methods:{
			find_start_point(e){
				console.log(e)
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
		border:1px solid #f4f4f4;
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
		.first:hover,.end:hover{
			color: #adacac;
		}
		.end{
			margin-top: 2vh;
		}
		.first::after{
			content: ">";
			color: #7a7979;
			padding: 1vh;
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
		width: 60%;
		display: flex;
		position: absolute;
		bottom: 10%;
		left: 50%;
		transform: translateX(-50%);
		color: #7a7979;
		justify-content: center;
		.go_method_nav:nth-child(-n+2)::after{
			content: "|";
			padding:2vh ;
		}
		
	}
</style>