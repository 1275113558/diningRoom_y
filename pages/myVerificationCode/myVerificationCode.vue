<template>
	<view>
		<nav-bar home :bgColor="['#FFB333','#ED8600']" bgColorAngle="90" fontColor="#FFF" title="我的核销码">
			<image @click="backTo" class="icon_setUp" slot="left" src="../../static/back.png"></image>
			<!-- <image class="icon_setUp_r" slot="right" src="../../static/xiugai@3x.png"></image> -->
		</nav-bar>
		<view class="backView">
			<image style="height:571rpx;width: 571rpx;margin-top: 10rpx;" src="../../static/erweima.png"></image>
			<view style="display: flex;background: #FFFFFF;border: 1px solid #3F3F3F;border-radius: 21rpx;width: 208rpx;margin-top: 40rpx;
							text-align:center;align-items:center;justify-content: center;height: 35rpx;margin-bottom: 20rpx;
			">
			<view style="display: flex;font-size: 17rpx;font-family: MicrosoftYaHeiLight;font-weight: bold;color: #3F3F3F;margin-top: -5rpx;">重新生成新的二维码
</view>
			</view>
			<view class="tip">请妥善保存自己的食堂核销码</view>
			<view class="tip">进入食堂出示此码核销后吃饭</view>
			<view class="tip1">（三分钟自动更新）</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
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
		align-items: center;
		 margin-top: 30rpx;
		margin-left: 30rpx;
		margin-right: 30rpx;
		width: 690rpx;
		background-color: #FFFFFF;
/* 		background-image: url(../../static/bg.png); */
		min-height: 300rpx;
		/* background-repeat : no-repeat; */
		/* background-size:100% 100%; */
		background: #FFFFFF;
		box-shadow: 0px 1px 4px 0px rgba(0, 0, 0, 0.15);
		border-radius: 24rpx;
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
.tip{
	display: flex;
	font-size: 17rpx;
	font-family: SimSun;
	font-weight: bold;
	color: #3F3F3F;
	/* margin-bottom: 40rpx; */
}
.tip1{
	display: flex;
	font-size: 17rpx;
	font-family: SimSun;
	font-weight: bold;
	color: #3F3F3F;
	margin-bottom: 40rpx;
}
</style>
