<template>
	<view class="back">
		<image class="top-back-img" src="../../static/loginback@3x.png"></image>
		<image class="log" src="../../static/login_log.png"></image>
		<view class="t">共享食堂</view>
		<view @click="login" class="wchatLogin_btn">
			<view class="wchatLogin_btn_title">微信登录</view>
			</view>
			<view  @click="phoneLogin" class="phone-view">
				<view class="phone-view-title ">手机号登录</view>
			</view>
			
			<view class="item">
				<view class="Sign_Up">还没有账号?</view>
				<view @click="registered" class="Sign_Up_item">注册账号</view>
			</view>
			
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				href: 'https://uniapp.dcloud.io/component/README?id=uniui'
			}
		},
		methods: {
			registered:function(){
				uni.navigateTo({
				    url: '/pages/registered/registered'
				});
			},
			phoneLogin:function(){
				uni.navigateTo({
				    url: '/pages/phoneLogin/phoneLogin'
				});
			},
			login:function(){
				
				uni.getProvider({
				    service: 'oauth',
				    success: function (res) {
						uni.showToast({
							title:'1',
							icon:"none"
						})
				        console.log(res.provider)
						uni.showToast({
							title:'res.provider',
							icon:"none"
						})
				        if (~res.provider.indexOf('weixin')) {
				            uni.login({
				                provider: 'weixin',
				                success: function (loginRes) {
				                    console.log(JSON.stringify(loginRes));
									uni.showToast('333')
				                }
				            });
				        }
				    }
				});
				// uni.navigateTo({
				//     url: '/pages/home/home'
				// });
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
		height: 50vh;
		width: 100%;
	}
	.log{
	display: flex;
	margin-top: -40vh;
	align-items: center;
	height: 670rpx;
	width: 500rpx;
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
	.t {
	  display: flex;
	  font-size: 95rpx;
	  font-family:"Source Han Sans CN";
	  color: rgb(255, 186, 0);
	  line-height: 1.2;
	  margin-top: 40rpx;
	  text-align: center;
	  height: 60rpx;
	  top: 850rpx;
	}

	.wchatLogin_btn {
	  display: flex;
	  border-radius: 85rpx;
	  background-color: rgb(59, 152, 68);
	  box-shadow: 0.5px 0.866px 17px 0px rgba(59, 152, 63, 0.5);
	  margin-top: 90rpx;
	  width: 550rpx; 
	  margin-left: 100rpx;
	  margin-right: 100rpx;
	  align-items: center; 
	  text-align: center; 
	  height: 102rpx;
	}
	.wchatLogin_btn_title{
		display: flex;
		align-items: center;
		margin-left : 190rpx;
		font-size: 40rpx;
		font-family: "SimSun";
		color: rgb(255, 255, 255);
		line-height: 1.2;
	}
	
	.phone-view {
		display: flex;
	  background-color: rgb(255, 186, 0);
	  box-shadow: 0.5px 0.866px 17px 0px rgba(54, 84, 211, 0.5);
	  
	  border-radius: 85rpx;
	  margin-top: 50rpx;
	  width: 550rpx; 
	  /* margin-left: 100rpx;
	  margin-right: 100rpx; */
	  align-items: center; 
	  text-align: center; 
	  height: 102rpx;
	}
	
	.phone-view-title {
	display: flex;
	  font-size: 40rpx;
	  font-family: "SimSun";
	  color: rgb(255, 255, 255);
	  line-height: 1.2;
	  text-align: center;
	  margin-left : 170rpx;
	}
	.item{
		display: flex;
		margin-top: 60rpx;
		align-items: center;
		width: 400rpx;
		/* margin-left: 175rpx;
		margin-right: 175rpx; */
		margin-bottom: 100rpx;
		justify-content: space-between;
	}
	
	.Sign_Up {
	  display: flex;
	  font-size: 32.407rpx;
	  font-family: "SimSun";
	  color: rgba(52, 52, 52, 0.8);
	  line-height: 1.2;
	  text-align: center;
	  /* width: 100rpx;
	  height: 50rpx;
	  left: 200rpx; */
	}
	
	.Sign_Up_item{
		display: flex;
		font-size: 32.407rpx;
		font-family: "SimSun";
		color: rgba(37, 135, 231, 1.0);
		line-height: 1.2;
		text-align: center;
	}

  


	
</style>
