<template name="goodsInfo">
	<view  class="goodsBox">
		<view class="goodsImg">
			<image :src="item.mainPic">
				<text style="position: absolute;bottom: 0;left: 10rpx;width: 50rpx;height: 20rpx;background-color: #4CD964;"></text>
			</image>
			
		</view>
		<view class="infoText">
			<view class="itemTitle">
				<text style="overflow:hidden;text-overflow: ellipsis;display: -webkit-box;-webkit-line-clamp: 2;-webkit-box-orient: vertical;">
					<text>
						
					</text>
					<text>{{item.title}}</text>
		
				</text>
				
			</view>
			<view class="itemMid">
				<view class="itemPrice">￥<text>{{item.actualPrice}}</text></view>
				<view class=""><text>已售{{item.monthSales}}件</text></view>
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
	.biaoqian{
		
	}
	.itemPrice{
		
	}
	.itemMid{
		display: flex;
		
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
		color: white;
		background-color: #C0C0C0;
	}
	.goodsBox{
		width: 100%;
		display: flex;
		height: 280rpx;
		margin-top: 10rpx;
		
		background-color: #000000;
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
