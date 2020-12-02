<template>
	<view>
		<nav-bar home :bgColor="['#FFB333','#ED8600']" bgColorAngle="90" fontColor="#FFF" :title="title">
			<image @click="backTo" class="icon_setUp" slot="left" src="../../static/back.png"></image>
			<image class="icon_setUp_r" slot="right" src="../../static/gouwuche@3x.png"></image>
		</nav-bar>
		<view class="backView">
			<view class="top-img-back"></view>
			<view class="detail-back-view">
				<view class="top-view">
					<view class="top-left-back-view">
						<view class="title">凉拌马铃薯</view>
						<view style="display: flex;flex-direction: row;align-items: center;margin-top: 10rpx;">
							<view style="font-size: 22rpx;font-family: MicrosoftYaHeiLight;font-weight: boldcolor: #3F3F3F;
opacity: 0.8;">4.5</view>
							<view class="uni-rate-view"><uni-rate size="10" :touchable="false" color="#FFFFFF" active-color="#656565" :value="4.5"/></view>
							<view style="font-size: 22rpx;font-family: MicrosoftYaHeiLight;font-weight: boldcolor: #3F3F3F;
							opacity: 0.8;">（18评论）</view>
						</view>
					</view>
					<view class="top-right-back-view">
						<view class="price-back">
							<image class="price-back-img" src="../../static/biaoqian@3x.png"></image>
						</view>
						<view class="price-back">
							<view class="price-back-title-yj">182~23</view>
							<view class="price-back-title-sj">2.25$</view>
						</view>
					</view>
					
					
				</view>
				<view class="lin"></view>
				<view class="tip">外面酥脆，里面有点甜，有点辣，蜂蜜、辣椒、土豆都是你想要吃点东西时吃的最好的东西。如果你想使这个食谱稍微健康一点，你可以烤土豆脆，而不是油炸他们。一个完美的启动任何政党，只需递给你的每一个客人一把牙签，让党开始！</view>
			</view>
			
			<view class="tip2" style="font-size: 36rpx;font-family: MicrosoftYaHei;font-weight: 400;
color: #3F3F3F;">请发表你的评论</view>
			<view class="item3-back">
				<view class="uni-input"><input placeholder="输入文字..." /></view>
				<view class="img2"><image style="width: 50rpx;height: 50rpx;" class="img2" src="../../static/fasong@3x.png"></image></view>
			</view>
			<view>
				
			</view>
			<view class="item3-back-1">
				<view style="display: flex;flex-direction: column;">
					<view class="item3-back-2">
						<view class="item3-left">
							<image style="width: 80rpx;height: 80rpx;margin: 20rpx;" src="../../static/longbaoImage@2x.png"></image>
						</view>
						<!-- <view class="item3-right"> -->
							<view style="display: flex;flex-direction: column;margin-top: 10rpx;">
								<view style="display: flex;flex-direction: row;">
									<view style="font-size: 28rpx;font-family: MicrosoftYaHei;font-weight: 400;color: #3F3F3F;">Alex Stone </view>
									<uni-rate style="margin-top: 6rpx;margin-left: 10rpx;align-items: center;" size="10" :touchable="false" :value="4.5"/>
								</view>
								
								<view style="font-size: 21rpx;font-family: MicrosoftYaHeiLight;font-weight: bold;color: #142029;line-height: 36rpx;opacity: 0.8;">哟，中国提供了完美的地方，体验正宗中国菜有轻微的印度变化，使您的口味。蓓蕾遍布Lala。
						            </view>
							</view>
					</view>
					<view>
						<view class="lin"></view>
						<view style="display: flex;flex-direction: row;display: flex;align-items: center;justify-content: center;font-size: 21rpx;font-family: MicrosoftYaHeiLight;font-weight: bold;color: #9E9FA1;line-height: 49rpx;">
							<view style="display: flex;flex-direction: row;align-items: center;justify-content: center;width: 200rpx;">
								<image style="width: 30rpx;height: 30rpx;" src="../../static/zan@3x.png"></image>
								<view style="margin-left: 10rpx;">2</view>
								<view style="margin-left: 10rpx;">赞</view>
							</view>
							<view style="display: flex;flex-direction: row;align-items: center;justify-content: center;width: 200rpx;">
								<image style="width: 30rpx;height: 30rpx;" src="../../static/pinlun@3x.png"></image>
								<view style="margin-left: 10rpx;">暂无评论</view>
							</view>
						</view>
					</view>
				</view>
				
				
			</view>
			
			
		</view>
		
		<view @click="goMake" style="display: flex; background: #FFFFFF;box-shadow: 0px -3px 9px 0px rgba(0, 0, 0, 0.1);position: fixed;height: 130rpx;width: 100%;left: 0;right: 0;bottom: 0rpx;" >
			<view style="display: flex;margin-top:20rpx;margin-bottom:20rpx;margin-left: 30rpx;margin-right: 30rpx;width: 690rpx; background: linear-gradient(-90deg, #FFB333, #ED8600);box-shadow: 0px 1px 10px 0px rgba(237, 134, 0, 0.5);border-radius: 54rpx;font-size: 39rpx;font-family: SimSun;font-weight: bold;color: #FFFFFF;align-items: center;justify-content: center;">
				我要吃这个
			</view>
		</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title:'',
			}
		},
		methods: {
			backTo:function(){
				uni.navigateBack({
				    // delta: 2
				});
			},
			goMake:function(){
				uni.navigateTo({
				    url:'../makeSureOrder/makeSureOrder'
				});
			}
		},
		onLoad:function(options) {
		             //options可以接到index 传过来的值
		             console.log(options)
					 this.title = options.title
		         },
	}
