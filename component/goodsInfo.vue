<template name="goodsInfo">
	<view  class="goodsBox" @tap="goDetail()">
		<view class="goodsImg">
			<image :src="item.mainPic">
				<text style="position: absolute;bottom: 0;left: 10rpx;width: 50rpx;height: 20rpx;background-color: #4CD964;"></text>
			</image>
			
		</view>
		<view class="infoText">
			<view class="itemTitle">
				<text style="overflow:hidden;text-overflow: ellipsis;display: -webkit-box;-webkit-line-clamp: 2;-webkit-box-orient: vertical;">
					<text style="background-color: #ff0000;border-radius: 10rpx;padding-left: 5rpx;padding-right: 5rpx;font-size:18rpx;color: white;">
						天猫
					</text>
					<text>{{item.title}}</text>
		
				</text>
				
			</view>
			<view class="itemMid">
				<view class="itemPrice">
				 <view class="">
					 <text style="font-size: 20rpx;">￥</text>
					 <text>{{item.actualPrice}}</text>
				 </view>
				<view class="" ><image src="../static/1.png" style="width:150rpx;height:50rpx;margin-left: -50rpx;"></image></view>
				<!-- <text style="color: #e9ca93;font-size: 10rpx;border-radius: 10rpx;margin-left: 5rpx;padding-left: 10rpx;padding-right: 10rpx;background-image: url(../static/1.png);width: 50rpx;height: 20rpx;">券后价</text> -->
				
				</view>
				<view class="xiaoliang"><text>已售{{item.monthSales}}件</text></view>
			</view>
			<view class="quan">
				<text>{{item.couponPrice}}元券</text>
			</view>
			
			
			
		</view>

	</view>
</template>

<script>
	export default {
		name:"goodsInfo",
		props:{
			item:{
				type:Object,
				value:null
				
			}
			
		},
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style>
	.quan{
		margin-top: 10rpx;
		color: white;
	}
	.quan text{
		width: 100rpx;
		height: 40rpx;
		background-color: #ff0000;
		padding-left: 10rpx;
		padding-right: 10rpx;
		border-radius: 10rpx;
		text-align: center;
		font-size: 30rpx;
		
		
	}
	.xiaoliang{
		font-size: 85%;
		color: #808080;
	}
	.biaoqian{
		
	}
	.itemPrice{
		color: #ff0000;
		display: flex;
		
	}
	.itemPrice text{
		font-size: 120%;		
		font-weight: bold;
		
	}
	.itemMid{
		display: flex;
		justify-content: space-between;
		padding-right: 10rpx;
		margin-top: 20rpx;
		
	}
	.itemTitle{
/* 		overflow-x: hidden;
		white-space: nowrap;
		text-overflow: ellipsis; */
		height: 80rpx;
		font-size: 30rpx;
		
	}
	.infoText{
		width:500rpx;
		height: 260rpx;
		padding:10rpx;
		margin-left: 5rpx;
	/* 	color: white; */
		/* background-color: #C0C0C0; */
	}
	.goodsBox{
		width: 100%;
		display: flex;
		height: 280rpx;
		margin-top: 10rpx;
		
		background-color: #f3f3f3;
		border-radius: 20rpx;
		
	}
	.goodsImg{
		width: 260rpx;
		height: 260rpx;
		padding: 10rpx;
		
		
	}
	.goodsImg image{
		width: 260rpx;
		height: 260rpx;
		border-radius: 10rpx;
		
	}

</style>
