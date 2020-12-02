<template>
	<view class="back">
		<image class="top-back-img" src="../../static/loginback@3x.png"></image>
		<image class="log" src="../../static/login_log.png"></image>
		<view class="item-back">
		<view class="item-view-back">
			<view class="left-img-view">
				<image class="left-img" src="/static/phone@3x.png"></image>
			</view>
			<input class="uni-input" type="number" placeholder="手机号码" />
		</view>
		<view class="lin"></view>
		</view>
		
		<view class="item-back">
		<view class="item-view-back1">
			<view class="left-img-view">
				<image class="left-img" src="/static/suo@3x.png"></image>
			</view>
			<input class="uni-input" password type="text" placeholder="登录密码" />
		</view>
		<view class="lin"></view>
		</view>
		
		
		<view class="res-btn">
			<view class="res-title">登录</view>
		</view>
		<view @click="back" class="back-btn">返回登录页</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			back:function(){
				uni.navigateBack({
				    // delta: 2
				});
			}
		}
	}
</script>

<style>
.back{
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	.top-back-img {
		height: 589rpx;
		width: 100%;
	}
	.log{
	display: flex;
	margin-top: -500rpx;
	align-items: center;
	height: 498rpx;
	width: 372rpx;
	line-height: 1.2;
	}
	@font-face {
	     font-family: 'Source Han Sans CN';
	     src: url('~@/static/SourceHanSansCN-Heavy-2.otf');
	 }
	 @font-face {
	 	font-family: 'simsun';
	 	src: url('~@/static/simsun.ttf');
	 }
	 .item-back{
		 display: flex;
		 flex-direction: column;
		 margin-top: 60rpx;
	 }
	 .item-view-back{
		 display: flex;
		 flex-direction: row;
		 margin-top: 30rpx;
		 /* justify-content: space-between; */
		 /* justify-content:flex-start; */
	 }
	 .item-view-back1{
	 		 display: flex;
	 		 flex-direction: row;
	 		 margin-top: 0rpx;
	 		 /* justify-content: space-between; */
	 		 /* justify-content:flex-start; */
	 }
	 .left-img-view{
		 display: flex;
		 /* 
		 position: fixed; */
		 /* left: 70rpx; */
		 margin-left: 70rpx;
		 margin-top: 5rpx;
		 /* width: 43rpx;
		 height: 43rpx; */
		 /* justify-content:flex-start; */
	 }
	 .left-img{
		 /* display: flex; */
		 /* position: fixed; */
		 /* margin-left: 60rpx; */
		 width: 43rpx;
		 height: 43rpx;
		 justify-content:flex-start;
	 }
	 
	 .uni-input{
		 /* position: fixed; */
		 display: flex;
		 /* left: 160rpx; */
		 margin-left: 20rpx;
	 }
	 .item-title{
		 
		 font-size: 30rpx;
		 font-family: SimSun;
		 font-weight: 400;
		 color: #3A3A3A;
		 opacity: 0.75;
	 }
	 .lin{
		 display: flex;
		 margin-top: 40rpx;
		 width: 700rpx;
		 height: 2rpx;
		 background-color: #000000;
		 opacity: 0.1;
	 }
	 
	 .code{
		 display: flex;
		 position: fixed;
		 right: 60rpx;
		 font-size: 30rpx;
		 font-family: YouYuan;
		 font-weight: bold;
		 color: #F2920D;
		 opacity: 0.75;
	 }
	 .res-btn{
		 display: flex;
		 width: 550rpx;
		 margin-top: 130rpx;
		 margin-left: 100rpx;
		 margin-right: 100rpx;
		 background: linear-gradient(-90deg, #FFB333, #ED8600);
		 box-shadow: 0px 1px 10px 0px rgba(237, 134, 0, 0.5);
		 border-radius: 52rpx;
		 align-items: center;
		 text-align: center; 
		 height: 102rpx;
	 }
	 .res-title{
		 display: flex;
		 align-items: center;
		 text-align: center; 
		 font-size: 37rpx;
		 margin-left: 235rpx;
		 font-family: MicrosoftYaHeiLight;
		 font-weight: 400;
		 color: #FFFFFF;
	 }
	 .back-btn{
		 display: flex;
		 margin-top: 30rpx;
		 font-size: 29rpx;
		 font-family: MicrosoftYaHeiLight;
		 font-weight: 400;
		 color: #3A3A3A;
	 }
</style>
