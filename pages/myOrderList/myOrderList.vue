<template>
	<view>
		<nav-bar home :bgColor="['#FFB333','#ED8600']" bgColorAngle="90" fontColor="#FFF" title="我的订单">
			<image @click="backTo" class="icon_setUp" slot="left" src="../../static/back.png"></image>
			<!-- <image class="icon_setUp_r" slot="right" src="../../static/xiugai@3x.png"></image> -->
		</nav-bar>
		<view v-for="item in list" class="backView" @click="click(item)">
			<view class="top-view-back">
				<view style="display: flex;flex-direction: row;align-items: center;">
					<image style="width: 80rpx;height: 80rpx;" src="../../static/myOrder.png"></image>
					<view class="tip">订单号 -{{item.id}} </view>
					<view v-show="item.state_id === '3'" style="color: #ED8600;" class="tip1">( {{item.state}} )</view>
					<view v-show="item.state_id === '4'" style="color: #ED8600;" class="tip1">( {{item.state}} )</view>
					<view v-show="item.state_id === '5'" style="color: #3FB32D;" class="tip1">( {{item.state}} )</view>
					<view v-show="item.state_id === '0'" style="color: #E92B2B;" class="tip1">( {{item.state}} )</view>
				</view>
				<view style="display: flex;background: #FFFFFF;border: 1px solid #3F3F3F;border-radius: 21rpx;width: 133rpx;margin-top: 25rpx;
				margin-bottom: 20rpx;margin-right: 10rpx;text-align:center;align-items:center;justify-content: center;height: 35rpx;
">
				<view style="display: flex;font-size: 17rpx;font-family: MicrosoftYaHeiLight;font-weight: bold;color: #3F3F3F;margin-top: -5rpx;">取消</view>
				</view>
			</view>
			<view class="lin"></view>
			<view style="display: flex;flex-direction: row;align-items: center;justify-content: space-between;height: 100rpx;">
				<view class="tip2">订单金额 - {{item.price}}</view>
				<view class="tip2" style="margin-left: 100rpx;">{{item.time}}</view>
				<view style="display: flex;background: #FFFFFF;border: 1px solid #3F3F3F;border-radius: 21rpx;width: 133rpx;margin-top: 20rpx;
								margin-bottom: 20rpx;margin-right: 30rpx;text-align:center;align-items:center;justify-content: center;height: 35rpx;
				">
				<view style="display: flex;font-size: 17rpx;font-family: MicrosoftYaHeiLight;font-weight: bold;color: #3F3F3F;margin-top: -5rpx;">重新下单</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list:[{
						"id":"17061585",
						"state":"已支付",
						"state_id":"4",
						"price":"19.76$",
						"time":"刚刚"
					},{
						"id":"17061123",
						"state":"派送中",
						"state_id":"3",
						"price":"19.76$",
						"time":"5小时前"
					},{
						"id":"17061232",
						"state":"已完成",
						"state_id":"5",
						"price":"19.76$",
						"time":"5月1日，2020"
					},{
						"id":"17061898",
						"state":"已取消",
						"state_id":"0",
						"price":"19.76$",
						"time":"5月1日，2019"
					},{
						"id":"17061223",
						"state":"已完成",
						"state_id":"5",
						"price":"19.76$",
						"time":"5月1日，2018"
					}
				]
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
			click:function(item){
				uni.navigateTo({
				    url: '/pages/orderDetail/orderDetail?title='+item.id
				});
			}
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
		min-height: 100rpx;
		
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
		
		margin-left: 20rpx;
		font-size: 24rpx;
		font-family: MicrosoftYaHeiLight;
		font-weight: bold;
		color: #3F3F3F;
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
	margin-left: 20rpx;
font-size: 24rpx;
		font-family: MicrosoftYaHeiLight;
		font-weight: bold;
		color: #ED8600;
}
.tip2{
	display: flex;
	font-size: 24rpx;
	margin-left: 20rpx;
	font-family: MicrosoftYaHeiLight;
	font-weight: bold;
	color: #3F3F3F;
	opacity: 0.75;
}
.top-view-back{
	display: flex;
	flex-direction: row;
	margin-top: 10rpx;
	margin-bottom: 10rpx;
	margin-left: 20rpx;
	margin-right: 20rpx;
	justify-content: space-between;
}
</style>
