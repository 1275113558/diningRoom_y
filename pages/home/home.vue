<template>
	<view>
		<nav-bar home :bgColor="['#FFB333','#ED8600']" bgColorAngle="90" fontColor="#FFF" title="菜单">
			<image @click="handleClick" class="icon_setUp" slot="left" src="../../static/caidanlist@3x.png"></image>
			<image class="icon_setUp_r" slot="right" src="../../static/gouwuche@3x.png"></image>
		</nav-bar>
		<uni-drawer ref="drawer">
			<view class="leftbackVIew"></view>
			
			<view class="item-back">
				<image class="item-back-img" src="../../static/caidan1@3x.png"></image>
				<view class="item-back-title-choose">菜单</view>
			</view>
			
			<view class="item-back" @click="myOrderList">
				<image class="item-back-img" src="../../static/dingdan@3x.png"></image>
				<view class="item-back-title-noChoose">订单</view>
			</view>
			
			<view class="item-back">
				<image class="item-back-img" src="../../static/huiyuan@3x.png"></image>
				<view class="item-back-title-choose">会员</view>
			</view>
			
			<view class="item-back">
				<image class="item-back-img" src="../../static/zhangdan@3x.png"></image>
				<view class="item-back-title-choose">账单</view>
			</view>
			
			<view class="item-back">
				<image class="item-back-img" src="../../static/shezhi@3x.png"></image>
				<view class="item-back-title-choose">设置</view>
			</view>
			
			<view class="item-lin"></view>
			
			<view @click="hexiaoma" class="item-back">
				<image class="item-back-img" src="../../static/erweima.png"></image>
				<view class="item-back-title-tip">核销码</view>
			</view>
			
			
		</uni-drawer>
		<view class="uni-grid-back">
			<uni-grid class="uni-grid-super" :show-border="false" :highlight="false" :column="2" @change="navToDetailPage">
			    <uni-grid-item class="uni-grid-item-item" v-for="item in list" :index="item.id">
			        <view class="item-view-back">
						<image class="img-back" :src='item.img'></image>
						<view class="name">{{item.name}}</view>
						<view class="star-back">
							<uni-rate size="10" :touchable="false" :value="item.star"/>
						</view>
						<view class="price-text">{{item.price}}</view>
						
					</view>
			    </uni-grid-item>
			    
			</uni-grid>
		</view>
		
	</view>
</template>

<script>
	import uniDrawer from "@/components/uni-drawer/uni-drawer.vue"
	import uniGrid from "@/components/uni-grid/uni-grid.vue"
	import uniGridItem from "@/components/uni-grid-item/uni-grid-item.vue"
	export default {
		components: {
			uniDrawer,
			uniGrid,
			uniGridItem
			},
		data() {
			return {
				list:[
					{'name':'休闲食品','id':1,'img':'../../static/xiuxianshiping@3x.png','price':'1$ - 10$','star':'5'},
					{'name':'中国菜','id':2,'img':'../../static/zhonguocai@3x.png','price':'13$ - 19$','star':'6'},
					{'name':'非素食','id':3,'img':'../../static/feisushi@3x.png','price':'1$ - 2$','star':'7'},
					{'name':'饮料','id':4,'img':'../../static/yingliao@3x.png','price':'5$ - 9$','star':'4'},
					{'name':'披萨','id':5,'img':'../../static/pisa@3x.png','price':'3$ - 5$','star':'5'},
					{'name':'甜甜圈','id':6,'img':'../../static/tiantianquan@3x.png','price':'2$ - 7$','star':'2'}
				]
			}
		},
		methods: {
			
			onshou:function(){
				
			},
			handleClick:function(){
			        this.$refs.drawer.open();
			    },
			myOrderList:function(){
				uni.navigateTo({
				    url: '/pages/myOrderList/myOrderList'
				});
			},	
			hexiaoma:function(){
				uni.navigateTo({
				    url: '/pages/myVerificationCode/myVerificationCode'
				});
			},
			navToDetailPage:function(e){
					console.log(e.detail.index)
					var title = this.list[e.detail.index-1].name
					uni.navigateTo({
					    url: '/pages/foodList/foodList?title='+title
					});
				}
		}
	}
</script>

<style>
	page{
		
background-color: #F7F7F7;
	}
.backView{
		display: flex;
		flex-direction: column;
		align-items: center;
	}
.icon_setUp{
	display: flex;
	margin-left: 20rpx;
	width: 40rpx;
	height: 40rpx;
}
.icon_setUp_r{
	display: flex;
	margin-right: 20rpx;
	width: 40rpx;
	height: 40rpx;
}
.item-view-back{
	display: flex;
	flex-direction: column;
	align-items: center;
	/* background-color: red; */
	margin-top: 10rpx;
	margin-left: 80rpx;
	margin-right: 40rpx;
	
	width: 300rpx;
	height: 300rpx;
	
	background: #FFFFFF;
	box-shadow: 0px 1px 4px 0px rgba(0, 0, 0, 0.15);
	border-radius: 24rpx;
}

.img-back{
	margin-top: 40rpx;
	width: 107rpx;
	height: 107rpx;
}

.name{
	display: flex;
	font-size: 30rpx;
	font-family: MicrosoftYaHeiLight;
	margin-top: 20rpx;
	font-weight: 400;
	color: #000000;
	opacity: 0.7;
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
.star-back{
	display: flex;
	margin-top: 20rpx;
}
.price-text{
	display: flex;
	margin-top: 20rpx;
	font-size: 23rpx;
	font-family: MicrosoftYaHeiLight;
	font-weight: 400;
	color: #ADADAD;
}


/* --------侧滑 */

.leftbackVIew{
	display: flex;
	flex-direction: column;
}

.item-back{
	display: flex;
	flex-direction: row;
	margin-top: 60rpx;
	align-items: center;
}

.item-back-img{
	margin-left: 60rpx;
	width: 136rpx;
	height: 136rpx;
}

.item-back-title-choose{
	display: flex;
	margin-left: 40rpx;
	
	font-size: 42rpx;
	font-family: MicrosoftYaHeiLight;
	font-weight: 400;
	color: #FFB333;
	
	/* background: linear-gradient(-90deg, #FFB333 0%, #ED8600 100%);
	-webkit-background-clip: text;
	-webkit-text-fill-color: transparent; */
}

.item-back-title-noChoose{
	display: flex;
	margin-left: 40rpx;
	
	font-size: 42rpx;
	font-family: MicrosoftYaHeiLight;
	font-weight: 400;
	color:#3A3A3A;
	
	/* background: linear-gradient(-90deg, #FFB333 0%, #ED8600 100%); */
	/* -webkit-background-clip: text;
	-webkit-text-fill-color: transparent; */
}

.item-lin{
	display: flex;
	margin-top: 100rpx;
	margin-left: 30rpx;
	margin-right: 30rpx;
	height: 2rpx;
	background-color: #ED8600;
	opacity: 0.5;
}

.item-back-title-tip{
	display: flex;
	margin-left: 40rpx;
	
	
	font-size: 42rpx;
	font-family: SimSun;
	font-weight: 400;
	color: #3A3A3A;
}

</style>
