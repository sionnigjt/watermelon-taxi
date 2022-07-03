<template>
    <view class="map-content">
     <map style="width: 100%;max-height: 55vh;height: 55vh;" :layer-style='5'  :style="{height:mapheight}" :show-location='true' :show-compass='true'
	   :latitude="latitude" :longitude="longitude" :markers="markers" :polyline="polyline" :controls="controls"
	   :scale="scale"  @markertap="markertap"   @callouttap='callouttap' @tap="click_tap" >
       </map>
    </view>
</template>

<script>

    export default {
		
        data() {
            return {
                        latitude:30.65984, //纬度
                        longitude:104.10194,//经度
                        scale:13,//缩放级别
                        bottomData:false,
						//线段等
						polyline:[
						        {//指定一系列坐标点，从数组第一项连线至最后一项
								points:[
									{latitude: 30.65984,longitude: 104.102},
						            {latitude: 30.65983,longitude:104.107}],
						            color:"#0000AA",//线的颜色
						            width:1,//线的宽度
						                    // 　　　　dottedLine:true,//是否虚线
									arrowLine:true,    //带箭头的线 开发者工具暂不支持该属性
						                    　　}
						                ],
						markers: [{
                  　　 	latitude:  30.65984,//纬度
                  　	longitude: 104.103,//经度
                  　　	iconPath: '../../static/map/compass.png',    //显示的图标        
                  　　	rotate:0,   // 旋转度数
                  　　	width:40,   //宽
                  　　	height:40,   //高
                 　　 	title:'我在这里',//标注点名
                 　　	alpha:0.5,   //透明度
                 　　 	label:{//为标记点旁边增加标签   //因背景颜色H5不支持
                 　　   content:'Hello,I am here',//文本
               　　　　 color:'red',//文本颜色
						}}],
						controls:[{
						    // 在地图上显示控件，控件不随着地图移动
						    id: 1, // 控件id
							iconPath:'../../static/map/compass.png', // 显示的图标
							position:{
							 // 控件在地图的位置
							 left: 15,
							 top: 15,
							 width: 25,
							 height: 25
						   },    
						}],
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
                    },
				
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
			//地图点击事件
			click_tap(){
					console.log("click")
					
				},
        }
    }
</script>
<style> 

</style>