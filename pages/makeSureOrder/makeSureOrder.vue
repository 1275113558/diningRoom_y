<template>
	<view>
		<nav-bar home :bgColor="['#FFB333','#ED8600']" bgColorAngle="90" fontColor="#FFF" title="订单确认">
			<image @click="backTo" class="icon_setUp" slot="left" src="../../static/back.png"></image>
			<image class="icon_setUp_r" slot="right" src="../../static/gouwuche@3x.png"></image>
		</nav-bar>
		<view class="backView">
			<view v-for="item in list" style="flex-direction: column;display: flex;">
				<view class="cell-back">
					<image style=" margin-top:20rpx; margin-left: 20rpx;width: 80rpx;height: 80rpx;" src="../../static/longbaoImage@2x.png"></image>
					<view style="display: flex;flex-direction: column;margin-left: 20rpx;">
						<view style="font-size: 24rpx;font-family: MicrosoftYaHeiLight;font-weight: bold;color: #3F3F3F;width: 300rpx;">猪肉饺子</view>
						<view style="margin-top: 10rpx;font-size: 18rpx;font-family: MicrosoftYaHeiLight;font-weight: bold;text-decoration: underline;color: #ED8600;">删除此商品</view>
					</view>
					<view style="display: flex;align-items: center;">
						<view class="item-jisuan">—</view>
						<view class="item-jisuan1">1</view>
						<view class="item-jisuan">+</view>
					</view>
					<view class="right-back-img">
						<view class="right-back-title">11.25$</view>
					</view>
				</view>
				
				<view class="lin"></view>
			</view>
			
			
			
			
			
		</view>
		
		<view class="bottom">
			<view class="b-l">
				<view class="b-l-t">添加更多商品</view>
				</view>
			<view class="price">总计: 20.25$</view>
		</view>
		<view style="height: 200rpx;"></view>
		<view @click="goMake" style="display: flex; background: #FFFFFF;box-shadow: 0px -3px 9px 0px rgba(0, 0, 0, 0.1);position: fixed;height: 130rpx;width: 100%;left: 0;right: 0;bottom: 0rpx;" >
			<view style="display: flex;margin-top:20rpx;margin-bottom:20rpx;margin-left: 30rpx;margin-right: 30rpx;width: 690rpx; background: linear-gradient(-90deg, #FFB333, #ED8600);box-shadow: 0px 1px 10px 0px rgba(237, 134, 0, 0.5);border-radius: 54rpx;font-size: 39rpx;font-family: SimSun;font-weight: bold;color: #FFFFFF;align-items: center;justify-content: center;">
				支付订单
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list:['1','2','3','4','4','4','4','4','4','4']
			}
		},
		methods: {
			goMake:function(){
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
/* ----NAV */
.backView{
		display: flex;
		flex-direction: column;
		/* align-items: center; */
		margin-top: 30rpx;
		margin-left: 30rpx;
		margin-right: 30rpx;
		width: 690rpx;
		background-image: url(../../static/bg01.png);
		min-height: 300rpx;
		background-repeat : no-repeat;
		background-size:100% 100%; 
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
	width: 40rpx;
	height: 40rpx;
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
	.cell-back{
		display: flex;
		flex-direction: row;
		align-items: center;
	}
	.item-jisuan{
		display: flex;
		align-items: center;
		justify-content: center;
		width: 26rpx;
		height: 26rpx;
		background: #FFFFFF;
		box-shadow: 1px 1px 7px 0px rgba(0, 0, 0, 0.15);
		border-radius: 13rpx;
		font-size: 23rpx;
		font-family: MicrosoftYaHeiLight;
		font-weight: bold;
		color: #3F3F3F;
	}
	.item-jisuan1{
		display: flex;
		margin-left: 20rpx;
		margin-right: 20rpx;
		align-items: center;
		justify-content: center;
		width: 46rpx;
		height: 46rpx;
		background: #FFFFFF;
		box-shadow: 1px 1px 7px 0px rgba(0, 0, 0, 0.15);
		border-radius: 23rpx;
		font-size: 23rpx;
		font-family: MicrosoftYaHeiLight;
		font-weight: bold;
		color: #3F3F3F;
	}
	.right-back-img{
		display: flex;
		min-width: 100rpx;
		height: 51rpx;
		margin-left: 20rpx;
		background-image: url(../../static/huisebiaoqian@3x.png);
		background-repeat : no-repeat;
		background-size:100% 100%; 
		justify-content: center;
	}
	.right-back-title{
		display: flex;
		padding-left: 35rpx;
		padding-right: 25rpx;
		align-items: center;
		font-size: 24rpx;
		font-family: MicrosoftYaHeiLight;
		font-weight: bold;
		color: #FFFFFF;
		
	}
	.lin{
		display: flex;
		margin-left: 17rpx;
		margin-right: 17rpx;
		margin-top: 20rpx;
		/* width: 100%; */
		height: 1rpx;
		background: #3F3F3F;
		opacity: 0.2;
		border-radius: 1rpx;
	}
	.bottom{
		display: flex;
		height: 140rpx;
		align-items: center;
		flex-direction: row;
		/* margin-top: 30rpx; */
		margin-left: 30rpx;
		margin-right: 30rpx;
		width: 690rpx;
		justify-content: space-between;
		background-image: url(../../static/bg02.png);
		/* min-height: 300rpx; */
		background-repeat : no-repeat;
		background-size:100% 100%; 
		
	}
	.b-l{
		display: flex;
		margin-left: 30rpx;
		justify-items: center;
		align-items: center;
		background: #F5F5F5;
		box-shadow: 1px 1px 4px 0px rgba(0, 0, 0, 0.15);
		border-radius: 29rpx;
	}
	.b-l-t{
		display: flex;
		margin-left: 30rpx;
		margin-right: 30rpx;
		margin-top: 10rpx;
		margin-bottom: 10rpx;
		font-size: 25rpx;
		font-family: MicrosoftYaHeiLight;
		font-weight: bold;
		color: #3F3F3F;
	}
	.price{
		display: flex;
		margin-right: 30rpx;
		font-size: 48rpx;
		font-family: MicrosoftYaHeiLight;
		font-weight: bold;
		color: #ED8600;
		
		background: linear-gradient(-90deg, #FFB333 0%, #ED8600 100%);
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
	}
page{
				
		background-color: #F7F7F7;
			}
			/* -------- */
</style>
