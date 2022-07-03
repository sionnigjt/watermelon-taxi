<template>
	<view class="content1">
		<view class="go_where">
			<view class="first">
			从<span @click="find_start_point" @mouseenter="enters" @mouseleave="leaver">
		 	 {{start_point}}</span>	出发
			</view>
			<view class="end" @click="find_end_point" @mouseenter="enters" @mouseleave="leaver">
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
		props:["searchValue"],
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
				uni.chooseLocation({
					success: res => {
						console.log('位置名称：' + res.name);
						console.log('详细地址：' + res.address);
						console.log('纬度：' + res.latitude);
						console.log('经度：' + res.longitude);
						uni.getLocation({
							type: 'gcj02',
							altitude:true,
							geocode:true,
							success: function(res) {
								console.log('当前位置的经度：' + res.longitude);
								console.log('当前位置的纬度：' + res.latitude);
							}
						});
						console.log('省：' + res.address.slice(0, res.address.indexOf('省') + 1));
						console.log('市：' + res.address.slice(res.address.indexOf('省') + 1, res.address.indexOf('市') + 1));
						console.log('区：' + res.address.slice(res.address.indexOf('市') + 1, res.address.indexOf('区') + 1));
						this.query.address = res.address;
						this.query.latitude = res.latitude;
						this.query.longitude = res.longitude;
						this.query.province = res.address.slice(0, res.address.indexOf('省') + 1)
						this.query.city = res.address.slice(res.address.indexOf('省') + 1, res.address.indexOf('市') + 1)
						this.query.district = res.address.slice(res.address.indexOf('市') + 1, res.address.indexOf('区') + 1)
					}
				});
			},
			find_end_point(){
				uni.chooseLocation({
					success: res => {
						console.log('位置名称：' + res.name);
						console.log('详细地址：' + res.address);
						console.log('纬度：' + res.latitude);
						console.log('经度：' + res.longitude);
						uni.getLocation({
							type: 'gcj02',
							altitude:true,
							geocode:true,
							success: function(res) {
								console.log('当前位置的经度：' + res.longitude);
								console.log('当前位置的纬度：' + res.latitude);
							}
						});
						console.log('省：' + res.address.slice(0, res.address.indexOf('省') + 1));
						console.log('市：' + res.address.slice(res.address.indexOf('省') + 1, res.address.indexOf('市') + 1));
						console.log('区：' + res.address.slice(res.address.indexOf('市') + 1, res.address.indexOf('区') + 1));
						this.query.address = res.address;
						this.query.latitude = res.latitude;
						this.query.longitude = res.longitude;
						this.query.province = res.address.slice(0, res.address.indexOf('省') + 1)
						this.query.city = res.address.slice(res.address.indexOf('省') + 1, res.address.indexOf('市') + 1)
						this.query.district = res.address.slice(res.address.indexOf('市') + 1, res.address.indexOf('区') + 1)
					}
				});
			},
			enters(){
				
				
			},leaver(){
				
			}
		},
		
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