</script>

<style>
.top-img-back{
	display: flex;
	background-color: red;
	height: 508rpx;
	margin-left: 0rpx;
	margin-right: 0rpx;
	width: 100%;
}
/* ----NAV */
.backView{
		display: flex;
		flex-direction: column;
		align-items: center;
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
/* ----- */
.detail-back-view{
	display: flex;
	margin-top: -140rpx;
	margin-left: 30rpx;
	margin-right: 30rpx;
	width: 690rpx;
	background: #FFFFFF;
	box-shadow: 1px 1px 4px 0px rgba(0, 0, 0, 0.15);
	border-radius: 24rpx;
	min-height: 300rpx;
	flex-direction: column;
}
.top-view{
	display: flex;
	flex-direction: row;
	width: 100%;
	/* align-items: center; */
	justify-content: space-between;
}
.top-left-back-view{
	display: flex;
	flex-direction: column;
	margin-left: 30rpx;
	margin-top: 30rpx;
}
.top-right-back-view{
	display: flex;
	/* background-color: #07C160; */
	margin-top: 30rpx;
	/* margin-right: 30rpx; */
	width: 171rpx;
	height: 75rpx;
}
.title{
	
	font-size: 36rpx;
	font-family: MicrosoftYaHei;
	font-weight: 400;
	color: #3F3F3F;
}
.price-back{
		display: flex;
		position: absolute;
		width: 184rpx;
		height: 100rpx;
		right: 23rpx;
		/* top: 30rpx; */
		/* right: -5rpx; */
		/* width: 100rpx; */
		/* height: 55rpx; */
		align-items: center;
		flex-direction: column;
	}
	.price-back-img{
		width: 184rpx;
		height: 100rpx;
	}
	.price-back-title-yj{
		display: flex;
		margin-top: 10rpx;
		margin-left: 20rpx;
		font-size: 21rpx;
		font-family: MicrosoftYaHeiLight;
		font-weight: bold;
		color: #FFFFFF;
		opacity: 0.6;
		text-decoration:line-through;
	}
	.price-back-title-sj{
		display: flex;
		margin-top: 3rpx;
		margin-left: 20rpx;
		font-size: 33rpx;
		font-family: MicrosoftYaHeiLight;
		font-weight: bold;
		color: #FFFFFF;
	}
	.uni-rate-view{
		display: flex;
		margin-left: 10rpx;
		margin-top: 5rpx;
	}
	.lin{
		display: flex;
		margin-top: 21rpx;
		height: 1rpx;
		background: #000000;
		opacity: 0.2;
	}
	.tip{
		margin-top: 20rpx;
		margin-left: 30rpx;
		margin-right: 30rpx;
		margin-bottom: 60rpx;
		font-size: 23rpx;
		font-family: MicrosoftYaHeiLight;
		font-weight: bold;
		color: #3F3F3F;
		line-height: 45rpx;
	}
	.tip2{
		display: flex;
		margin-left: -400rpx;
	}
	.item3-back{
		/* background-color: #07C160; */
		display: flex;
		flex-direction: row;
		margin-top: 30rpx;
		margin-left: 30rpx;
		margin-right: 30rpx;
		width: 690rpx; 
		background: #FFFFFF; 
		box-shadow: 1px 1px 4px 0px rgba(0, 0, 0, 0.15);
		border-radius: 18rpx;
		min-height: 80rpx;
		align-items: center;
		text-decoration:line-through;
		flex-direction: row;
		/* width: 100%; */
		/* align-items: center; */
		justify-content: space-between;
	}
	.item3-back-1{
		/* background-color: #07C160; */
		display: flex;
		flex-direction: column;
		margin-top: 30rpx;
		margin-left: 30rpx;
		margin-right: 30rpx;
		margin-bottom: 200rpx;
		width: 690rpx; 
		background: #FFFFFF; 
		box-shadow: 1px 1px 4px 0px rgba(0, 0, 0, 0.15);
		border-radius: 18rpx;
		min-height: 80rpx;
		align-items: center;
		/* text-decoration:line-through; */
		/* flex-direction: row; */
		/* width: 100%; */
		/* align-items: center; */
		justify-content: left;
	}
	.item3-back-2{
		/* background-color: #07C160; */
		display: flex;
		flex-direction: row;
		/* margin-top: 30rpx; */
		/* margin-left: 30rpx; */
		/* margin-right: 30rpx; */
		/* margin-bottom: 60rpx; */
		/* width: 690rpx; */
		/* background: #FFFFFF; */
		/* box-shadow: 1px 1px 4px 0px rgba(0, 0, 0, 0.15); */
		/* border-radius: 18rpx; */
		/* min-height: 80rpx; */
		align-items: center;
		/* text-decoration:line-through; */
		flex-direction: row;
		/* width: 100%; */
		/* align-items: center; */
		justify-content: left;
	}
	.uni-input{
		display: flex;
		margin-left: 20rpx;
		margin-right: 30rpx;
		/* width: 400rpx; */
	}
	.img2{
		display: flex;
		margin-right: 10rpx;
		width: 50rpx;
		height: 50rpx;
	}
	.item3-left{
		display: flex;
	}
	.item3-right{
		display: flex;
		flex-direction: column;
		justify-content: left;
	}
page{
			
	background-color: #F7F7F7;
		}
</style>
