<template>
	<view class="">
		<view>
			<view class="headerNavigationbar rowCenBet borderBox">
				<view class="leftContent rowCen">
					<!-- <view class="backIcon rowCenSta" >
						<image src="@/static/return.png" mode=""></image>
					</view> -->
					<view class="search-container rowCenBet borderBox">
						<input class="searchInput" type="text" @input='searchInput' @confirm="GoSearch()" v-model="searchText"
						 placeholder="输入商品或粘贴宝贝标题搜索" placeholder-class='searchplaceHolder' />
						<view class="rightIcon rowCenBet" v-if="searchText">
							<view class="searchicon iconfont" @click="cleanSearch()">
								&#xe641;
							</view>
						</view>
					</view>
				</view>
				<view class="searchbtn rowCenEnd" @click="GoSearch()">
					<view>搜索</view>
				</view>
			</view>
		</view>
		
		
		<view class="pageContent-container colCen borderBox">
			<view class="searchcontent" >
				<view class="receiptNotes-container colCen borderBox" >
					<view class="content-title">
						<view class="title-box">
							三步轻松获得优惠券
						</view>
					</view>
		
					<view class="steplist-container rowCen" style="display: flex;">
						<view class="itembox rowCen" style="display: flex;margin-left: 10rpx;">
							<view class="defIcon iconbox">
								<image src="../../static/searchTao.png" mode="" style="width: 31rpx;height: 31rpx;margin-right: 10rpx;"></image>
							</view>
							<view class="textTips" style="font-size: 26rpx;">
								1.进入淘宝
							</view>
						</view>
						<view class="itembox rowCen" style="display: flex;margin-left: 10rpx;">
							<view class="defIcon iconbox" >
								<image src="../../static/searchCopy.png" mode="" style="width: 31rpx;height: 31rpx;margin-right: 10rpx;"></image>
							</view>
							<view class="textTips" style="font-size: 26rpx;">
								2.复制商品标题
							</view>
						</view>
						<view class="itembox rowCen" style="display: flex;margin-left: 10rpx;">
							<view class="defIcon iconbox">
								<image src="../../static/searchQuan.png" mode="" style="width: 31rpx;height: 31rpx;margin-right: 10rpx;"></image>
							</view>
							<view class="textTips" style="font-size: 26rpx;">
								3.打开APP
							</view>
						</view>
					</view>
				</view>
				
				</view>
				</view>
			
		
		
		
		

			
			
		
		
		
		<view class="guessLike-container">
			<view class="bottom-title rowCenCen">
				<view class="bordercontent"></view>
				<view class="texttitle">
					猜你喜欢
				</view>
				<view class="bordercontent"></view>
			</view>
		</view>
		
		
	</view>
</template>


<script>
	
	export default {
		data() {
			return {
				title: 'Hello',
				searchText:''
		
			}
		},
		onLoad() {
	
		},
		methods: {
			cleanSearch() {
				this.searchText = ''
			},
			GoSearch(){
				uni.navigateTo({
					url: 'searchResult?searchText=' + this.searchText 
					
				});
				},
				searchInput(){
					
				}
	
		}
	}
</script>

