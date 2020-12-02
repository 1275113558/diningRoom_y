<template>
	<view>
		<nav-bar home :bgColor="['#FFB333','#ED8600']" bgColorAngle="90" fontColor="#FFF" title="订单确认">
			<image @click="backTo" class="icon_setUp" slot="left" src="../../static/back.png"></image>
			<image class="icon_setUp_r" slot="right" src="../../static/xiugai@3x.png"></image>
		</nav-bar>
		<view class="backView">
			<view style="display: flex;flex-direction: row;">
				
				<view>
					<image style="width: 150rpx;height: 150rpx;margin-top: 20rpx;margin-left: 20rpx;" src="../../static/orderCar2@3x.png"></image>
				</view>
				<view style="display: flex;flex-direction: column; margin-top: 40rpx;margin-left: 30rpx;">
					<view style="font-size: 36rpx;font-family: MicrosoftYaHeiLight;font-weight: bold;color: #3F3F3F;">John Doe</view>
					<view style="font-size: 24rpx;font-family: MicrosoftYaHeiLight;font-weight: bold;color: #3F3F3F;line-height: 36rpx;">johndoe@gmail.com</view>
					<view style="font-size: 24rpx;font-family: MicrosoftYaHeiLight;font-weight: bold;color: #3F3F3F;line-height: 36rpx;">01 987 6543 210</view>
				</view>
			</view>
		<view class="lin"></view>
		<view class="text-class">派送地址：</view>
		<view class="text-class">41，应用创新，一楼 74区、工业区相8b 160062印度莫哈里</view>
		<view class="lin"></view>
		<view v-for="item in 4">
			<view style="display: flex;flex-direction: row;align-items: center;">
				<image style="width: 50rpx;height: 50rpx;margin-top: 30rpx;margin-left: 40rpx;margin-bottom: 20rpx;" src="../../static/longbaoImage@2x.png"></image>
				<view style="width: 400rpx;font-size: 24rpx;font-family: MicrosoftYaHeiLight;font-weight: bold;color: #3F3F3F;margin-left: 20rpx;">兰州拉面</view>
				<view class="text-class">5</view>
				<view class="text-class1">11.25$</view>
			</view>
			<view class="lin"></view>
		</view>
		
		<view style="display: flex;flex-direction: row;align-items: center;justify-content: space-between;margin-top: 20rpx;margin-left: 40rpx;margin-right: 40rpx;">
			<view class="tip">总计</view>
			<view class="tip">20.25$</view>
		</view>
		
		<view style="display: flex;flex-direction: row;align-items: center;justify-content: space-between;margin-top: 0rpx;margin-left: 40rpx;margin-right: 40rpx;">
			<view class="tip">折扣</view>
			<view class="tip">-3.00$</view>
		</view>
		
		<view style="display: flex;flex-direction: row;align-items: center;justify-content: space-between;margin-top: 0rpx;margin-left: 40rpx;margin-right: 40rpx;">
			<view class="tip">送餐费用（14.4%）</view>
			<view class="tip">3.00$</view>
		</view>
		
		<view style="display: flex;flex-direction: row;align-items: center;justify-content: space-between;margin-top: 0rpx;margin-left: 40rpx;margin-right: 40rpx;">
			<view class="tip">服务费</view>
			<view class="tip">0.75$</view>
		</view>
		
		<view style="display: flex;flex-direction: row;align-items: center;justify-content: space-between;margin-top: 0rpx;margin-left: 40rpx;margin-right: 40rpx;">
			<view class="tip">其他费用</view>
			<view class="tip">0.75$</view>
		</view>
		
		<view class="lin"></view>
		
		<view style="display: flex;flex-direction: row;align-items: center;justify-content: space-between;margin-top: 20rpx;margin-left: 40rpx;margin-right: 40rpx;margin-bottom: 20rpx;">
			<view class="tip">总计</view>
			<view class="tip">21.75$</view>
		</view>
		
		</view>
		
		<view style="height: 200rpx;width: 100%;"></view>
		
		<view @click="goPay" style="display: flex; background: #FFFFFF;box-shadow: 0px -3px 9px 0px rgba(0, 0, 0, 0.1);position: fixed;height: 130rpx;width: 100%;left: 0;right: 0;bottom: 0rpx;" >
			<view style="display: flex;margin-top:20rpx;margin-bottom:20rpx;margin-left: 30rpx;margin-right: 30rpx;width: 690rpx; background: linear-gradient(-90deg, #FFB333, #ED8600);box-shadow: 0px 1px 10px 0px rgba(237, 134, 0, 0.5);border-radius: 54rpx;font-size: 39rpx;font-family: SimSun;font-weight: bold;color: #FFFFFF;align-items: center;justify-content: center;">
				确认支付21.75$
			</view>
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
			goPay:function(){
				uni.navigateTo({
				    url: '/pages/SureOrder/SureOrder'
				});
			},
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
.lin{
	margin-top: 10rpx;
	margin-left: 10rpx;
	margin-right: 10rpx;
	height: 1rpx;
	background: #3F3F3F;
	opacity: 0.1;
}
.text-class{
	margin-top: 10rpx;
	margin-left: 20rpx;
	margin-right: 20rpx;
	font-size: 24rpx;
	font-family: MicrosoftYaHeiLight;
	font-weight: bold;
	color: #3F3F3F;
	line-height: 36rpx;
}
.text-class1{
	margin-top: 10rpx;
	margin-left: 50rpx;
	margin-right: 20rpx;
	font-size: 24rpx;
	font-family: MicrosoftYaHeiLight;
	font-weight: bold;
	color: #3F3F3F;
	line-height: 36rpx;
}
.tip{
	font-size: 24rpx;
	font-family: MicrosoftYaHeiLight;
	font-weight: bold;
	color: #3F3F3F;
	line-height: 48rpx;
}
</style>
