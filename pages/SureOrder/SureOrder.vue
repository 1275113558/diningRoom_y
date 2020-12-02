<template>
	<view>
		<nav-bar home :bgColor="['#FFB333','#ED8600']" bgColorAngle="90" fontColor="#FFF" title="确认订单">
			<image @click="backTo" class="icon_setUp" slot="left" src="../../static/back.png"></image>
			<!-- <image class="icon_setUp_r" slot="right" src="../../static/购物车@3x.png"></image> -->
		</nav-bar>
		
		<view class="backView">
			<view style="display: flex;flex-direction: row;">
				<image @click="kuaidiClick" :src="kuaidi" class="song-back">
					<!-- <image src="../../static/订单确认@3x.png"></image>
					<view>快递送餐</view> -->
				</image>
				<image @click="ziquClick" :src="ziqu" class="qu-back"></image>
			</view>
			<view class="uni-input-view">
				<input class="uni-input" placeholder="姓名" />
			</view>
			
			<view class="uni-input-view1">
				<input class="uni-input" placeholder="联系电话" />
			</view>
			
			<view class="uni-input-view1">
				<input class="uni-input" placeholder="邮箱地址" />
			</view>
			
			<view class="uni-input-view1">
				<input class="uni-input" placeholder="订单备注" />
			</view>
		</view>
		<view @click="goPay" style="display: flex; background: #FFFFFF;box-shadow: 0px -3px 9px 0px rgba(0, 0, 0, 0.1);position: fixed;height: 130rpx;width: 100%;left: 0;right: 0;bottom: 0rpx;" >
			<view style="display: flex;margin-top:20rpx;margin-bottom:20rpx;margin-left: 30rpx;margin-right: 30rpx;width: 690rpx; background: linear-gradient(-90deg, #FFB333, #ED8600);box-shadow: 0px 1px 10px 0px rgba(237, 134, 0, 0.5);border-radius: 54rpx;font-size: 39rpx;font-family: SimSun;font-weight: bold;color: #FFFFFF;align-items: center;justify-content: center;">
				继续
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				kuaidi:'../../static/kuaidisongcan1@3x.png',
				ziqu:'../../static/daodianziqu@3x.png'
			}
		},
		methods: {
			kuaidiClick:function(){
				this.kuaidi = '../../static/kuaidisongcan1@3x.png';
				this.ziqu ='../../static/daodianziqu@3x.png';
			},
			ziquClick:function(){
				this.kuaidi = '../../static/kuaidisongcan@3x.png';
				this.ziqu ='../../static/daodianziqu1@3x.png';
			},
			goPay:function(){
				uni.navigateTo({
				    url: '/pages/methodPayment/methodPayment'
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
		/* margin-top: 30rpx;
		margin-left: 30rpx;
		margin-right: 30rpx;
		width: 690rpx;
		background-image: url(../../static/bg.png);
		min-height: 300rpx;
		background-repeat : no-repeat;
		background-size:100% 100%; */
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
page{
					
	background-color: #F7F7F7;
}
.song-back{
	display: flex;
	margin-left: 30rpx;
	margin-top: 30rpx;
	width: 330rpx;
	height: 116rpx;
	/* background: #FFFFFF;
	border: 2rpx solid;
	border-image: linear-gradient(90deg, #FFB333, #ED8600) 2 2;
	box-shadow: 1px 1px 4px 0px rgba(0, 0, 0, 0.15);
	border-radius: 54rpx; */
}
.qu-back{
	display: flex;
	margin-left: 30rpx;
	margin-top: 30rpx;
	width: 330rpx;
	height: 116rpx;
}
.uni-input-view{
	display: flex;
	margin-top: 60rpx;
	margin-left: 30rpx;
	margin-right: 30rpx;
	background: #FFFFFF;
	box-shadow: 1px 1px 4px 0px rgba(0, 0, 0, 0.15);
	border-radius: 6px;
}

.uni-input-view1{
	display: flex;
	margin-top: 35rpx;
	margin-left: 30rpx;
	margin-right: 30rpx;
	background: #FFFFFF;
	box-shadow: 1px 1px 4px 0px rgba(0, 0, 0, 0.15);
	border-radius: 6px;
}

.uni-input{
	display: flex;
	margin-top: 20rpx;
	margin-left: 30rpx;
	margin-bottom: 20rpx;
	margin-right: 30rpx;
}
				
</style>