<style lang="scss">


	.texttitle {
		font-size: 28rpx;
		font-weight: 500;
		color: #FF4242;
		margin: 0 30rpx;
	}
	
	
	.guessLike-container {
		width: 100%;
		background-color: #FFFFFF;
		margin-top: 20rpx;
		}
	.bottom-title {
		margin-top: 30rpx;
		margin-bottom: 20rpx;
		}
	.bordercontent {
		width: 30rpx;
		height: 4rpx;
		margin-top: 10rpx;
		border-radius: 2rpx;
		background-color: transparent;
	}
	
	.headerNavigationbar {
		width: 100%;
		height: 90rpx;
		padding: 0 32rpx;
		display: flex;
		}
	.searchbtn {
		padding-top: 10rpx;
		font-size: 30rpx;
		font-weight: 500;
		margin-left: 15rpx;
		color: #333333;
	}
	.search-container {
		width: 554rpx;
		height: 60rpx;
		background: #F0F1F7;
		border-radius: 30rpx;
		padding: 0 32rpx;
		}
		
	.searchInput {
		width: 90%;
		height: 100%;
		font-size: 24rpx;
		font-weight: 400;
		color: #222222;
	}
	.searchplaceHolder {
		font-size: 24rpx;
		font-weight: 400;
		color: #999999;
	}
	.backIcon {
		width: 40rpx;
		height: 32rpx;
		z-index: 1;
	
		image {
			width: 17rpx;
			height: 32rpx;
		}
		}
		
	
	
	
	.searchindex-wrapper {
		width: 100%;
	
		.backTitlebar-wrapper {
			.placeBox {
				.placeemptybox {}
			}
	
			.fixedBox {
				width: 100%;
				position: fixed;
				top: 0;
				left: 0;
				z-index: 100;
				background-color: #FFFFFF;
	
				.headerNavigationbar {
					width: 100%;
					height: 90rpx;
					padding: 0 32rpx;
	
					.leftContent {
						.backIcon {
							width: 40rpx;
							height: 32rpx;
							z-index: 1;
	
							image {
								width: 17rpx;
								height: 32rpx;
							}
						}
	
						.search-container {
							width: 554rpx;
							height: 60rpx;
							background: #F0F1F7;
							border-radius: 30rpx;
							padding: 0 32rpx;
	
							.searchInput {
								width: 90%;
								height: 100%;
								font-size: 24rpx;
								font-weight: 400;
								color: #222222;
							}
	
							.searchplaceHolder {
								font-size: 24rpx;
								font-weight: 400;
								color: #999999;
							}
	
							.rightIcon {
								.searchicon {
									color: #222222;
								}
							}
						}
					}
	
					.searchbtn {
						font-size: 28rpx;
						font-weight: 500;
						color: #333333;
					}
				}
	
				.onlineStore-container {
					width: 100%;
					height: 80rpx;
					background-color: #FFFFFF;
					padding: 0 32rpx;
	
					.onlineStoreList {
						width: 100%;
						height: 100%;
	
						.store-items {
							margin-right: 60rpx;
	
							.store-name {
								font-size: 28rpx;
								font-weight: 500;
								color: #999999;
								margin-top: 20rpx;
							}
	
							.bordercontent {
								width: 30rpx;
								height: 4rpx;
								margin-top: 10rpx;
								border-radius: 2rpx;
								background-color: transparent;
							}
						}
	
						.store-items-active {
							.store-name {
								font-size: 28rpx;
								font-weight: 500;
								color: #FF4242;
							}
	
							.bordercontent {
								width: 30rpx;
								height: 4rpx;
								background-color: #FF4242;
							}
						}
					}
				}
			}
		}
	
		.pageContent-container {
			width: 100%;
	
			.receiptNotes-container {
				width: 100%;
				height: 130rpx;
				margin-bottom: 20rpx;
				padding: 0 32rpx;
				background-color: #FFFFFF;
	
				.content-title {
					width: 100%;
					font-size: 24rpx;
					font-weight: bold;
					color: #333333;
					margin-top: 15rpx;
				}
	
				.steplist-container {
					width: 100%;
					margin-top: 25rpx;
	
					.itembox {
						margin-right: 50rpx;
	
						.iconbox image {
							width: 31rpx;
							height: 31rpx;
							margin-right: 10rpx;
						}
	
						.textTips {
							font-size: 26rpx;
							font-weight: 500;
							color: #333333;
							white-space: nowrap;
						}
					}
				}
			}
	
			.searchcontent {
				width: 100%;
			}
	
			.historyWrap {
				width: 100%;
				background-color: #FFFFFF;
				padding: 30rpx;
	
				.historyTitle {
					font-size: 28rpx;
					color: #333333;
					font-weight: bold;
				}
	
				.iconbox {
					font-size: 30rpx;
				}
	
				.historyCon {
					margin-top: 10rpx;
					display: flex;
					flex-wrap: wrap;
	
					.historyItem {
						font-size: 24rpx;
						line-height: 34rpx;
						font-weight: 500;
						color: #666666;
						border-radius: 27rpx;
						padding: 8rpx 28rpx;
						margin-top: 20rpx;
						margin-right: 24rpx;
						background-color: #F0F1F7;
						white-space: nowrap;
					}
				}
			}
	
			.guessLike-container{
				width: 100%;
				background-color: #FFFFFF;
				margin-top: 20rpx;
	
				.bottom-title {
					margin-top: 30rpx;
					margin-bottom: 20rpx;
	
					.texttitle {
						font-size: 28rpx;
						font-weight: 500;
						color:#FF4242;
						margin: 0 30rpx;
					}
	
					.bordercontent {
						width: 35rpx;
						height: 4rpx;
						background-color: #FF4242;
					}
				}
	
				.goodsList-container {
					width: 100%;
	
					.listbox {
						width: 100%;
	
						.goods-items-container {
							width: 100%;
							height: 240rpx;
							padding: 0 32rpx;
							border-bottom: 1rpx solid #F0F1F7;
	
							.left-imagecontent {
								width: 200rpx;
								height: 200rpx;
								border-radius: 8rpx;
								overflow: hidden;
							}
	
							.right-goodsinfo-container {
								margin-left: 20rpx;
								width: 460rpx;
								height: 200rpx;
	
								.goodsnameinfo-content {
									width: 100%;
	
									.typeIcon-content {
										width: 60rpx;
										height: 24rpx;
										margin-right: 5rpx;
										margin-top: 8rpx;
									}
	
									.tradename {
										width: 400rpx;
										overflow: hidden;
										text-overflow: ellipsis;
										white-space: nowrap;
										font-size: 28rpx;
										font-weight: 400;
										color: #333333;
									}
								}
	
	
								.price-saleNums-container {
									width: 100%;
									margin-top: 30rpx;
	
									.left-price-box {
										.greytxt {
											font-size: 20rpx;
											font-weight: 400;
											color: #999999;
											line-height: 32rpx;
										}
	
										.rmb {
											font-size: 20rpx;
											font-weight: 600;
											color: #FF4242;
											line-height: 32rpx;
										}
	
										.pricebox {
											font-size: 28rpx;
											line-height: 34rpx;
											font-weight: 600;
											color: #FF4242;
										}
									}
								}
	
								.discounts-container {
									width: 100%;
									margin-top: 10rpx;
	
									.coupon-box {
										width: 102rpx;
										height: 30rpx;
										background: url(../../static/images/goods/couponbac.png)no-repeat;
										background-size: 100% 100%;
										font-size: 20rpx;
										font-weight: 500;
										color: #FF4242;
									}
	
									.back-box {
										width: 100rpx;
										height: 30rpx;
										background: linear-gradient(-90deg, #7619EC, #A429F3);
										border-radius: 5rpx;
										margin-left: 8rpx;
										font-size: 20rpx;
										font-weight: 500;
										color: #FFFFFF;
									}
								}
	
								.saleNum-content {
									width: 100%;
									font-size: 20rpx;
									font-weight: 400;
									line-height: 34rpx;
									margin-top: 10rpx;
									color: #999999;
								}
	
								.shopEnter-bar {
									width: 100%;
	
									.storename {
										font-size: 20rpx;
										font-weight: 400;
										color: #999999;
									}
	
									.enterbtn {
										.enterStore {
											font-size: 20rpx;
											font-weight: 400;
											color: #333333;
											margin: 0 5rpx;
										}
	
										.arrow {
											width: 6rpx;
											height: 12rpx;
											margin-top: 4rpx;
										}
									}
								}
							}
						}
					}
				}
			}
	
			.associationSearch-container {
				width: 100%;
				background-color: #FFFFFF;
	
				.associationList-container {
					width: 100%;
	
					.association-items {
						width: 100%;
						height: 70rpx;
						box-shadow: 0px -1rpx 0rpx 0px #EFF1F7;
						padding: 0 35rpx;
						font-size: 24rpx;
						font-weight: 400;
						color: #333333;
					}
				}
			}
		}
	}
</style>
