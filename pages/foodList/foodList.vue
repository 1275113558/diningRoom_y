<template>
	<view>
		<nav-bar home :bgColor="['#FFB333','#ED8600']" bgColorAngle="90" fontColor="#FFF" :title="title">
			<image @click="backTo" class="icon_setUp" slot="left" src="../../static/back.png"></image>
			<image class="icon_setUp_r" slot="right" src="../../static/gouwuche@3x.png"></image>
		</nav-bar>
		<view class="uni-grid-back">
			<uni-grid class="uni-grid-super" :highlight="false" :show-border="false" :column="2" @change="navToDetailPage">
			    <uni-grid-item class="uni-grid-item-item" v-for="item in list" :index="item.id">
			        <view class="item-view-back" @click="foodDetail">
						<image class="img-back" :src='item.img'></image>
						<view class="name">{{item.name}}</view>
						<view class="star-back">
							<uni-rate size="10" :touchable="false" :value="item.star"/>
						</view>
						<view class="price-back">
							<image class="price-back-img" src="../../static/biaoqian@3x.png"></image>
						</view>
						<view class="price-back">
							<view class="price-back-title-yj">182~23</view>
							<view class="price-back-title-sj">{{item.price}}</view>
						</view>
						<!-- <view class="price-text">{{item.price}}</view> -->
					</view>
					<view v-if="item.choose == 0" class="btn-back">
						<view class="btn-title">添加</view>
					</view>
					<view v-if="item.choose == 1" class="btn-back_choose">
						<view class="btn-title_choose">已添加</view>
					</view>
			    </uni-grid-item>
			</uni-grid>
		</view>
		
	</view>
</template>

<script>
	import uniGrid from "@/components/uni-grid/uni-grid.vue"
	import uniGridItem from "@/components/uni-grid-item/uni-grid-item.vue"
	export default {
		components: {
			uniGrid,
			uniGridItem
			},
		data() {
			return {
				title:'',
				list:[
					{'name':'猪肉饺子','id':1,'img':'../../static/longbaoImage@2x.png','price':'1$ - 10$','star':'5','choose':'1'},
					{'name':'烤春卷','id':2,'img':'../../static/longbaoImage@2x.png','price':'13$ - 19$','star':'6','choose':'0'},
					{'name':'兰州炒面','id':3,'img':'../../static/longbaoImage@2x.png','price':'1$ - 2$','star':'7','choose':'0'},
					{'name':'凉拌马铃薯','id':4,'img':'../../static/longbaoImage@2x.png','price':'5$ - 9$','star':'4','choose':'0'},
					{'name':'冰海鲜','id':5,'img':'../../static/longbaoImage@2x.png','price':'3$ - 5$','star':'5','choose':'0'},
					{'name':'蒜香辣子鸡','id':6,'img':'../../static/longbaoImage@2x.png','price':'2$ - 7$','star':'2','choose':'1'}
				]
			}
			
		},
		
		methods: {
			
				backTo:function(){
					uni.navigateBack({
					    // delta: 2
					});
				},
				navToDetailPage:function(e){
						console.log(e.detail.index)
						var title = this.list[e.detail.index-1].name
						uni.navigateTo({
						    url: '/pages/foodDetail/foodDetail?title='+title
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
		
		background-color: #FFFFFF;
		box-shadow: 0px 1px 4px 0px rgba(0, 0, 0, 0.15);
		border-radius: 24rpx;
	}
	
	.btn-back_choose{
		display: flex;
		margin-top: -20rpx;
		margin-left: 140rpx;
		box-shadow: 1px 1px 7px 0px rgba(0, 0, 0, 0.15);
		border-radius: 21rpx;
		width: 198rpx;
		height: 42rpx;
		align-items: center;
		background: linear-gradient(-90deg, #FFB333, #ED8600);
		box-shadow: 0px 1px 9px 0px rgba(237, 134, 0, 0.3);
	}
	.btn-title_choose{
		margin-left: 80rpx;
		font-size: 18rpx;
		font-family: MicrosoftYaHeiLight;
		font-weight: bold;
		color: #FFFFFF;
	}
	.btn-back{
		display: flex;
		margin-top: -20rpx;
		margin-left: 140rpx;
		background-color: #FFFFFF;
		box-shadow: 1px 1px 7px 0px rgba(0, 0, 0, 0.15);
		border-radius: 21rpx;
		width: 198rpx;
		height: 42rpx;
		align-items: center;
	}
	.btn-title{
		margin-left: 80rpx;
		font-size: 18rpx;
		font-family: MicrosoftYaHeiLight;
		font-weight: bold;
		color: #3F3F3F;
	}
	.price-back{
		display: flex;
		position: absolute;
		top: 30rpx;
		right: -25rpx;
		width: 100rpx;
		height: 55rpx;
		align-items: center;
		flex-direction: column;
	}
	.price-back-img{
		width: 100rpx;
		height: 55rpx;
	}
	.price-back-title-yj{
		display: flex;
		margin-top: 5rpx;
		margin-left: 20rpx;
		font-size: 11rpx;
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
		font-size: 18rpx;
		font-family: MicrosoftYaHeiLight;
		font-weight: bold;
		color: #FFFFFF;
	}
	page{
			
	background-color: #F7F7F7;
		}
</style>
