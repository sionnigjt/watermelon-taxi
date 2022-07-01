<template>
	<view class="index-content">
		<uni-section title="基本用法" type="line" >
			<uni-search-bar @confirm="search" :focus="true" @blur="blur" @focus="focus" @input="input"
				@cancel="cancel" @clear="clear">
			</uni-search-bar>
		</uni-section>
		<Mymap></Mymap>
		<GrapCar></GrapCar>
	
	</view>
</template>

<!-- 引入组件库 -->
<!-- <script src="https://unpkg.com/element-ui/lib/index.js"></script> -->

<script>
	import Mymap from "./Mymap.vue"
	import GrapCar from "./GrapCar.vue"
	import UniSection from "@/uni_modules/uni-search-bar/components/uni-search-bar/uni-search-bar.vue"
	// import uni-forms-item from "../../uni_modules/uni-forms/components/uni-forms-item/uni-forms-item.vue"
	// import uni-forms from "../../uni_modules/uni-forms/components/uni-forms/uni-forms.vue"
	export default {
		data() {
			return {
		
			}
		},

		methods: {

		},
		components:{
			Mymap,
			UniSection,
			GrapCar
		}
	}
	
</script>

<style>
	.example {
			padding: 15px;
			background-color: #fff;
		}
	
		.segmented-control {
			margin-bottom: 15px;
		}
	
		.button-group {
			margin-top: 15px;
			display: flex;
			justify-content: space-around;
		}
	
		.form-item {
			display: flex;
			align-items: center;
		}
	
		.button {
			display: flex;
			align-items: center;
			height: 35px;
			margin-left: 10px;
		}
	 .index-content {
		display: block;
	/* 	flex-direction: column;
		align-items: center;
		justify-content: center; */
	}

	
</style>
