<template name="nine-view">
	<view class="nine-card-warp">
		<view class="nine-card-warp-content">
			<navigator :url="item.path" hover-class="none"  v-if="item.flag==true" v-for="(item,index) in data" :key="index" :style="{height:styleData.height+'rpx'}">
				<image :src="item.imageUrl" mode="aspectFit" :style="{height:styleData.imgStyle.height+'rpx',width:styleData.imgStyle.width+'rpx'}"></image>
				<text>{{item.name}}</text>
			</navigator>
		</view>
	</view>
</template>

<script>
export default {
	//属性
	props: {
		data:[],
		styleData:{}
	},
	//组件生命周期
	created:function(e){
		
	},
	methods: {
		// 函数名称:function(obj){
		// 
		// },
	}
}
</script>

<style scoped>
	.nine-card-warp {
		margin:20rpx 0;
		padding:0;
		overflow:hidden;
	}
	.nine-card-warp-content {
		background:#fff;
		border-radius:8rpx;
		width:100%;
		display:table;
	}
	.nine-card-warp-content navigator {
		float:left;
		width:calc(33.333% - 1rpx);
		border:1rpx solid #e6e6e6;
		border-left:none;
		border-top:none;
		background:#ff!important;
		font-size:30rpx;
		color:#323232;
		text-align:center;
	}
	.nine-card-warp-content navigator image {
		padding-top:30rpx;
		display:block;
		margin:0 auto;
	}
</style>
