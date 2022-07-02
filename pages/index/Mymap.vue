<template>
    <view class="map-content">
     <map style="width: 100%;max-height: 55vh;height: 55vh;" :layer-style='5'  :style="{height:mapheight}" :show-location='true' :show-compass='true'
	   :latitude="latitude" :longitude="longitude" :markers="markers" 
	   :scale="scale"  @markertap="markertap"   @callouttap='callouttap'>
       </map>
    </view>
</template>

<script>

    export default {
		
        data() {
            return {
                        latitude:30.65984, //纬度
                        longitude:104.10194,//经度
                        scale:14,//缩放级别
                        bottomData:false,
						markers: [{
							id: 1, // Number
							title: '1', // String-标注点名
							rotate: 180, // Number - 顺时针旋转的角度，范围 0 ~ 360，默认为 0
							alpha: 0.5, // 默认1，无透明，范围 0 ~ 1
							latitude: 39.899,
							longitude: 116.39742,
							width: 30,
							height: 30,
							// callout: {
							// 	display: "BYCLICK",
							// 	padding: 10,
							// 	borderRadius: 5,
							// 	content: '',
							// },
							// anchor: {},
							iconPath: '../../static/map/compass/指南针.png', // 显示的图标
						}]
            }
            },
        onLoad() {

        },
        computed:{
                    mapheight(){
                        let data =''
                        if(this.bottomData){
                            if(this.upTop){
                                data ='50px'
                            }else{
                                data ='200px'
                            }
                        }else{
                            data ='90vh'
                        }
                        return data
                    },
                    coverbottom(){
                        let data =''
                        if(this.bottomData){
                            data ='20rpx'
                        }else{
                            data ='100rpx'
                        }
                        return data
                    }
                },
        methods:{
                //地图点击事件
            markertap(e) {
                console.log("===你点击了标记点===",e)
                },
            //地图点击事件
            callouttap(e){
                console.log('此处经纬度')
				
        },
		chooseLocation(e) { //打开地图选择位置
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
		}
        }
    }
</script>
<style> 

</style>