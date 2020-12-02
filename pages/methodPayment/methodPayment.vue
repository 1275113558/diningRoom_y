<template>
	<view>
		<nav-bar home :bgColor="['#FFB333','#ED8600']" bgColorAngle="90" fontColor="#FFF" title="支付方式">
			<image @click="backTo" class="icon_setUp" slot="left" src="../../static/back.png"></image>
			<!-- <image class="icon_setUp_r" slot="right" src="../../static/购物车@3x.png"></image> -->
		</nav-bar>
		<view>
			<uni-segmented-control style="font-size: 24rpx;font-family: MicrosoftYaHeiLight;font-weight: bold;" :current="current" :values="items" @clickItem="onClickItem" style-type="text" active-color="#ED8600"></uni-segmented-control>
					<view class="lin"></view>
					<view class="content">
					    <view v-if="current === 0">
					        账户余额
					    </view>
					    <view style="display: flex;flex-direction: column;" v-if="current === 1">
					        <special-banner :banner-list="bannerList" :swiper-config="swiperConfig"></special-banner>
							
							<view class="uni-input-view">
								<input class="uni-input" placeholder="详细地址" />
							</view>
							<view @click="chooseWeizhi" class="uni-input-view1">
								<input disabled class="uni-input" placeholder="位置选择" :value="address"/>
							</view>
							<view class="uni-input-view1">
								<input class="uni-input" placeholder="选择城市" />
							</view>
					    </view>
					    <view v-if="current === 2">
					        网络银行
					    </view>
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
	import uniSegmentedControl from "@/components/uni-segmented-control/uni-segmented-control.vue"
	import specialBanner from "@/components/EtherealWheat-banner/specialBanner.vue"
	export default {
		components: {uniSegmentedControl,specialBanner},
		data() {
			return {
				items: ['账户余额','信用卡','网络银行'],
				current: 1,
				bannerList: [{
				            picture: 'http://image.mishi.cn/r/yry_h5_test/detail/3_1535359279285.png',
				            
				        }, {
				            picture: 'http://image.mishi.cn/r/yry_h5_test/detail/2_1535359240426.png',
				            
				        }, {
				            picture: 'http://image.mishi.cn/r/yry_h5_test/detail/1_1535359204228.png',
				            
				            
				        }, {
				            picture: 'http://image.mishi.cn/r/yry_h5_test/detail/4_1535359327213.png',
				            
				        }],
				        swiperConfig: {
				            indicatorDots: true,
				            indicatorColor: 'rgba(255, 255, 255, .4)',
				            indicatorActiveColor: 'rgba(255, 255, 255, 1)',
				            autoplay: false,
				            interval: 3000,
				            duration: 300,
				            circular: true,
				            previousMargin: '58rpx',
				            nextMargin: '58rpx'
				        },
						address:''
			}
		},
		methods: {
			onClickItem(e) {
			            if (this.current !== e.currentIndex) {
			                this.current = e.currentIndex;
			            }
			        },
					goPay:function(){
						uni.navigateTo({
						    url: '/pages/orderConfirmation/orderConfirmation'
						});
					},
					backTo:function(){
						uni.navigateBack({
						    // delta: 2
						});
					},
					chooseWeizhi:function(){
						var that = this
						
						uni.chooseLocation({
						    success: function (res) {
								that.address = res.address
						        console.log('位置名称：' + res.name);
						        console.log('详细地址：' + res.address);
						        console.log('纬度：' + res.latitude);
						        console.log('经度：' + res.longitude);
						    }
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
.lin{
	display: flex;
	/* margin-left: 17rpx;
	margin-right: 17rpx; */
	/* margin-top: 20rpx; */
	/* width: 100%; */
	height: 1rpx;
	background: #3F3F3F;
	opacity: 0.2;
	border-radius: 1rpx;
}
.uni-input-view{
	display: flex;
	margin-top: -60rpx;
	margin-left: 30rpx;
	margin-right: 30rpx;
	background: #FFFFFF;
	box-shadow: 1px 1px 4px 0px rgba(0, 0, 0, 0.15);
	border-radius: 6px;
	width: 500rpx;
}

.uni-input-view1{
	display: flex;
	margin-top: 30rpx;
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
