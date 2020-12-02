<template>
	<view>
		<nav-bar home :bgColor="['#FFB333','#ED8600']" bgColorAngle="90" fontColor="#FFF" :title="title">
			<image @click="backTo" class="icon_setUp" slot="left" src="../../static/back.png"></image>
			<!-- <image class="icon_setUp_r" slot="right" src="../../static/xiugai@3x.png"></image> -->
		</nav-bar>
	<view class="backView">
			<view style="display: flex;flex-direction: row;">
				
				<view>
					<image style="width: 150rpx;height: 150rpx;margin-top: 20rpx;margin-left: 20rpx;" src="../../static/orderCar2@3x.png"></image>
				</view>
				<view style="display: flex;flex-direction: column; margin-top: 40rpx;margin-left: 30rpx;width: 330rpx;">
					<view style="font-size: 36rpx;font-family: MicrosoftYaHeiLight;font-weight: bold;color: #3F3F3F;">John Doe</view>
					<view style="font-size: 24rpx;font-family: MicrosoftYaHeiLight;font-weight: bold;color: #3F3F3F;line-height: 36rpx;">johndoe@gmail.com</view>
					<view style="font-size: 24rpx;font-family: MicrosoftYaHeiLight;font-weight: bold;color: #3F3F3F;line-height: 36rpx;">01 987 6543 210</view>
				</view>
				<view style="margin-left: 10rpx;display: flex;align-items: center;flex-direction: column;">
					<view style="display: flex;background: #FFFFFF;border: 1px solid #3F3F3F;border-radius: 21rpx;width: 133rpx;margin-top: 40rpx;
									margin-bottom: 20rpx;margin-right: 30rpx;text-align:center;align-items:center;justify-content: center;height: 35rpx;
					">
					<view style="display: flex;font-size: 17rpx;font-family: MicrosoftYaHeiLight;font-weight: bold;color: #3F3F3F;margin-top: -5rpx;">派送进度</view>
					</view>
					
					<view style="display: flex;background: #FFFFFF;border: 1px solid #3F3F3F;border-radius: 21rpx;width: 133rpx;margin-top: 0rpx;
									margin-bottom: 20rpx;margin-right: 30rpx;text-align:center;align-items:center;justify-content: center;height: 35rpx;
					">
					<view style="display: flex;font-size: 17rpx;font-family: MicrosoftYaHeiLight;font-weight: bold;color: #3F3F3F;margin-top: -5rpx;">重新下单</view>
					</view>
				</view>
			</view>
		<view class="lin"></view>
		<view class="text-class">订单号 - 2017061585 </view>
		<view class="text-class">时间: 11:35, 5月1日，2017</view>
		<view class="text-class">派送地址：</view>
		<view class="text-class">41，应用创新，一楼 74区、工业区相8b 160062印度莫哈里</view>
		<view class="lin"></view>
		<view style="display: flex;flex-direction: row;align-items: center;">
			<!-- <image style="width: 50rpx;height: 50rpx;margin-top: 30rpx;margin-left: 40rpx;margin-bottom: 20rpx;" src="../../static/longbaoImage@2x.png"></image> -->
			<view style="width: 400rpx;font-size: 24rpx;font-family: MicrosoftYaHeiLight;font-weight: bold;color: #3F3F3F;margin-left: 40rpx;">商品</view>
			<view class="text-class" style="margin-left: 20rpx;">数量</view>
			<view class="text-class1" style="margin-left: 40rpx;">价格</view>
		</view>
		<view v-for="item in 4">
			<view style="display: flex;flex-direction: row;align-items: center;">
				<!-- <image style="width: 50rpx;height: 50rpx;margin-top: 30rpx;margin-left: 40rpx;margin-bottom: 20rpx;" src="../../static/longbaoImage@2x.png"></image> -->
				<view style="width: 400rpx;font-size: 24rpx;font-family: MicrosoftYaHeiLight;font-weight: bold;color: #3F3F3F;margin-left: 40rpx;">兰州拉面</view>
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
		
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title:''
			}
		},
		methods: {
			backTo:function(){
				uni.navigateBack({
				    // delta: 2
				});
			},
		},
		onLoad:function(options) {
		             //options可以接到index 传过来的值
		             console.log(options)
					 this.title = '订单号-'+options.title
		         },
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
	margin-left: 40rpx;
	margin-right: 40rpx;
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
