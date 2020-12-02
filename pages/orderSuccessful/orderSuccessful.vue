<template>
	<view>
		<nav-bar home :bgColor="['#FFB333','#ED8600']" bgColorAngle="90" fontColor="#FFF" title="订单成功">
			<image @click="backTo" class="icon_setUp" slot="left" src="../../static/back.png"></image>
			<!-- <image class="icon_setUp_r" slot="right" src="../../static/xiugai@3x.png"></image> -->
		</nav-bar>
		<view style="display: flex;align-items: center;width: 100%;height: 400rpx;justify-content: center;margin-top: 30rpx;flex-direction: column;">
			<image style="width: 157rpx;height: 157rpx;" src="../../static/orderSuccessful.png"></image>
			<view style="font-size: 60rpx;font-family: MicrosoftYaHeiLight;font-weight: bold;color: #000000;line-height: 72rpx;opacity: 0.9;margin-top:30rpx">感谢您</view>
			<view style="margin-top:10rpx;font-size: 36rpx">您的订单已经提交</view>
		</view>
		<view class="backView">
			<view style="display: flex;flex-direction: row;align-items: center;justify-content: space-between;margin-top: 20rpx;margin-left: 40rpx;margin-right: 40rpx;margin-bottom: 20rpx;">
				<view class="tip">订单号</view>
				<view class="tip">2017061585</view>
			</view>
			<view class="lin"></view>
			<view style="display: flex;flex-direction: row;align-items: center;justify-content: space-between;margin-top: 20rpx;margin-left: 40rpx;margin-right: 40rpx;margin-bottom: 20rpx;">
				<view class="tip">总计</view>
				<view class="tip">21.75$</view>
			</view>
			<view class="lin"></view>
			<view style="display: flex;margin-left: 40rpx;margin-right: 40rpx;flex;flex-direction: column;margin-top: 20rpx;margin-bottom: 20rpx;">
				<view class="tip">订单详情</view>
				<view class="tip1">兰州炒面, 2 凉拌马铃薯, 5 猪肉饺子 和
2 大杯可乐</view>
			</view>
			<view class="lin"></view>
			<view style="display: flex;flex-direction: row;align-items: center;justify-content: space-between;margin-top: 20rpx;margin-left: 40rpx;margin-right: 40rpx;margin-bottom: 20rpx;">
				<view class="tip">支付方式</view>
				<view class="tip">XXXX-4143</view>
			</view>
		</view>
		<view @click="goPay" style="display: flex; background: #FFFFFF;box-shadow: 0px -3px 9px 0px rgba(0, 0, 0, 0.1);position: fixed;height: 130rpx;width: 100%;left: 0;right: 0;bottom: 0rpx;" >
			<view style="display: flex;margin-top:20rpx;margin-bottom:20rpx;margin-left: 30rpx;margin-right: 30rpx;width: 690rpx; background: linear-gradient(-90deg, #FFB333, #ED8600);box-shadow: 0px 1px 10px 0px rgba(237, 134, 0, 0.5);border-radius: 54rpx;font-size: 39rpx;font-family: SimSun;font-weight: bold;color: #FFFFFF;align-items: center;justify-content: center;">
				确定
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
				    url: '/pages/home/home'
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
		
		background: #FFFFFF;
		box-shadow: 0px 1px 6px 0px rgba(0, 0, 0, 0.15);
		border-radius: 24rpx;
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
.tip{
		
		font-size: 33rpx;
		font-family: MicrosoftYaHeiLight;
		font-weight: bold;
		color: #000000;
		line-height: 54rpx;
	}
.lin{margin-top: 0rpx;
	margin-left: 0rpx;
	margin-right: 0rpx;
	height: 1rpx;
	background: #3F3F3F;
	opacity: 0.1;
	}
	
page{
					
	background-color: #F7F7F7;
}
.tip1{
font-size: 27rpx;
	font-family: MicrosoftYaHeiLight;
	font-weight: bold;
	color: #000000;
	line-height: 48rpx;
	opacity: 0.8;
}
</style>
