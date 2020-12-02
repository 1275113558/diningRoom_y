<template>
	<view>
		<nav-bar home :bgColor="['#FFB333','#ED8600']" bgColorAngle="90" fontColor="#FFF" :title="title">
			<image @click="backTo" class="icon_setUp" slot="left" src="../../static/back.png"></image>
			<!-- <image class="icon_setUp_r" slot="right" src="../../static/xiugai@3x.png"></image> -->
		</nav-bar>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title:'中国菜'
			}
		},
		methods: {
			backTo:function(){
				uni.navigateBack({
				    // delta: 2
				});
			},
		}
	}
</script>

<style>
.backView{
		display: flex;
		flex-direction: column;
		/* align-items: center; */
		 margin-top: 30rpx;
		margin-left: 30rpx;
		margin-right: 30rpx;
		width: 690rpx;
		background-color: #FFFFFF;
/* 		background-image: url(../../static/bg.png); */
		min-height: 300rpx;
		/* background-repeat : no-repeat; */
		/* background-size:100% 100%; */
	}
.icon_setUp{
	display: flex;
	margin-left: 20rpx;
	width: 51rpx;
	height: 40rpx;
}
.icon_setUp_r{
	display: flex;
	margin-right: 20rpx;
	margin-top: 10rpx;
	width: 30rpx;
	height: 30rpx;
}
.uni-grid-back{
	display: flex;
	margin-top: 40rpx;
	width: 690rpx;
	height: 100rpx;
}

.uni-grid-super{
	display: flex;
	margin-left: -30rpx;
	margin-right: 5rpx;
	/* width: 190rpx; */
	}
page{
					
	background-color: #F7F7F7;
}
</style>
